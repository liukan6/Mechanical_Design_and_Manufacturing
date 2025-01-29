# Screw Jack Design

## Overview

### Working Principle and Design Parameters

The screw jack works by reciprocating the handle, which rotates a rod to drive the nut, causing the lifting screw to rotate and raise or lower the lifting cup, thus achieving the lifting and pulling force. The jack uses a screw transmission to convert the rotational motion of the screw into linear motion, while also transmitting motion and power. The screw transmission has advantages such as a large transmission ratio, self-locking ability, compact structure, and high precision.

| Design Parameter              | 数值 [单位] |
| ----------------------------- | ----------- |
| Maximum Lifting Capacity$Q$ | 20 [kN]     |
| Maximum Lifting Distance$h$ | 120 [mm]    |

The material selection and design of the jack need to meet functional requirements, economic considerations, and durability and reliability requirements.

### Design Proposal (Simplified Diagram)

#### Proposal 1: Vertical Screw Jack

As shown in the figure, the handle can slide to adjust the lever arm length. Turning the handle raises the screw, thus lifting the heavy object.

<div>			<!--块级封装-->
    <center>	<!--将图片和文字居中-->
    <img src="image/1.png"
         alt="无法显示图片时显示的文字"
         style="zoom:0.8"/>
    <br>		<!--换行-->
    Figure 1: Vertical Screw Jack Schematic	<!--标题-->
    </center>
</div>

#### Proposal 2: Scissors Screw Jack

As shown in the figure, the screw rotates in opposite directions on both sides, and turning the handle causes the two nuts to move in opposite directions, lifting or lowering the object.

<div>			<!--块级封装-->
    <center>	<!--将图片和文字居中-->
    <img src="image/2.png"
         alt="无法显示图片时显示的文字"
         style="zoom:这里写图片的缩放百分比"/>
    <br>		<!--换行-->
    Figure 2: Scissors Screw Jack Schematic	<!--标题-->
    </center>
</div>

We will use Proposal 1 as an example for the design calculations.

## Design and Calculation of the Screw

### Selection of Screw Thread Type

Based on the relationship between the screw and the nut's movement, the nut is fixed in the jack, and the screw rotates and moves. It serves as a power transmission screw. For this design, a **single-thread screw** (GB5796-86) is chosen. The commonly used thread type is  **right-hand thread** , and for sliding screw transmissions, trapezoidal and sawtooth threads are commonly used. Since the trapezoidal thread has a good fit between the inner and outer threads and has a high root strength, we choose a **trapezoidal thread** for calculation, with the tooth profile being an isosceles trapezoid and the thread angle $\alpha=30^\circ$。

### Material Selection for the Screw

Common materials for the screw include $Q235$, $Q275$, $45$, and $50$ steel. For parts that require high wear resistance, materials such as $T12$, $65Mn$, $40Cr$, and $18CrMnTi$ are used. Since the jack operates at low speed, with only moderate stress on each surface, and considering the overall economic factors, **45 steel** is chosen. According to the national standard "High-Quality Carbon Structural Steel" (GB/T699-2015), the tensile strength of $45$ steel is $\sigma_b = 600$ MPa, $\sigma_s = 355$ MPa, and the elastic modulus $E = 2.06 \times 10^5$ MPa.

### Determining the Thread Diameter

The contact pressure $p$ of the thread surface needs to be limited to below the permissible pressure of the screw pair $[p]$, i.e.

$$
p  =\frac{Q}{\pi d_2 h Z}=\frac{QP}{\pi d_2 h H}\leq[p]
$$

Where $Q$ is the axial load, $d_2$ is the thread middle diameter, $H$ is the nut height, $P$ is the pitch, and $h$ is the thread contact height. Therefore, we have

$$
d_2\geq\sqrt{\frac{Q}{\pi\varphi\psi[p]}}
$$

where $\psi = \frac{H}{d_2}$ represents the ratio of nut height to middle diameter, and $\varphi = \frac{h}{P}$ represents the ratio of thread contact height to pitch. For trapezoidal threads, $\varphi = 0.5$, and since the nut is an integral nut, $\psi$ is generally between 1.2 and 2.5. In this case, we take $\psi = 1.8$.

此处螺旋传动副的螺杆—螺母材料选择钢对青铜，考虑螺旋千斤顶的工作条件为低速、人力传动，许用压强$[p]=18\sim25MPa$，此处取中间值$[p]=20MPa$。 根据 1.1 中的载荷要求，载荷力为$Q=20kN$，代入计算得

$$
d_2\geq18.81mm
$$

根据国家标准《梯形螺纹 第 2 部分：直径与螺距系列》(GB/T 5796.2-2022)，优先选用第一系列，公称直径取 $d=28mm$。 根据《梯形螺纹 第 3 部分：基本尺寸》(GB/T 5796.3-2022)，螺纹中径为 $d_2=25.500mm$，螺距为 $P=5mm$，计算得螺母高度为 $H=\psi d_2=45.9mm$。考虑到螺纹间载荷实际分布不均匀，螺母螺纹圈数$Z$不应超过10，否则需要更换材料或增大直径，验算得$Z=\frac{H}{P}=9.18<10$，**满足要求**。

此时表面工作压力

$$
p=\frac{Q}{\pi d_2 \varphi H}=10.88MPa<[p]=20MPa
$$

**满足要求**。单线螺纹导程 $S=P=5mm$，亦可以计算出螺纹牙根部宽度 $b=0.65P=3.25mm$ 和螺纹升角 $\lambda=\arctan\frac{S}{\pi d_2}=3.571^\circ$。

此时有

| 公称直径 [mm] | 螺距 [mm] | 内/外螺纹中径$d_2=D_2$[mm] | 内螺纹大径$D_4$ [mm] | 外螺纹小径$d_3$[mm] | 内螺纹小径$D_1$[mm] | 螺纹牙根部宽度$b$ [mm] | 螺纹升角$\lambda$ | 牙形角$\alpha$ |
| ------------- | --------- | ---------------------------- | ---------------------- | --------------------- | --------------------- | ------------------------ | ------------------- | ---------------- |
| 28            | 5         | 25.500                       | 28.500                 | 22.500                | 23.000                | 3.25                     | 3.571°             | 30°             |

---

### 自锁验算

钢对青铜的摩擦系数 $\mu = 0.08 \sim 0.10$，取小值 $\mu = 0.08$，梯形螺纹的牙形角 $\alpha = 30^\circ$。

$$
\varphi_v=\arctan\frac{\mu}{\cos\beta}=\arctan\frac{\mu}{\cos\frac{\alpha}{2}}=4.735^\circ\\
\lambda=3.571^\circ<\varphi_v
$$

故螺旋副**满足自锁条件**。

### 螺杆结构设计

螺杆上端用于支承托杯$10$并在其中插装手柄$ 7$，因此需要加大直径。暂取 $D_S=2d = 56mm$，膨大部分长度取 $l_s = 1.5d=42mm$。

手柄孔径 $d_k$ 的大小根据手柄直径$d_p$决定，$d_k \approx d_p + (0.5 \sim 1)mm$ ，取 $d_k = 22.5mm$ 。

为了便于切制螺纹，螺纹上端应设有退刀槽。退刀槽的直径 $d_c$ 应比螺杆小径 $D_1$ 约小 $0.2 \sim 0.5mm$ 。退刀槽的宽度可取为 $l_c = 1.5P \approx 8mm$ ，退刀槽直径 $d_c = 22mm$。

为了便于螺杆旋入螺母，螺杆下端应有倒角，在设计中倒角统一取$c2$。

考虑千斤顶最大升程、退刀槽宽度、真实螺母高度（在 3.2 中计算），螺杆等效长度

$$
l_B =h+l_c+H'= 178mm
$$

### 螺杆强度校核

受力较大的螺杆需要用第四强度理论进行强度计算，螺杆工作时承受轴向压力 $Q$ 和扭矩 $T$ 的作用，螺杆危险截面上既有压缩应力，又有切应力。螺杆受到的扭矩

$$
T = \frac{Qd_2\tan(\psi+\varphi_v)}{2}=29.21N\cdot m
$$

螺杆材料为$ 45 $号钢，安全系数为 $3\sim5$，取最大值$5$，许用应力 $[\sigma]= \sigma_s/5=71MPa$ ,

$$
\sigma = \sqrt{\sigma^2+3\tau^2}=\sqrt{\left(\frac{Q}{A}\right)^2 + 3\left(\frac{T}{W_T}\right)^2}
$$

其中，对于圆柱体螺杆$A=\frac{\pi d_3^2}{4}$,$W_T=\frac{\pi d_3^3}{16}=A\frac{d_3}{4}$。螺杆的内螺纹小径 $d_3 = 22.500mm$，代入计算得到 $\sigma = 55.15MPa<[\sigma]=71MPa$ ，故该螺杆**满足强度要求**。

### 稳定性校核

对于长径比大的受压螺杆，当轴向负载 $Q$ 大于某一临界值时，螺杆就会突然发生侧曲而丧失其稳定性，存在临界载荷$Q_c$，螺杆的稳定性条件

$$
\frac{Q_c}{Q}\geq S_s
$$

其中$S_s$为保证螺杆不失稳的最小安全系数，对于传力螺旋传动$S_s=3.5\sim 5.0$，取最大值$S_s=5$。根据材料力学，失稳时的临界载荷$Q$与螺杆的柔度$\lambda_s = \frac{\mu l}{i}$的值有关，式中$l$为螺杆承受压力的一段长度，$i$为螺杆危险截面的惯性半径，若危险截面可近似看做是直径为$d_3$（螺纹小径）的圆，则$i=\frac{d_3}{4}$，单位均为$mm$，$\mu$为螺杆的长度系数，对于螺旋千斤顶可视为一端固定一端自由，取$\mu=2$。

$$
\lambda_s = \frac{\mu l_B}{i}=63.29>40
$$

需要进行稳定性校核。当$40<\lambda_s<100$时，对于优质碳素钢，取

$$
Q_c = (461-2.568\lambda_s)\frac{\pi d_3^2}{4}=118.67kN
$$

$$
\frac{Q_c}{Q} =5.934>S_s=5
$$

故该螺杆**满足稳定性条件**。

### 挡圈设计

为了防止工作时螺杆从螺母中脱出，在螺杆下端必须安置钢制挡圈 (GB/T 891-1986)，挡圈用十字槽沉头螺钉 (GB/T 819.1-2016) 固定在螺杆端部。

由 GB891-86 查得，对于公称直径 $d = 28$ mm 的螺钉紧固轴端挡圈应选用的挡圈公称直径为 $D = 35 mm$，$H = 5 mm$，$L = 10 mm$，小径 $d = 6.6 mm$，$d_1 = 3.2mm$，$D_1 = 13mm$，$c = 1mm$，螺钉 $M6 \times 16$。

## 螺母设计与计算

### 螺母材料选取与结构设计

螺母的材料除了足够的强度，还需要与螺杆材料配合时摩擦系数小并耐磨。为适应重载低速传动，这里选用铸造铝青铜$\text{ZQAl9-4-4-2}$ ，查询得许用切应力 $[\tau] = 30\sim40MPa$ ，许用弯曲应力 $[\sigma_b] = 40\sim60MPa$。

### 确定螺纹旋合圈数与螺母高度

螺母高度 $H =\psi d_2= 45.9mm$，螺纹工作圈数

$$
u=\frac{H}{P}=9.18
$$

考虑退刀槽的影响面设计螺母圈数（取整数）

$$
u'=u+1=10.18\approx10
$$

此时螺母的实际高度

$$
H'=u'P=50mm
$$

### 螺母螺牙强度校核

螺纹牙多发生剪切和挤压破坏，一般螺母的强度低于螺杆，故只需要校核螺母螺纹牙强度。

螺纹牙危险截面的剪切强度条件

$$
\tau = \frac{Q}{\pi D_4 b u'}\leq[\tau]
$$

螺纹牙危险界面弯曲强度条件

$$
\sigma = \frac{6Ql}{\pi D_4 b^2 u'}\leq[\sigma_b]
$$

其中b为螺纹牙根部的厚度，对于梯形螺纹，$b = 0.65P = 3.25mm$，$l$ 为弯曲力臂，$ l = \frac{D-D_2}{2} =1.5mm$，内螺纹大径$D_4=28.5mm$。对于青铜材料，许用切应力 $[ \tau ] = 30\sim40MPa$，许用弯曲应力 $[ \sigma_b ] = 40\sim60MPa$，这里取小值，$ [ \tau ] = 30 \text{ MPa} $，$[\sigma_b]=40MPa$。代入数据计算

$$
\tau=\frac{Q}{\pi D_4 b u'}=6.87MPa\leq[\tau]\\
\sigma=\frac{6Ql}{\pi D_4 b^2u'}=19.03MPa\leq[\sigma_b]
$$

故螺母螺纹牙**满足强度要求**。

### 螺母外部尺寸设计与校核

取螺母外径 $D_N = 50mm\approx1.8d$，螺母凸缘直径 $D_{N1}=65mm=1.3D_N$，螺母凸缘厚度 $a=22mm=0.4H'$。

#### 拉扭组合校核

螺母凸缘处受拉、扭组合作用，需要进行强度校核，由于数据信息少，扭转力矩大小难以精确计算，估算拉应力约为 $F = 35kN\cdot m\approx1.3Q$,

$$
\sigma'=\frac{F}{0.25\pi(D_N^2-d^2)}<[\sigma]
$$

取许用拉应力 $[ \sigma ] = 40\text{MPa}$，计算得到

$$
\sigma' = 19.29 \text{ MPa} < [ \sigma ] = 40 \text{ MPa}
$$

，

**满足强度要求**

。

#### 凸缘与底座挤压校核

凸缘与底座接触部分存在挤压，需要进行挤压强度计算，

$$
\sigma_p=\frac{Q}{0.25\pi(D_{N1}^2-D_N^2)}<[\sigma_p]
$$

取许用挤压应力 $[ \sigma_p ] = 75\text{MPa}$，计算得到

$$
\sigma_p' = 19.19 \text{ MPa} < [ \sigma_p ] = 75 \text{ MPa}
$$

，故可以认为/

**满足挤压强度要求**

。

#### 凸缘根部强度计算

凸缘根部需要进行弯曲强度计算，

$$
\sigma_b=\frac{Q(D_{N1}-D_N)}{\pi D_Na^2}<[\sigma_b]
$$

代入计算$\sigma_b'=3.95\text{MPa}<[\sigma_b]$，**满足弯曲强度要求**。

根据 $\text{GB/T 77-2007}$，这里使用内六角平端紧定螺钉 $\text{M12}$。

## 托杯设计与计算

### 托杯材料选择与结构设计

托杯用于承托重物，可以用$\text{ Q235}$ 钢模锻制成，材料为$\text{ Q235}$。其结构尺寸见图。为了与重物接触良好并防止相对滑动，在杯托上表面制有切口的沟纹。为了防止杯托从螺杆端部脱落，在螺杆上端装有挡板。

### 托杯尺寸设计与强度校核

当螺杆转动时，杯托和重物不作相对转动。因此在起重时，杯托底部与螺杆和接触面有相对滑动。为了避免过快磨损，一方面需要润滑，另一方面还需要验算接触面间的压力强度。

$$
p=\frac{Q}{\frac{\pi}{4}(D_S'^2-D_S''^2)}\leq[p]
$$

其中，$[ p ]$ 为许用压强，应为杯托与螺杆材料许用压强的较小值，查表知$\text{Q235}$的许用压强较小，取 $[ p ] =[p]_\text{杯} =225$ MPa。

取杯托外径$D_S=58mm$，杯托直径$D_S'=D_S-(2\sim4)$，取$D_S'=54mm$，直径$D_S''=d+(1\sim2)$，取$D_S''=30mm$，代入公式

$$
p=\frac{Q}{\frac{\pi}{4}(D_S'^2-D_S''^2)}=12.63MPa\leq[p]=225MPa
$$

**满足强度要求**。

杯托外口径$D_3=70\approx2.5dmm$。杯托厚度取$\delta=8mm$，杯底厚度为$\delta_b\approx1.5\delta=10mm$，沟纹宽度为$1.5\delta=12mm$，沟纹深度为$\delta_d=\delta/2=6mm$，杯托高度为$h_c\approx2d=60mm$，为保证杯托可以转动，螺杆顶部的垫片和杯托底部留有间隙，间隙值为$3\sim4mm$，因承受力不大，故取值为$3mm$。

## 手柄设计与计算

### 手柄材料选择与结构设计

手柄的材料选择为常用的 45 号钢。其许用应力常取为 $[\sigma] = 160MPa$。将手柄插入螺杆上部的孔中，为防止手柄从孔中滑出，在手柄两端应加上手把，并用螺钉固定。

### 确定手柄长度

手柄上的工作转矩包括螺纹副摩擦力矩与接触面摩擦力矩

$$
T=F_HL_H=T_1+T_2
$$

螺旋副间的摩擦阻力矩

$$
T_1 =Q\tan(\psi+\rho_v) \frac{d_2}{2}
$$

杯托与轴端支承面的摩擦力矩

$$
T_2 =Q\cdot \frac{1}{3}f_c \frac{D_0^3-d_0^3}{D_0^2-d_0^2}
$$

取 $D_0=D_s'=54mm$,$d_0=D_s''=30mm$，人手的最大操作力 $F_H = 300N$，给出$f_c=0.12$，代入可求得$T_1=29.21N$，$T_2=51.77N$手柄的有效长度

$$
L_H=269.9mm
$$

取手柄长度为 $L_H = 271 mm$，该距离为螺杆中心到人手施力点的距离，考虑螺杆头部尺寸和人工握手距离，适当增加手柄实际长度。

$$
L_H'=L_H+\frac{D_S}{2}+50mm=350mm
$$

### 确定手柄直径

Q235 的许用应力 $[\sigma] = 160$ MPa，可将手柄看作一个悬臂梁，按照弯曲强度确定手柄直径,

$$
\sigma_b=\frac{F_HL_H}{W}=\frac{F_HL_H}{\frac{\pi}{32}d_k^3}\leq[\sigma_b]
$$

计算得到

$$
d_p\geq \sqrt[3]{\frac{32F_HL_H}{\pi[\sigma_b]}}=17.28mm
$$

可适当取大，取 $d_p = 22 mm$。

## 底座设计

底座材料常用铸铁$ HT150 $及$ HT200$，选用$ HT150$。铸件的壁厚取 $\delta = 10mm$，为防止裂纹和缩孔，对所有小于$120^\circ$的角取圆角$R2$。为了增加底座的稳定性，底部尺寸应大些，因此将其外形制成约$ 1:5 $的斜度。

底座高度考虑螺母高度，推程和一定的距离裕度，取$H = 180mm$，底座与螺母相套处直径为

$$
D_{B1} = D_N = 50 \text{mm}
$$

按照斜度计算底座斜段下方直径：

$$
D_{B2} = D_{B1 }+ \frac{1}{5}(H-H_2) =102 \text{mm}
$$

应按照挤压强度计算底座最大尺寸$D_{B3}$，其中灰铸铁和混凝土的许用挤压应力 $[\sigma_p] = 4.5MPa$

$$
\sigma_p=\frac{Q}{\frac{\pi}{4}(D_{B3}^2-D_{B2}^2)}\geq[\sigma_p]\\
D_{B3}\geq\sqrt{\frac{4Q}{\pi[\sigma_p]}+D_{B2}^2}=126.7mm
$$

适当取大，取底座最大尺寸 $d_{B3}=150mm$。

## 装配图绘制

见附页。

## 参考资料

1. 陈秀宁, 顾大强. 机械设计[M]. 第3版. 杭州: 浙江大学出版社，2018.
2. 刘鸿文, 材料力学$\text{I}$[M]. 第6版. 北京: 高等教育出版社, 2017: 316.

部分资料来源网络和机械设计有关国家标准。
