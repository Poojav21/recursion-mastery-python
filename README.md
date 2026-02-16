# Recursion Mastery in Python 🔄

A comprehensive collection of recursion problems and solutions in Python, covering fundamental concepts to advanced backtracking techniques. Perfect for learning, interview preparation, and mastering recursive thinking.

## 📚 Overview

This repository contains well-documented Python implementations of classic recursion problems, organized from basic to advanced topics. Each solution includes working examples with test cases executed in Jupyter Notebook.

## 🎯 Topics Covered

### Basic Recursion
- **Number Sequences**: Print 1 to N, N to 1
- **Mathematical Operations**: Sum, Factorial, Power
- **String Manipulation**: Reverse string, Palindrome check
- **Digit Operations**: Count digits, Sum of digits, Reverse number

### Array & List Operations
- **Array Reversal**: Recursive array reversal (two approaches)
- **Fibonacci Sequence**: Classic implementation
- **Array Sorting**: Merge Sort, Quick Sort
- **Search Algorithms**: Binary Search

### Advanced Backtracking
- **Subset Problems**:
  - Generate all subsets
  - Subset sum check
  - Unique subsets (with duplicates)
- **Permutations**:
  - Generate all permutations (arrays)
  - String permutations
  - Unique permutations (with duplicates)
- **Combination Sum**: Find combinations that sum to target

## 📂 Repository Structure

```
recursion-mastery-python/
│
├── MyRecursionNotes.ipynb    # Main Jupyter notebook with all solutions
└── README.md                  # This file
```

## 🚀 Getting Started

### Prerequisites
```bash
python 3.x
jupyter notebook
```

### Running the Notebook

1. Clone the repository:
```bash
git clone https://github.com/yourusername/recursion-mastery-python.git
cd recursion-mastery-python
```

2. Launch Jupyter Notebook:
```bash
jupyter notebook MyRecursionNotes.ipynb
```

3. Run cells to see recursion in action!

## 💡 Key Implementations

### Basic Examples

**Print 1 to N** (Tail Recursion)
```python
def print_1_to_n(n):
    if n == 0:
        return
    print_1_to_n(n-1)
    print(n, end=" ")
```

**Factorial**
```python
def fac(n):
    if n == 0 or n == 1:
        return 1
    return n * fac(n-1)
```

### Advanced Examples

**Generate All Subsets**
```python
def subset(arr):
    def subsets(arr, i, l, ans):
        if i == len(arr):
            ans.append(l.copy())
            return
        l.append(arr[i])
        subsets(arr, i+1, l, ans)
        l.pop()
        subsets(arr, i+1, l, ans)
        return ans
    return subsets(arr, 0, [], [])
```

**Permutations with Duplicates**
```python
def permutation(arr):
    def permutations(arr, f, l, ans):
        if len(l) == len(arr):
            ans.append(l.copy())
            return
        for i in range(len(arr)):
            if i > 0 and arr[i] == arr[i-1] and not f[i-1]:
                continue
            if not f[i]:
                f[i] = True
                l.append(arr[i])
                permutations(arr, f, l, ans)
                l.pop()
                f[i] = False
        return ans
    arr.sort()
    return permutations(arr, [False]*len(arr), [], [])
```

## 🎓 Learning Path

1. **Start with Basics**: Understand base cases and recursive cases
2. **Number Operations**: Practice with factorial, power, sum
3. **String & Array**: Work on reversal and palindrome problems
4. **Sorting & Searching**: Implement merge sort and binary search
5. **Backtracking**: Master subset and permutation generation
6. **Optimization**: Learn to handle duplicates and optimize solutions

## 🔑 Key Concepts Demonstrated

- **Base Case**: Proper termination conditions
- **Recursive Case**: Breaking problems into smaller subproblems
- **Backtracking**: Exploring all possibilities with state restoration
- **Space Complexity**: Understanding call stack depth
- **Duplicate Handling**: Techniques to avoid duplicate solutions

## 📊 Problem Categories

| Category | Count | Difficulty |
|----------|-------|------------|
| Basic Number Operations | 6 | Easy |
| String Operations | 3 | Easy-Medium |
| Array Operations | 4 | Medium |
| Sorting & Searching | 3 | Medium |
| Backtracking | 6 | Medium-Hard |

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Add new recursion problems
- Improve existing solutions
- Add explanations and comments
- Optimize algorithms

## 📝 Notes

- All solutions are tested and working
- Each implementation includes example usage
- Output is shown in the notebook for verification
- Solutions focus on clarity and understanding over optimization

## 🎯 Use Cases

- **Interview Preparation**: Practice common recursion interview questions
- **Algorithm Learning**: Understand recursive problem-solving patterns
- **Teaching Resource**: Use as teaching material for recursion concepts
- **Quick Reference**: Look up recursion patterns and implementations

## 📖 Resources

- [Python Documentation](https://docs.python.org/3/)
- [Introduction to Algorithms](https://mitpress.mit.edu/books/introduction-algorithms)
- [GeeksforGeeks Recursion](https://www.geeksforgeeks.org/recursion/)

## ⚡ Quick Examples

```python
# Fibonacci
fib(5)  # Output: 5

# Palindrome Check
is_palindrome("madam")  # Output: True

# Generate Subsets
subset([1,2,3])  # Output: [[1,2,3], [1,2], [1,3], [1], [2,3], [2], [3], []]

# Permutations
permutation([1,2,3])  # Output: [[1,2,3], [1,3,2], [2,1,3], [2,3,1], [3,1,2], [3,2,1]]
```

## 📜 License

This project is open source and available for educational purposes.

---

⭐ **Star this repo** if you find it helpful for learning recursion!

💬 **Questions or suggestions?** Open an issue or reach out!

Happy Coding! 🚀
