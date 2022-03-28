# 2. Function
## 2.1 Expression & call expression
**expression** 表达式：本质是一种符号  
**call expression** 调用表达式：复合表达，具有子表达式 subexpression  
*Anatomy of a Call Expression: operator; operand.*
![20220325182140](https://user-images.githubusercontent.com/101033647/160353368-af573082-67af-4a67-a5a7-f284fa215e3d.png)
区别：
![image](https://user-images.githubusercontent.com/101033647/160359465-898ff682-0d26-4c01-b04a-73de77a1428e.png)

Discussion Question 1:  
```
>>> f = min # min->f  
>>> f = max # max->f
>>> g, h = min, max 
>>> max = g #  f: max, g: min, h: max, max: min
>>> max(f(2, g(h(1, 5), 3)), 4)
```

## 2.2 Names, Assignment, and User-Defined Functions
略

## 2.3 Environment Diagrams

