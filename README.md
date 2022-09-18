# Finding shortests path using networkx and numpy packages

## Task 1 : Write a function which finds a shortest path with least traffic jam and returns that path.
### Starting point : (1,3) (_index_)
### Finish point : (4,2) (_index_)

![sp1](https://user-images.githubusercontent.com/113797630/190903362-2a282549-52bc-439e-9a84-c8eb8af3ce64.png)
---
Firstly, let's understand the task deeply to solve it in detail. Imagine that you are going to write a program for the cab company which finds out best route for drivers. That program has to look through all possible ways one by one to choose best of them, in the same time it should consider traffic jams for being avoid them. So, think of roads on map as lines which goes through rows and columns of matrix. This task requires writing exactly the same program. Let's go on with solution of task.

I got help of networkx and numpy packages on this task, for solving the task with less lines of code and time. Firstly, I have used **NetworkX** **nx.grid_2d_graph**, it is **Graph generator**, that returns the **2d grid graph of mxn nodes**, each being connected to its nearest neighbors. So, after getting that map, program gets chance of estimating shortests path between wanted nodes(each matrix element is called node, the lines which connects them are called edges) and I have done it using **nx.all_shortest_paths** method of module. Second step is counting number of cars(_least traffic jam_) which driver will be encountered during journey. To get that value, I have used for **loop** to check all shortests path indices which are given by **NetworkX** module. When, loop ends, returns the path with least number of cars as final result.

As it is shown picture above, journey starts with the index of (1,3) and tries all possible ways to reach final point (4,2). Finally, **red** and **pink** colored arrows are chosen as candidates to be the best route. Then, program checks both roads to select one of them with less jam. And pink colored route is our winner.

---
## Task 2 : Write a function which finds a shortest path to given index then to finish point with least traffic jam.
### Starting point : (0,0_index_)
### First destination : (1,3) (_index_)
### Finish point : (4,2) (_index_)

![sp2](https://user-images.githubusercontent.com/113797630/190908073-9258f6cf-1f7a-4fbf-8db1-35e7cc606451.png)
---
In this task, requirement differs a little bit than previous one. The difference is going to given index instead of directly final point. Going back to imagination of cab company, this task requires writing the **entire navigation**(_to customer, then finish point_).

Returning back to the task, program is so simple for people who understood workflow of first task. The program need to find out 2 paths together(_first is from starting point to first destination, second is the from first destination to the final point_) and combine them. Process of getting paths are exactly the same separatedly as I have written in first task.

According to picture above, 'taxi driver' starts from (0,0) index which is marked with green color, wants to go index of (1,3). By the help of less number of cars, red colored arrow is chosen as best route from 2 candidates (_red and yellow_). Second step is getting best 'road' to reach out index of (4,2) (_finish point_). As i wrote in first task, **pink** and **red** colored arrows are candidates. Pink colored arrow (_route_) is chosen because of containing only 6 'cars'.

---
## Task 3 : Write a function which calculates fare of journey too.
### Starting point : (0,0_index_)
### First destination : (1,3) (_index_)
### Finish point : (4,2) (_index_)

![sp3](https://user-images.githubusercontent.com/113797630/190911768-a5a60b63-9a0a-4ae6-ad88-d13793b73a52.png)
---

All the processes is the same as written in task 2. I will write merely calculation of fare for journey.

---
**Fare for journey = (number of cars encountered during journey) * 0.2 + steps * 0.5**

---

So, I have got number of cars using 'sum' variable as storage and summing all numbers which are located in the indices  given by shortest path function. As a number of steps, if we call number of index couples are returned from function as **n** then **n-1** will be number of steps which have been taken during process. And we can calculate fare for trip using formula given above. For my task, it's 7.6$.

---
