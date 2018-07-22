# Cross - 叉积

--------

#### 数学定义

1. 向量

向量$$ v = [x, y, z] $$表示三维空间中一个有长度的方向，单位长度为$$ 1 $$。

或者也可以写作：

$$
v = x \times i + y \times j + z \times k
$$

其中$$ i, j, k $$是$$ x, y, z $$三个轴上的单位向量，平面中的向量可以视为$$ z $$轴为$$ 0 $$的三维空间中一种特殊的向量。

2. 点积

两个向量的点积计算方式如下：

$$
v_{1} \cdot v_{2} = x_{1} \times x_{2} + y_{1} \times y_{2} + z_{1} \times z_{2}
$$

两个向量的点积结果是一个数字。

3. 叉积

两个向量的点积计算方式如下：

$$
//v1 cross v2 =	| i   j   k  |
//              | x1  y1  z1 |
//              | x2  y2  z2 |
$$

叉积的结果是一个向量，此向量遵循右手法则，将右手四指卷起大拇指伸出。从$$ v1 $$沿着四根卷起的手指指向v2 叉积结果向量与大拇指方向相同 与v1和v2所在平面垂直。

4. 行列式计算公式
//| a b c | = 
//| d e f |
//| g h i |
//  a*(-1)^(1+1)*| e f | + b*(-1)^(1+2)*| d f | + c*(-1)^(1+3)*| d e |
//               | h i |                | g i |                | g h |
//
//| a b | = a*d - b*c
//| c d |
//可得三维空间中v1 cross v2 = (y1*z2 - y2*z1)i-(x1*z2 - x2*z1)j+(x1*y2 - x2*y1)k
//二维平面中v1 cross v2 = (x1*y2 - x2*y1)k
//5)向量夹角
//在平面中v1 cross v2 = x1*y2 - x2*y1
//若为正数则v1在v2的顺时针方向 按照右手螺旋法则从v2到v1旋转时 大拇指与z轴反方向一致(向下)
//若为负数则v1在v2的逆时针方向 按照右手螺旋法则从v2到v1旋转时 大拇指与z轴正方向一致(向上)
//若为0则v1和v2共线 此为边界情况
//在两连续线段p0_p1 p1_p2中 考察角<p0p1p2是左转还是右转
//即计算向量p0->p2在p0->p1的顺时针方向还是逆时针方向 可以通过计算p0->p2 cross p0->p1
//在向量a->b中 a是向量起点 b是向量终点
//若为正则p0->p2在p0->p1的顺时针方向 角右转
//若为负则p0->p2在p0->p1的逆时针方向 角左转
//若为0则p0 p1 p2三点共享
//这里需要注意叉积的正负值与向量间顺时针逆时针的关系 实际运算时很容易搞混
//
//本节引用了"数学复习全书(2013年李永乐李正元考研数学 数学一)" 作者"李永乐""李正元"

用冒泡排序对长度为$$ n $$的无序序列$$ s $$进行排序。

#### 解法

//叉积
//cross

//给定两向量v1和v2 求两向量的叉积

//1)向量
//向量v1和v2在立体的三维坐标系中表示为
//v1 = x1*i + y1*j + z1*k
//v2 = x2*i + y2*j + z2*k
//其中i j k是x y z三轴上的单位向量 平面中的向量可以视为z轴为0的三维空间向量
//2)点积
//v1 dot v2 = x1*x2 + y1*y2 + z1*z2
//点积的结果是一个数字
//3)叉积
//v1 cross v2 =	| i   j   k  |
//              | x1  y1  z1 |
//              | x2  y2  z2 |
//叉积的结果是一个向量 此向量遵循右手法则 将右手四指卷起大拇指伸出
//从v1沿着四根卷起的手指指向v2 叉积结果向量与大拇指方向相同 与v1和v2所在平面垂直
//4)行列式计算公式
//| a b c | = 
//| d e f |
//| g h i |
//  a*(-1)^(1+1)*| e f | + b*(-1)^(1+2)*| d f | + c*(-1)^(1+3)*| d e |
//               | h i |                | g i |                | g h |
//
//| a b | = a*d - b*c
//| c d |
//可得三维空间中v1 cross v2 = (y1*z2 - y2*z1)i-(x1*z2 - x2*z1)j+(x1*y2 - x2*y1)k
//二维平面中v1 cross v2 = (x1*y2 - x2*y1)k
//5)向量夹角
//在平面中v1 cross v2 = x1*y2 - x2*y1
//若为正数则v1在v2的顺时针方向 按照右手螺旋法则从v2到v1旋转时 大拇指与z轴反方向一致(向下)
//若为负数则v1在v2的逆时针方向 按照右手螺旋法则从v2到v1旋转时 大拇指与z轴正方向一致(向上)
//若为0则v1和v2共线 此为边界情况
//在两连续线段p0_p1 p1_p2中 考察角<p0p1p2是左转还是右转
//即计算向量p0->p2在p0->p1的顺时针方向还是逆时针方向 可以通过计算p0->p2 cross p0->p1
//在向量a->b中 a是向量起点 b是向量终点
//若为正则p0->p2在p0->p1的顺时针方向 角右转
//若为负则p0->p2在p0->p1的逆时针方向 角左转
//若为0则p0 p1 p2三点共享
//这里需要注意叉积的正负值与向量间顺时针逆时针的关系 实际运算时很容易搞混
//
//本节引用了"数学复习全书(2013年李永乐李正元考研数学 数学一)" 作者"李永乐""李正元"


#include "general_head.h"
#include "geometry.h"

double cross(vec v1, vec v2) 
{//返回二维坐标系中的v1 cross v2
	return(v1.v_x * v2.v_y - v2.v_x * v1.v_y);
}