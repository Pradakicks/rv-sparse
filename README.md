# rv-sparse

Implementation of `sparse_multiply` for the RV-Sparse challenge.
Extracts non-zeros from a dense row-major matrix into caller-owned
CSR buffers (`values`, `col_indices`, `row_ptrs`) and writes
`y = A * x` into a caller-owned `y`. No `malloc` inside the function.

## Build & run
```
gcc -lm -o run challenge.c
./run
```

The harness runs 100 random matrices (5–45 dims, 5–40% density) and
compares the result against a dense reference with a mixed
absolute/relative tolerance of 1e-7.
