# Algorithm and Greedy Algorithm

# Algorithm

An algorithm is a step-by-step problem-solving method. It is a set of instructions that are followed to solve a particular problem. Algorithms are used in various fields such as mathematics, computer science, engineering, and many others. An algorithm takes an input and produces an output through a series of well-defined steps.

# Greedy Algorithm

A greedy algorithm is a simple, intuitive algorithm that is used in optimization problems. The algorithm makes the optimal choice at each step as it attempts to find the overall optimal way to solve the entire problem. The greedy algorithm works by making a series of locally optimal choices that eventually lead to a globally optimal solution.

# Limitations of Greedy Algorithm

However, in many problems, a greedy strategy does not produce an optimal solution. For example, in the animation below, the greedy algorithm seeks to find the path with the largest sum. It does this by selecting the largest available number at each step. The greedy algorithm fails to find the largest sum, however, because it makes decisions based only on the information it has at any one step, and without regard to the overall problem.

![image](https://user-images.githubusercontent.com/85940284/231799501-7a4e3694-db0c-4f33-80be-bd4363f93e15.png)

Despite its limitations, the greedy algorithm is widely used in a variety of optimization problems. Its simplicity and efficiency make it a popular choice for many applications. However, it is important to be aware of its limitations and to carefully consider whether it is the best algorithm for a given problem

# Characteristics of Greedy Algorithm

A greedy algorithm is a problem-solving method that is used in optimization problems. Here are some key characteristics of the greedy algorithm:

There is an ordered list of resources which contain profits, costs, or values etc. These measure the constraints on a system.
Maximum quantity of resources such as max profit, max values etc. are taken when a constraint applies.
In the fractional knapsack problem, the maximum value is taken first according to the availability of capacity.

# Example 

As a busy person with limited time, you want to maximize the number of interesting things you can do within your schedule. You are given an array A of integers, where each element represents the time it takes to complete a task. Your goal is to find the maximum number of tasks that can be completed within a given time T using a greedy algorithm.

To solve this problem, you will sort the array A in increasing order and iteratively select each task, greedily choosing the ones that take the least amount of time to complete while maintaining two variables: currentTime and numberOfTasks. Follow these steps:

Sort the array A in increasing order.
Initialize currentTime and numberOfTasks to 0.
Iterate through each task in A:
a. Add the time it takes to complete the task to currentTime.
b. Increment numberOfTasks by 1.
c. Repeat steps a-b as long as currentTime is less than or equal to T.
Return the value of numberOfTasks.
For example, let A = {5, 3, 4, 2, 1} and T = 6. After sorting A in increasing order, A = {1, 2, 3, 4, 5}. In the first iteration, select the task that takes 1 unit of time to complete, and add 1 to both currentTime and numberOfTasks. In the second iteration, select the task that takes 2 units of time to complete, and add 2 to currentTime and 1 to numberOfTasks. Continue this process until currentTime is greater than T or there are no more tasks to select. The maximum number of tasks that can be completed within T is 3.

# Implementation in C++
Here is a sample implementation of the greedy algorithm in C++:

```
#include <iostream>
#include <algorithm>

const int MAX = 105;
int A[MAX];

int main() {
    int T, N, numberOfTasks = 0, currentTime = 0;

    std::cout << "Enter the number of tasks: ";
    std::cin >> N;
    std::cout << "Enter the time limit: ";
    std::cin >> T;

    for (int i = 0; i < N; ++i) {
        std::cout << "Enter the time for task " << i + 1 << ": ";
        std::cin >> A[i];
    }

    std::sort(A, A + N);

    for (int i = 0; i < N; ++i) {
        currentTime += A[i];
        if (currentTime > T) {
            break;
        }
        numberOfTasks++;
    }

    std::cout << "The maximum number of tasks that can be completed within the time limit is: " << numberOfTasks << std::endl;
    return 0;
}

```
~ For more details Download PDF 
