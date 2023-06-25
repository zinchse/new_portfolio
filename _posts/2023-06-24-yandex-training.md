---
layout: post
title: Yandex Training 3.0 - Hints and Results
date: 2023-06-22 13:59:00
description: general conclusions after participating in the contest
categories: code, algorithms, contest
disqus_comments: true
related_posts: false
img: /assets/img/_contest_logo.jpg
---


![contest logo](/assets/img/contest_logo.png){:width="800px"}


> Path **from** *"count the number of characters"*  **to**  *"compress graph by going to graph on connected components, build common transitive vertex to reduce number of edges, set problem on state graph and solve it bypassing 0-1 BFS"* \\
> -- or just [`[Yandex.Training 3.0]`](https://yandex.ru/yaintern/algorithm-training) :D    

I've already seen most of the problems from there in some form, but I really liked the last block. The concept of the `State Graph` is very cool, I recommend everyone to get acquainted.
You can find my solutions and the template with optimal and universal I/O [[here]](https://github.com/zinchse/_contests).

As a result, I took `1-144`th place in the olympiad division, and was the first among those who were left without prizes, both in the both divisions. Interestingly, I wrote an algorithm with optimal asymptotics, which did not pass all the tests, and most of the time I tried to start it. But without success... So, after a couple of months I got back to this problem, and found something amazing (`really :)`). About this I will report in a separate post.

The main experience that I took away from these trainings:

- **`Input/Output` is an important part of the problem**
> you have to think about how fast you read and write data; to combat this problem, I wrote a special [[template]](https://github.com/zinchse/_contests/blob/main/yandex%20training%203.0/template.py) in which you need to organize only one function `solve`, the data is processed by other methods in an optimal way

- **the problem's input limits are the most important information in the problem's definition**
>  you can use them to figure out the asymptotic required solution; my advice is to assume that python can handle `10 ** 7` operations; then a solution with complexity `n * n` for an input size of `10 000` is not even worth writing, while `n * logn` is fine

- **even simple arithmetic operations can be saved** 
> for example, if suddenly within a loop you repeatedly step to elements at some distance, for example `d ** 3`, then by storing this value at each iteration in the `shift` variable, you can significantly speed up the program

- **iterating over rows and columns in a matrix, if they are represented by a list of lists, is not the same thing**
> yes, this is quite a basic rule, but once in an asymptotically optimal solution I ran into this, and for a long time I could not understand what solution the authors of the problem expected from me... the reason for this phenomenon is the physical arrangement of array memory elements and random access speed