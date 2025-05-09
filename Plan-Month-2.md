以下是**第二个月的详细学习计划**，聚焦于轮式机器人在仿真中的运动控制、建图（SLAM）、定位与导航，为后续强化学习做准备。

---

## 🗓️ 第二个月学习计划：**轮式机器人控制 + SLAM + 导航**

### 🎯 本月目标：

* 理解并掌握差速驱动原理与控制实现
* 熟练使用 **SLAM 建图** 与 **AMCL 定位**
* 能在 Gazebo + ROS 中实现机器人自主导航
* 为第三个月 RL 接入准备 Gazebo 环境 + Sensor 模拟

---

## 📅 每周详细安排

---

### 📖 第1周：轮式机器人控制原理与实战

| 日期 | 学习内容                            | 推荐资源                                                                                           |
| -- | ------------------------------- | ---------------------------------------------------------------------------------------------- |
| 周一 | 学习差速驱动运动模型与里程计计算                | [差速驱动控制介绍](https://www.cs.cmu.edu/~16311/s07/labs/NXJ/lab2/diffdrive.html)                     |
| 周二 | 编写 ROS 节点控制机器人行走（订阅 `/cmd_vel`） | 官方 [geometry\_msgs/Twist](http://docs.ros.org/en/noetic/api/geometry_msgs/html/msg/Twist.html) |
| 周三 | 使用键盘遥控机器人运动（teleop）             | `rosrun teleop_twist_keyboard teleop_twist_keyboard.py`                                        |
| 周四 | 记录里程计数据并通过 `rviz` 显示轨迹          | 学习 `nav_msgs/Odometry`                                                                         |
| 周五 | 实践练习：机器人定点巡航                    | 设置定时目标点                                                                                        |
| 周末 | 综合练习：轨迹跟踪、速度控制稳定性调试             | 使用 matplotlib 绘制实际 vs 目标轨迹                                                                     |

---

### 🧭 第2周：SLAM 建图与激光雷达

| 日期 | 学习内容                            | 推荐资源                                                                                           |
| -- | ------------------------------- | ---------------------------------------------------------------------------------------------- |
| 周一 | 安装并运行 gmapping 建图仿真             | [TurtleBot3 SLAM 教程](https://emanual.robotis.com/docs/en/platform/turtlebot3/slam_simulation/) |
| 周二 | 学习激光雷达原理（2D lidar 数据 + 角度 + 噪声） | RPLidar A1/A2 说明书                                                                              |
| 周三 | Gazebo 中添加激光传感器插件 + rviz 可视化    | `gazebo_ros_laser` 插件示例                                                                        |
| 周四 | 使用 `rosbag` 保存仿真数据，回放建图过程       | `rosbag record /scan /odom` 等命令                                                                |
| 周五 | 调试地图质量：对比 lidar 精度、刷新率、仿真精度     | 建图细节调整技巧                                                                                       |
| 周末 | 项目练习：在虚拟室内环境中手动建图并保存 `/map`     | 保存 `.pgm` 与 `.yaml` 地图文件                                                                       |

---

### 📌 第3周：AMCL 定位 + Move Base 路径规划

| 日期 | 学习内容                                       | 推荐资源                                                                        |
| -- | ------------------------------------------ | --------------------------------------------------------------------------- |
| 周一 | 学习 Navigation Stack 架构（costmap、move\_base） | [ROS Navigation Stack 结构](https://www.ncnynl.com/archives/201707/1785.html) |
| 周二 | AMCL 粒子滤波定位原理与参数调整                         | `/amcl` topic & dynamic\_reconfigure                                        |
| 周三 | 设置 static\_map + localization，rviz 可视化位姿   | `initialpose` 工具使用                                                          |
| 周四 | 设置路径目标点并自动导航                               | `2D Nav Goal` 工具                                                            |
| 周五 | 调整代价地图参数，提高路径避障效果                          | `local_costmap`, `inflation_radius`, `obstacle_range`                       |
| 周末 | 综合练习：SLAM → 保存地图 → AMCL → 导航路径 → 到达目标点     | 记录路径时间与性能指标                                                                 |

---

### 🔧 第4周：实战项目 + RL 环境准备

| 日期 | 学习内容                                            | 推荐资源                                                                 |
| -- | ----------------------------------------------- | -------------------------------------------------------------------- |
| 周一 | 使用自定义轮式机器人完成 SLAM 与导航                           | 替代 TurtleBot3 模型                                                     |
| 周二 | 封装机器人控制接口为简易 API（Python）                        | 封装 `/cmd_vel`, `/odom`, `/scan` 等                                    |
| 周三 | 使用 Python 控制机器人导航到多个目标点                         | 编写路径点导航程序                                                            |
| 周四 | 设置 rosbridge\_server + websocket 通信（为 Gym 环境准备） | [rosbridge tutorials](http://wiki.ros.org/rosbridge_suite/Tutorials) |
| 周五 | 设计一个简化 RL 环境接口（reset/step）                      | 仿照 OpenAI Gym 环境接口结构                                                 |
| 周末 | 项目练习：搭建自己的 RL-ready 仿真环境（Gazebo+ROS）            | 为下月 RL 学习做准备                                                         |

---

## 📦 推荐资源汇总

| 类型     | 名称                                                                                  | 链接                                                                                                                                         |
| ------ | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| 教程     | TurtleBot3 SLAM & Navigation                                                        | [https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/](https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/) |
| 教程     | ROS Navigation 中文教程                                                                 | [https://www.ncnynl.com/archives/201707/1785.html](https://www.ncnynl.com/archives/201707/1785.html)                                       |
| 视频     | The Construct SLAM/NAV 课程                                                           | [https://www.theconstructsim.com](https://www.theconstructsim.com)                                                                         |
| GitHub | [turtlebot3\_simulations](https://github.com/ROBOTIS-GIT/turtlebot3_simulations)    | Gazebo 中使用示例                                                                                                                               |
| 视频     | [YouTube - ROS Navigation Full Course](https://www.youtube.com/watch?v=mdC0KfE7fEY) | 英文详解路径规划                                                                                                                                   |

---

## 📁 可选附加内容（我可以提供）

* 第二个月每日任务打卡表（如前月）
* SLAM 参数调试对照表
* AMCL 粒子滤波可视化讲解图
* RL-Gazebo 环境模板（Python 接口，支持 reset/step）
* 视频推荐清单（按子主题整理）

---
