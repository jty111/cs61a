# 2. Function
## 2.1 Expression & call expression
**expression** 表达式：本质是一种符号  
**call expression** 调用表达式：复合表达，具有子表达式 subexpression  
*Anatomy of a Call Expression: operator; operand.*
![20220325182140](https://user-images.githubusercontent.com/101033647/160353368-af573082-67af-4a67-a5a7-f284fa215e3d.png)
区别：
![image](https://user-images.githubusercontent.com/101033647/160359465-898ff682-0d26-4c01-b04a-73de77a1428e.png)



## 2.2 Names, Assignment, and User-Defined Functions
name: 
> If a value has been given a name, we say that the name binds to the value.  
> Names can also be bound to functions.  

assignment 赋值
> In Python, we can establish new bindings using the assignment statement, which contains a name to the left of = and a value to the right.  

注意 **=** 的赋值意义，从右到左

Discussion Question 1:  
```
>>> f=min
>>> f
<built-in function min>
>>> f = max 
>>> f
<built-in function max>
>>> g,h = min,max
>>> g
<built-in function min>
>>> h
<built-in function max>
>>> max = g
>>> g
<built-in function min>
>>> max
<built-in function min>
>>> f
<built-in function max>
>>> g
<built-in function min>
>>> h
<built-in function max>
>>> max(f(2, g(h(1, 5), 3)), 4)  
3
>>> h(1,5)
5
>>> g(h(1, 5), 3) 
3
>>> f(2, g(h(1, 5), 3))    
3
>>> max(f(2, g(h(1, 5), 3)), 4)
3
```

## 2.3 Environment Diagrams
![image](https://user-images.githubusercontent.com/101033647/160550262-97674045-fb52-419b-84cd-04c1eaf6dabc.png)

Environment: memories that keep tract of the bindings between names and values.

注意 **Frame** 的含义：框架？体系？  
解释器可视化过程：https://pythontutor.com/composingprograms.html#mode=edit

## 2.4 Defining Functions  
### def & assignment 区别：
- def:  binds names to expressions  
- assignment: binds names to values  

![image](https://user-images.githubusercontent.com/101033647/160552269-8a2daa72-2ad7-4fd1-9476-ca5d405f9267.png)
- signiture: 参数列表  
- body: 函数体，应用函数时执行的计算

### Calling/applying user-def funtions
在定义时，function本身并没有执行，需要调用  

调用步骤：
1. Add a local frame, forming a new environment **建立本地框架新环境**
2. Bind the function's formal parameters to its arguments in that frame 实参绑定形参
3. Execute the body of the function in that new environment 在新环境中执行  

![image](https://user-images.githubusercontent.com/101033647/160562877-fe85d886-c2a1-456e-8bd5-f1094e6efcf5.png)

signature的重要性：包含构建frame的信息（参数性质？）
> A function’s signature has all the information needed to create a local frame  

### Looking Up Names In Environments  
现有环境：
- global frame
- local frame + global frame    
*local frame调用后才产生 具有查找优先级* 


> An environment is a sequence of frames.     

框架搭建下成立环境


> A name evaluates to the value bound to that name in the earliest frame of the current environment in which that name is found.      

怎么理解... 
某name的计算值，是最初建立框架（定义 define function）在现有环境（参数赋值 bind formal parameters to its arguments）的运行结果
