# DAA_HandsOn-6

## Quicksort Benchmark Project

This project implements two versions of the quicksort algorithm (non-random and random pivot) and benchmarks the non-random version for the best, worst, and average cases.

## Files
- `quicksort.py`: Non-random pivot quicksort implementation.
- `quicksort_random.py`: Random pivot quicksort implementation.
- `generate_inputs.py`: Functions to generate best, worst, and average case inputs.
- `benchmark.py`: Script to benchmark non-random quicksort and plot the results.

## How to Run
1. Install required libraries: `pip install numpy matplotlib`.
2. Run the benchmarking script: `python benchmark.py`.

## Benchmark Results

The following results were obtained from running the Quicksort benchmarks for different input sizes. The times are measured in milliseconds (ms) for each case:

```plaintext
Best Case (n=100): 0.155926ms
Worst Case (n=100): 0.174999ms
Average Case (n=100): 0.158072ms

Best Case (n=500): 1.842260ms
Worst Case (n=500): 1.221895ms
Average Case (n=500): 1.496792ms

Best Case (n=1000): 2.285242ms
Worst Case (n=1000): 5.660057ms
Average Case (n=1000): 2.410889ms

Best Case (n=5000): 49.762011ms
Worst Case (n=5000): 27.763367ms
Average Case (n=5000): 20.917892ms

Best Case (n=10000): 36.962032ms
Worst Case (n=10000): 56.139946ms
Average Case (n=10000): 52.241087ms
```

![Graph](https://github.com/user-attachments/assets/7ce9a38f-94fd-477f-9b7b-c4dda03714a2)

## System Information

The benchmarks were run on the following system configuration:

```plaintext
Platform: Darwin 20.6.0
Processor: i386
RAM: 8.00 GB
Python Version: 3.8.9
ROM: 465.57 GB
```

## Deriving the Average Case Time Complexity for Non-Random Quicksort

The average case time complexity of the non-random pivot version of Quicksort can be derived mathematically. In general, Quicksort performs well with random pivots, but when using a fixed pivot strategy (like the first or last element), the average time complexity can be analyzed as follows:

1. **Divide and Conquer**: Each partitioning operation divides the array into two subarrays. The performance depends on how evenly the pivot splits the array.
  
2. **Recursive Formula**: The recursive time complexity can be represented as:
   \[
   T(n) = T(k) + T(n - k - 1) + O(n)
   \]
   where \(k\) is the number of elements in one partition and \(O(n)\) accounts for the time taken to partition the array.

3. **Expected Splits**: On average, the pivot will split the array into two roughly equal halves. This gives us:
   \[
   T(n) = 2T\left(\frac{n}{2}\right) + O(n)
   \]

4. **Master Theorem**: By applying the Master Theorem, we can conclude:
   \[
   T(n) = O(n \log n)
   \]
   Therefore, the average case time complexity of non-random Quicksort is \(O(n \log n)\).
