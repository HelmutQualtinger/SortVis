# SortVis — Sorting Algorithm Visualizer

A single-file interactive visualizer for six classic sorting algorithms, built with plain HTML, CSS, and JavaScript.

## How to Use

Open `index.html` in any modern browser. No build step or server required.

- **Run** — animate the sort automatically at the selected speed
- **Step** — advance one operation at a time
- **Stop** — pause the animation
- **Shuffle** — generate a new random array

Use the sliders to adjust **array size** (10–200 elements) and **animation speed**.

---

## Algorithms

### Bubble Sort

Repeatedly steps through the array, compares adjacent elements, and swaps them if they are in the wrong order. Each full pass bubbles the largest unsorted element to its correct position at the end.

- **Time**: O(n²) average and worst case
- **Space**: O(1)
- **Stable**: yes

### Selection Sort

Divides the array into a sorted and unsorted region. On each pass it finds the minimum element in the unsorted region and swaps it into the next sorted position.

- **Time**: O(n²) in all cases
- **Space**: O(1)
- **Stable**: no

### Insertion Sort

Builds the sorted array one element at a time. Each new element is shifted leftward until it lands in its correct position among the already-sorted elements.

- **Time**: O(n²) average/worst, O(n) best (nearly sorted input)
- **Space**: O(1)
- **Stable**: yes

### Merge Sort

A divide-and-conquer algorithm. It recursively splits the array in half, sorts each half, then merges the two sorted halves back together by comparing elements from each side.

- **Time**: O(n log n) in all cases
- **Space**: O(n) auxiliary
- **Stable**: yes

### Quick Sort

A divide-and-conquer algorithm. A pivot element is chosen (using median-of-three here), and the array is partitioned so that all elements smaller than the pivot come before it and all larger elements come after. The process repeats recursively on each partition.

- **Time**: O(n log n) average, O(n²) worst case (rare with median-of-three)
- **Space**: O(log n) stack
- **Stable**: no

### Heap Sort

First builds a max-heap from the array (a complete binary tree where every parent is larger than its children). Then repeatedly extracts the maximum element from the heap root and places it at the end of the array, shrinking the heap by one each time.

- **Time**: O(n log n) in all cases
- **Space**: O(1)
- **Stable**: no

---

## Visual Legend

| Color | Meaning |
| ----- | ------- |
| Blue → Red gradient | Bar value (blue = small, red = large) |
| Yellow glow | Two bars being **compared** |
| Pink glow | Bar(s) being **swapped / written** |
| Brighter bars | Position confirmed **sorted** |
