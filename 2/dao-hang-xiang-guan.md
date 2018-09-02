---
description: apply to Navigation field
---

# Navigation



* A Deep-Network Solution Towards Model-less Obstacle Avoidance
  * 这俩人专门研究 DRL机器人避障的.挺专业的
* Building Generalizable Agents with a Realistic and Rich 3D Environment

  > Yi Wu , UC Berkeley , yuxin wu, Facebook AI, ICLR , 2018

  * 建立了一个 House3D 的东西, 基于 SUNCG 数据库. 用于室内导航的. 大量采集的图像形成各 library

* Control of Memory, Active perception, and Action in Minecraft
  * 利用外部记忆结构\(类似 NTM,DNC,MemNN\)通过将记忆存入外部记忆结构,提高 Agnet 的迁移能力,导航能力泛化到没见过的场景. 作者是密歇根大学博士生,
* Deep Reinforcement Learning in a 3-D Blockworld Environment
  * 使用CNNs 与 DQN 网络来提取图像深度信息. 使用Minecraft 环境, 开源的. 视觉输入,估计距离.
* Learning Sample-Efficient Target Reaching for Mobile Robots

  > Arbaaz Khan , 2018

  * 机器人寻找目标导航. 雷达扫描距离; 可以参考本文写作,很好.
  * 使用 gym-gazebo 仿真环境测试.并且进行了实物测试.

* LEARNING TO NAVIGATE IN COMPLEX ENVIRONMENTS
  * 类似微软屏幕保护的迷宫环境. 此文追求累积奖励最大化与辅助任务 loss 降低,达到提高数据效率和训练效果的目标.此文顺便做了 slam 的工作. agent 需要有长短的记忆来存储环境中的动态因素. 本文目标是找到东西,辅助任务是对输入的图像给出深度信息有利于路径规划,另一个是知道 slam 的 loop closure, 就是知道这个地方我曾经来过;文中模型: A3C, LSTM , stacked LSTM. NavA3C; 本文中的环境是开源的.
* Towards cognitive exploration through deep Reinforcement learning

  > Lei Tai , Ming Liu , 2016

  * 使用图像输入的深度信息探测距离,避障功能.使用了卷积神经网络.并且在生活中做了实验. 可以参考一下. 从图像信息中提取深度信息.

