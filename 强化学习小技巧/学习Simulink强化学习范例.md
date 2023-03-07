## 学习Simulink强化学习范例

显示神经网络可学习参数的数量

```matlab
summary(criticNetwork)
```

![image-20230306200612512](D:\common\本地图库\image-20230306200612512.png)

检查神经网络输出

```matlab
getValue(critic,{rand(obsInfo.Dimension)},{rand(actInfo.Dimension)})
```

```matlab
getAction(actor,{rand(obiInfo.Dimension)})
```

```
getAction(agent,{rand(obsInfo.Dimension)})
```

getValue(critic,{[0 0 3.6e4]},{[0]})

getAction(actor,{[0 0 3.6e4]})

getAction(A

gent,{[0 0 3.6e4]})

DDPG程序对应xFinal230227初始状态