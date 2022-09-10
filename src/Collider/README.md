# Collider

碰撞体，用于物体间产生阻碍或检测碰撞。

## 碰撞型检测

碰撞时两物体产生阻碍

| 方法                                      | 说明                   |
| ----------------------------------------- | ---------------------- |
| [OnCollisionEnter](./OnCollisionEnter.md) | 碰撞时被调用           |
| [OnCollisionExit](./OnCollisionExit.md)   | 碰撞体离开时被调用     |
| [OnCollisionStay](./OnCollisionStay.md)   | 碰撞体持续碰撞时被调用 |

## 触发型检测

碰撞时两物体不产生阻碍

| 方法                                  | 说明               |
| ------------------------------------- | ------------------ |
| [OnTriggerEnter](./OnTriggerEnter.md) | 触发器进入时被调用 |
| [OnTriggerExit](./OnTriggerExit.md)   | 触发器退出时被调用 |
| [OnTriggerStay](./OnTriggerStay.md)   | 在触发器内时被调用 |

## 补充

OnCollisionxxx 使用注意：

* 碰撞双方都有碰撞体或者刚体
* 如果双方都有刚体，需要勾选 `isKinematic`
* 双方都不可勾选 `isTrigger`

OnTriggerxxx 使用前提：

* 碰撞双方都有碰撞体
* 至少有一方有刚体
* 双方至少有一方勾选 `isTrigger`