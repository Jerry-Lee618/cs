## Pages, Extents, Segments, and Tablespaces
Each tablespace consists of database pages. Every tablespace in a MySQL instance has the same page size. By default, all tablespaces have a page size of 16KB; you can reduce the page size to 8KB or 4KB by specifying the innodb_page_size option when you create the MySQL instance.

The pages are grouped into extents of size 1MB (64 consecutive 16KB pages, or 128 8KB pages, or 256 4KB pages). <font color=red>**The “files” inside a tablespace are called segments in InnoDB**</font>. (These segments are different from the rollback segment, which actually contains many tablespace segments.)

