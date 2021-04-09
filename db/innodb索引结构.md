## Pages, Extents, Segments, and Tablespaces
Each tablespace consists of database pages. Every tablespace in a MySQL instance has the same page size. By default, all tablespaces have a page size of 16KB; you can reduce the page size to 8KB or 4KB by specifying the innodb_page_size option when you create the MySQL instance.

The pages are grouped into extents of size 1MB (64 consecutive 16KB pages, or 128 8KB pages, or 256 4KB pages). **The “files” inside a tablespace are called segments in InnoDB**. (These segments are different from the rollback segment, which actually contains many tablespace segments.)

**Two segments are allocated for each index in InnoDB. One is for nonleaf nodes of the B-tree, the other is for the leaf nodes. Keeping the leaf nodes contiguous on disk enables better sequential I/O operations, because these leaf nodes contain the actual table data.**

Some pages in the tablespace contain bitmaps of other pages, and therefore a few extents in an InnoDB tablespace cannot be allocated to segments as a whole, but only as individual pages.

## How Pages Relate to Table Rows
**The maximum row length is slightly less than half a database page**. For example, the maximum row length is slightly less than 8KB for the default 16KB InnoDB page size, which is defined by the innodb_page_size configuration option.

If a row does not exceed the half page limit, all of it is stored locally within the page. **If a row exceeds the half page limit, variable-length columns are chosen for external off-page storage until the row fits within half a page.** External off-page storage for variable-length columns differs by row format:

- COMPACT and REDUNDANT Row Formats

When a variable-length column is chosen for external off-page storage, **InnoDB stores the first 768 bytes locally in the row, and the rest externally into overflow pages**. Each such column has its own list of overflow pages. ***The 768-byte prefix is accompanied by a 20-byte value that stores the true length of the column and points into the overflow list where the rest of the value is stored***. See Section 14.11, “InnoDB Row Formats”.

- DYNAMIC and COMPRESSED Row Formats

When a variable-length column is chosen for external off-page storage, InnoDB stores a 20-byte pointer locally in the row, and the rest externally into overflow pages. See Section 14.11, “InnoDB Row Formats”.
