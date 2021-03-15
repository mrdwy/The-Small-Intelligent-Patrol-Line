# The-Small-Intelligent-Patrol-Line
一个可循线的双红外传感器巡线小车，有自己独特的算法，期待与大家交流。（学校智能车的寒假作业，低调copy）嘘~


# 安装问题
1.本人的安装可能与你的电机安装不尽相同，所以安装后要对代码进行调试
2.红外传感器使用的时候，将其放到黑线上，不要活动位置，用螺丝刀轻扭滑动变阻器，等指示灯恰好由亮变灭时，停止调试
3.红外传感器安装在车模的最前方俩个孔里以便于与代码适配，
4.红外的下方两个红外探头可以掰弯，掰弯后。使其两个红外同时接触到黑线的时间较长对本机的调试更有利。即左右移动时两个红外（已经经过步骤2调试后的红外传感器）一起灭的范围较大

# 代码问题
1。循线逻辑
  ①直行时，两个红外同时触线——直行
          一侧触线 ，另一侧不触线，进入修正。改变左右轮的差速，使其稍微的左右转动回归正常的角度
  ②过弯时，当两个红外同时不触线时（入弯的标志），进入过弯模式，不再采用左右差速转动，采用左右轮反向转动。（大角度摆动）
          左转右转的判断解决方式如下
          每次读取红外传感器的值的时候，将上一次的读取内容保存到一组值中，当进入过弯模式时，将上一组存取的值读取出来，判断左转还是右转
 
# 未解决的问题/调试的难点
1。本车未采用速度pid，直行时两轮的转速不同，可以通过手动改变差速解决，不过上pid可能更好些，自己拓展。也希望改进后能分享给我
2.两个红外的探头方向不太一样，导致两个红外同时触线的范围比较小。
3.直行时左右轮差速调整比较费时费力（我没调，直接让他左右摆动去吧，也能跑）
4.正常的话使用if语句左侧红外碰线，往左拐，右侧红外碰线往右拐，也可以完成循线任务，不过小车会一直左右摆头（虽然本代码没调好也会左右摆头）
5.红外的阈值调整也是个难点，发现有些弯能过去，有些就原地转圈了，可能就是红外的问题。

加油小伙子/大哥哥
