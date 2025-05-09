以下是为期**1个月**的详细学习计划，专注于**机器人建模、ROS、Gazebo 仿真**等内容，为后续强化学习和高级仿真做好准备。计划按每周细分，包含每日学习任务和推荐资源。

---

## 🗓️ 第1个月详细学习计划（不含数学和 Python）

### 🎯 本月目标：

* 掌握 ROS (Noetic 或 ROS2) 的核心概念与基本操作
* 能够建模一个简单的轮式机器人（URDF）
* 掌握 Gazebo 仿真环境的使用，完成轮式机器人在仿真世界中的控制
* 为第2个月的导航与 RL 做好仿真基础

---

## 📅 第1周：ROS 基础与环境搭建

| 日期 | 内容                                     | 推荐资源                                                               |
| -- | -------------------------------------- | ------------------------------------------------------------------ |
| 周一 | 安装 ROS（Noetic）与工作空间设置                  | [ROS Wiki 安装指南](http://wiki.ros.org/noetic/Installation/Ubuntu)    |
| 周二 | 学习 ROS 节点、话题、服务的通信机制                   | [ROS 官方 Tutorials](http://wiki.ros.org/ROS/Tutorials)（1-7）         |
| 周三 | 学习 `rosrun`、`roslaunch`、参数服务器、rosparam | Tutorials 8-12                                                     |
| 周四 | 学习 TF 坐标变换                             | [TF Tutorials](http://wiki.ros.org/tf/Tutorials)                   |
| 周五 | 使用 `rviz` 可视化 TF、雷达、机器人状态              | rviz 教程 / 官方 Demo                                                  |
| 周末 | 练习：建立两个节点通信，发布/订阅坐标点                   | 自己写 Python 节点或参考 [The Construct](https://www.theconstructsim.com/) |

---

## 📅 第2周：URDF 机器人建模与仿真入门

| 日期 | 内容                              | 推荐资源                                                            |
| -- | ------------------------------- | --------------------------------------------------------------- |
| 周一 | 学习 URDF 文件结构、link/joint 类型      | [URDF Tutorials](http://wiki.ros.org/urdf/Tutorials)            |
| 周二 | 建模两轮差速机器人 + rviz 可视化            | 用 `xacro` 重构模型                                                  |
| 周三 | 给机器人加传感器（激光雷达、IMU）              | TurtleBot3 URDF 作为参考                                            |
| 周四 | 安装 Gazebo 与 ROS 插件，运行仿真         | [Gazebo + ROS](http://gazebosim.org/tutorials?tut=ros_overview) |
| 周五 | 将 URDF 模型导入 Gazebo，调试启动脚本       | `gazebo_ros_control`                                            |
| 周末 | 项目练习：建模你自己的简单轮式机器人并在 Gazebo 中运行 | 可参考 TurtleBot3 的结构，但简化                                          |

---

## 📅 第3周：机器人控制与世界建模

| 日期 | 内容                            | 推荐资源                    |
| -- | ----------------------------- | ----------------------- |
| 周一 | 学习 `cmd_vel` 控制差速机器人运动        | `geometry_msgs/Twist`   |
| 周二 | 写一个 ROS 节点让机器人定速前进和转弯         | Python / C++            |
| 周三 | 使用键盘控制机器人（teleop）             | `teleop_twist_keyboard` |
| 周四 | Gazebo 世界建模，添加障碍物与地图          | SDF/World 文件语法          |
| 周五 | 给机器人添加激光雷达插件                  | `gazebo_ros_laser`      |
| 周末 | 项目练习：创建带障碍的室内环境并控制机器人避障（暂用手动） | 结合 rviz 可视化激光数据         |

---

## 📅 第4周：SLAM 与导航入门（为第2月铺垫）

| 日期 | 内容                                 | 推荐资源                                                                                       |
| -- | ---------------------------------- | ------------------------------------------------------------------------------------------ |
| 周一 | 安装 `turtlebot3` 仿真包并运行其 SLAM 示例    | [TurtleBot3 e-Manual](https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/) |
| 周二 | 运行 gmapping 建图仿真，理解话题结构            | `/scan`, `/map`, `/tf` 等                                                                   |
| 周三 | 运行 Navigation Stack 进行路径规划         | `move_base`, `amcl`                                                                        |
| 周四 | 学习 costmap、路径规划算法原理                | [ROS Navigation Stack 中文教程](https://www.ncnynl.com/archives/201707/1785.html)              |
| 周五 | 自己尝试让 TurtleBot3 在虚拟房间中从 A 点走到 B 点 | 结合 rviz 设置导航目标                                                                             |
| 周末 | 总结复盘，准备进入下个月 RL 部分                 | 整理 URDF、launch、仿真环境结构                                                                      |

---

## 📦 本月推荐资源汇总

| 类型     | 名称                                 | 链接                                                                                     |
| ------ | ---------------------------------- | -------------------------------------------------------------------------------------- |
| 视频课程   | The Construct ROS Basics in 5 Days | [https://www.theconstructsim.com/](https://www.theconstructsim.com/)                   |
| GitHub | TurtleBot3 仓库                      | [https://github.com/ROBOTIS-GIT/turtlebot3](https://github.com/ROBOTIS-GIT/turtlebot3) |
| 文档     | ROS 官方 Wiki                        | [http://wiki.ros.org/](http://wiki.ros.org/)                                           |
| 视频     | Gazebo 官方教程                        | [https://classic.gazebosim.org/tutorials](https://classic.gazebosim.org/tutorials)     |
| 仿真环境   | turtlebot3\_simulations            | `apt install ros-noetic-turtlebot3-simulations`                                        |

---
