# 控制理论基本概念

## 系统表达形式

1. 状态空间形式（时域）

状态方程 ẋ = Ax + Bu
输出方程 y = Cx + Du


```text
                                      d(t) 物理扰动
                                           |
                                           v
r(t) 期望 --->(+)Σ(-)<----+     e(t) --> [ C(s) ] --> u(t) --> [ P(s) ] --+--> y(t) 实际
                          |                                               |
                          |                                               |
                          +<---------(+)Σ(+)---------- [ H(s) ] <---------+
                                        ^
                                        |
                                n(t) 测量噪声
```
注意⚠️：控制器的输入不一定是 r(t) - y(t), 这只是其中一种形式。

- **信号定义**：
  - `r(t)` (Reference): 期望/参考信号
  - `y(t)` (Output): 系统实际状态/输出
  - `y_m(t)` (Measured Output): 传感器测得的实际状态，`y_m(t) = H(s)y(t) + n(t)`
  - `e(t)` (Error): 误差信号，`e(t) = r(t) - y_m(t)`
  - `u(t)` (Control Input): 控制器的输出，被控系统的控制输入，`u(t) = C(s)e(t)`
  - `d(t)` (Disturbance): 作用在被控对象上的物理扰动（如风力、负载突变）
  - `n(t)` (Noise): 传感器读取数据时引入的高频测量噪声

- **模块定义** (s 域传递函数)：
  - `C(s)` (Controller): 控制器（如 PID 算法）
  - `P(s)` (Plant/Process): 被控对象/系统
  - `H(s)` (Sensor/Measurement): 测量环节/传感器动态（有时假设传感器是理想的，即 `H(s)=1`）


2. 高阶微分方程（时域）

3. 拉普拉斯变换形式（复频域）

4. 傅里叶变换形式（频域）




# Internal Model Principle

## 原型理论
[理论证明参考文章](https://zhuanlan.zhihu.com/p/131348966)

鲁棒性。即使被控系统的参数发生变化，或者外部信号的幅值、初值未知，只要控制器中包含正确的“内模”，系统就能自动调整，实现稳态误差为零。

被控对象  ẋ = Ax + Bu

参考信号模型 ẋᵣ = Aᵣ xᵣ

扰动模型 ẋ_d = A_d x_d



## Hybrid Internal Model
https://arxiv.org/pdf/2312.11460

问题1：如何进行对比学习

问题2： 如何证明HIM的引入是有作用的



## Perceptive Internal Model
https://arxiv.org/pdf/2411.14386

问题1： 如何证明PIM的引入是有作用的，没有对比实验？



# H-infinity/H无穷控制理论

https://arxiv.org/pdf/2404.14405

# 柔顺控制

[Dobot 笛卡尔柔顺控制器设计原理](https://github.com/GuangjunZeng/dynamic_rotation/blob/main/serl/serl_dobot/impedance_controller.md)

# MPC

注： zhongyu有一篇人形结合MPC的文章





