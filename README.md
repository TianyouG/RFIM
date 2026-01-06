This repository provides the source code for the paper:

- Tianyou Gao and Takayuki Ito. 2026. Robust Fair Influence Maximization under Multiple Community Partitions. Proc. ACM Manag. Data 4, 1 (SIGMOD).

## Compilation

To compile the code, use the following command:

    g++ -std=c++17 -O3 rfim.cpp -o rfim

## Usage

### Step 1: Format the Graph

Before running the algorithm, format the graph:

```bash
./rfim -func=format -graphname=facebook -pdist=wc
```
### Step 2: Run the Algorithm

Execute the sg-hist method with the specified parameters:

```bash
./rfim -func=rfim -graphname=facebook -pdist=wc -seedsize=100 -eps=0.1 -delta=0.05 -method=sgh
```

## Important Parameters

Option       | Type    | Description
------------ | ------- | --------------------------------------------
-func         | string  | Task to perform: `format` or `rfim`
-graphname    | string  | Name of the input graph
-pdist        | string  | Propagation model; we use `wc` in the paper
-seedsize     | int     | Number of seeds to select, `k` in the paper
-eps          | double  | Error bound for approximation
-delta        | double  | failure probability
-method       | string  | Method to use: `sgh`, `sg`, `ag`, `wag1`, or `wag2`

**Method options:**
- `sgh`: SG-HIST (proposed method)
- `sg`: SingleGreedy (baseline method)
- `ag`: AllGreedy (baseline method)
- `wag1`: WAGreedy1 (baseline method)
- `wag2`: WAGreedy2 (baseline method)

## Base Code Acknowledgement

This code builds upon the implementation of:

- Qintian Guo, Sibo Wang, Zhewei Wei, and Ming Chen. 2020. Influence Maximization Revisited: Efficient Reverse Reachable Set Generation with Bound Tightened. In SIGMOD.

## Related Projects

For reference and comparison, please see the following open-source projects:

- SUBSIM / HIST: https://github.com/qtguo/subsim
- OPIM / OPIM-C: https://github.com/tangj90/OPIM