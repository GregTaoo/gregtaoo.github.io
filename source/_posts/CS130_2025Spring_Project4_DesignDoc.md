# CS 130: Project 4 - File Systems Design Document

## Group Information

Please provide the details for your group below, including your group's name and the names and email addresses of all members.

- **Group Name**: *[Enter your group name here]*
- **Member 1**: FirstName LastName `<email@shanghaitech.edu.cn>`
- **Member 2**: FirstName LastName `<email@shanghaitech.edu.cn>`



---

## Preliminaries

> If you have any preliminary comments on your submission, notes for the TAs, or extra credit, please give them here.

*Your answer here.*



---

## Indexed and Extensible Files

### Data Structures

> **A1:** Copy here the declaration of each new or changed `struct` or struct member, global or static variable, `typedef`, or enumeration. Identify the purpose of each in 25 words or less.

*Your answer here.*



> **A2:** What is the maximum size of a file supported by your inode structure? Show your work.

*Your answer here.*



### Synchronization

> **A3:** Explain how your code avoids a race if two processes attempt to extend a file at the same time.

First, `sema_down (&inode->write_sema);`. If it does not extend a file, then `sema_up`. If it extends a file, `sema_up` when writing being finished. Thus ensures only a single process can extends a file.



> **A4:** Suppose processes A and B both have file F open, both positioned at end-of-file. If A reads and B writes F at the same time, A may read all, part, or none of what B writes. However, A may not read data other than what B writes (e.g., if B writes nonzero data, A is not allowed to see all zeros). Explain how your code avoids this race.

Only when B finishes writing all data to cache can the length of this inode be modified to the new length. It means A cannot read the data beyond the current length.


> **A5:** Explain how your synchronization design provides "fairness." File access is "fair" if readers cannot indefinitely block writers or vice versa—meaning that many readers do not prevent a writer, and many writers do not prevent a reader.

No locks for readers. Only when a writer extends a file, there could be a lock to prevent some writers. When finishes extending the file, release the lock. So there is no fairness problems.



### Rationale

> **A6:** Is your inode structure a multilevel index? If so, why did you choose this particular combination of direct, indirect, and doubly indirect blocks? If not, why did you choose an alternative inode structure, and what advantages and disadvantages does your structure have compared to a multilevel index?

Yes. It is a classic UNIX design. 



---

## Subdirectories

### Data Structures

> **B1:** Copy here the declaration of each new or changed `struct` or struct member, global or static variable, `typedef`, or enumeration. Identify the purpose of each in 25 words or less.

```c
/* A directory. */
struct dir {
  struct inode *inode;                /* Backing store. */
  int32_t pos;                          /* Current position. */
  struct semaphore sema;
};

/* A single directory entry. */
struct dir_entry {
  block_sector_t inode_sector;        /* Sector number of header. */
  char name[NAME_MAX + 1];            /* Null terminated file name. */
  bool in_use;                        /* In use or free? */
  bool is_dir;
};
```

```c
struct thread {
    ...
    uint32_t current_dir;
}
```

### Algorithms

> **B2:** Describe your code for traversing a user-specified path. How do traversals of absolute and relative paths differ?

Simply traverse through the path provided. Because I will create `.` and `..` for each directory, so there is no difference.


### Synchronization

> **B4:** How do you prevent races on directory entries? For example, only one of two simultaneous attempts to remove a single file should succeed, as should only one of two simultaneous attempts to create a file with the same name.

There is a semaphore to wrap the code for removing a file, i.e. `sema_down (&dir->sema);` after looking it up and before starting to remove it, then `sema_up (&dir->sema);` when everything is done.



> **B5:** Does your implementation allow a directory to be removed if it is open by a process or if it is in use as a process's current working directory?  
> If so, what happens to that process's future file system operations? If not, how do you prevent it?

Processes currently have opened this file can still read/write on it until all file descriptors are freed.



### Rationale

> **B6:** Explain why you chose to represent the current directory of a process the way you did.

This allows efficient access to the directory entries and simplifies implementation of path resolution (e.g., `.` and `..`). It also avoids the overhead of repeatedly parsing absolute paths and ensures consistency with the file system’s internal structures.



---

## Buffer Cache

### Data Structures

> **C1:** Copy here the declaration of each new or changed `struct` or struct member, global or static variable, `typedef`, or enumeration. Identify the purpose of each in 25 words or less.

```c
struct cache_entry {
  void *addr;
  block_sector_t sector;
  bool accessed;
  bool dirty;

  struct hash_elem elem;
};
```


### Algorithms

> **C2:** Describe how your cache replacement algorithm chooses a cache block to evict.

Second chance. First choose an cache entry that is not accessed and not dirty to evict. Then traverse again, evict the first entry who is dirty but not accessed, then mark all entries traversed as not accessed.



> **C3:** Describe your implementation of write-behind.

All writings go through the cache module, and modified (dirty) blocks are marked but not immediately written to disk. Instead, periodically flushes dirty blocks to disk in batches.



> **C4:** Describe your implementation of read-ahead.

*Your answer here.*



### Synchronization

> **C5:** When one process is actively reading or writing data in a buffer cache block, how are other processes prevented from evicting that block?

Selecting a cache entry or evicting it is an atomic operation and protected by a semaphore. Only a single process can do an eviction at the same time.



> **C6:** During the eviction of a block from the cache, how are other processes prevented from attempting to access the block?

The same as C5. Selecting a cache entry is protected by the same semaphore.



### Rationale

> **C7:** Describe a file workload likely to benefit from buffer caching, and workloads likely to benefit from read-ahead and write-behind.

A workload that repeatedly accesses the same files or blocks greatly benefits from buffer caching. Since the same file blocks are accessed repeatedly, caching avoids redundant disk I/O and significantly improves performance.



---

## Survey Questions

> Do you have any suggestions for the TAs to more effectively assist students, either for future quarters or the remaining projects? Any other comments?

Nothing here
