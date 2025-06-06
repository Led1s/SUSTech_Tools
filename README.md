# 南科大Tis选课助手  
**2024 Sep 更新：Tis 后台在用户级别做了流量限制**   
每个有效请求触发新的限制，因此大量发送数据不一定再是最优选择  
因此当前版本同时只选一门课（最重要的），选课队列优先级请参考使用说明  
**该程序未对流量特征做任何的混淆，追求隐蔽性请自行修改** (UA，请求参数，其他流量等)

> 维护者不一定会在每学期开学前检查脚本有效性，欢迎有兴趣的同学提前几天测试脚本（以避免 TIS 偷偷修改接口导致脚本失效）  

如遇到学期服务器证书配置出错，兼容修改请参照issue手动修复  
如遇CAS不明原因500，请**提前多次尝试登录**  

## 使用说明  
- main.py为Python3编写的主程序，运行即可  
- class.txt为需要选择的课程列表，一行一个数据，因编码问题，第一行请留空或不要编辑。  
**选课顺序会严格按照class.txt中录入的先后顺序进行，在高优先级课程被选完/冲突前不会选低优先级课程，除非手动输入任意值字符回车跳过**  
- 按下回车之后会进入一个3s的循环，每秒选当前最优先的课程一次。（可以按多次开启多个计时循环）
课程列表添加说明（图片加载不出请科学加载）：  
![课程名称说明](screenShots/help.png)  
  脚本运行界面：
![脚本运行界面](screenShots/sc.png)

## 更新
最后一次**检测可用**是2024-09-05，检测结果是 **可用**  
- 如果您本地有Python3.6+环境并希望手动运行/修改代码[访问源代码](https://github.com/GhostFrankWu/SUSTech_Tools/blob/master/main.py)  
- 如果您本地没有Python环境，您可以[使用windows打包版](https://github.com/GhostFrankWu/SUSTech_Tools/releases/tag/v5.1.0)  

## 免责声明

该脚本诞生的目的是研究节省流量，减轻选课系统负担的方法，经过测试确实能达到该效果，因人为修改脚本产生的超过手工频率的流量，由修改者承担责任  
>虽然Tis经过若干更新，网页端选课产生的流量已经大大减少，但该脚本仍产生更少的流量

<!--
### 免责声明
该脚本是通过抽象人对计算机的操作方法，提供节省流量并方便选课的功能。脚本为非营利性开源脚本，仅供个人学习、研究或欣赏使用，采用MIT协议，不具有任何市场价值。开发和使用过程不涉及对任何系统进行逆向破解/反汇编/反编译，本脚本编写使用的一切数据都来源于公开在互联网上的内容。  
本脚本不提供任何明示或暗示的保证，包括但不限于对适销性和特定用途的适用性的暗示保证。 在任何情况下，版权所有人或贡献者均不对任何直接，间接，偶发，特殊，示范性或后果性的损害负责。  
本脚本仅限用于合理合法的学习用途如网络环境测试，因本脚本而产生的各种后果由使用者自行承担，作者对此不负任何责任。  


>## TL;DR
>有人要向老师举报："是脚本导致了教务系统瘫痪"。  
>经过测试，学生正常使用TIS选课和使用脚本选课的请求情况如下表所示  
>
>项目（三次取平均） | 请求总数(个) | 流量总计(kB) | 总用时(ms)  
>-- | -- | -- | --
>TIS登录 | 17 | 188 | 680
>脚本登录 | 0 | 0 | 0
>TIS登录CAS认证 | 22 | 745 | 1410
>脚本登录CAS认证 | 1 | 11 | 96
>TIS进入 | 141 | 2487 | 8760
>脚本进入 | 4 | 223 | 692
>TIS选课+刷新 | 119 | 1299 | 取决于查询内容1-10秒不等
>脚本选课 | 1 | 0.6 | 177
>TIS总计（刷新n次） | 180+119n | 3350+1299n | 10秒+每次刷新耗时
>脚本总计（选课m次） | 5+m | 234+0.6m | 0.8秒+每次请求144ms
>
>可见在目前的TIS设计下，脚本一秒发送100次请求都不及一位正常学生刷新页面看选课按钮有没有激活产生的请求/流量多。  
>- 所以如果TIS崩了，那最不应该指责是就是如此节省流量脚本用户了（吧？）  
>  
>本人寄网挂科水平，欢迎大佬对以上论述批评指正。

-->
