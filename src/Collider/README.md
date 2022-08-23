# Collider

碰撞体，用于物体间产生阻碍或检测碰撞。

* 碰撞型检测（两物体产生阻碍）
    * [OnCollisionEnter](./OnCollisionEnter.md) 碰撞时被调用
    * [OnCollisionExit](./OnCollisionExit.md) 碰撞体离开时被调用
    * [OnCollisionStay](./OnCollisionStay.md) 碰撞体持续碰撞时被调用

* 触发型检测（两物体不产生阻碍）
    * [OnTriggerEnter](./OnTriggerEnter.md) 触发器进入时被调用
    * [OnTriggerExit](./OnTriggerExit.md) 触发器退出时被调用
    * [OnTriggerStay](./OnTriggerStay.md) 在触发器内时被调用

## 注意事项

### 使用前提

* 碰撞双方都有碰撞体
* 其中一方有刚体
* 如果是触发型检测需要将 `isTrigger` 属性设为 `true`（两个物体都启用了 `isTrigger` 则不会发生碰撞）

### 使用步骤

1. 确定写代码的位置。分析碰撞的两者中谁要检测这个碰撞，谁检测就在谁的脚本中写代码。有可能两者都可以去做这个检测，那选择其中一个就行。
   
2. 确定用哪组检测函数。分析这个碰撞是否是阻碍性的，如果是选用OnCollisionXXX函数，非阻碍性的碰撞则用OnTriggerXXX函数检测。

3. 确定检测时机。OnCollisionXXX和OnTriggerXXX，其XXX部分可以替换为Enter,Stay,Exit。如果是持续检测用Stay，如果时单次检测，碰撞体接近时检测用Enter,碰撞体离开时检测用Exit。

4. 编写碰撞处理代码。在编写过程中可以使用参数获取碰撞时对方的信息。