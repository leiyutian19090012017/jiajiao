# jiajiao
给你两个数 hour 和 minutes 。请你返回在时钟上，由给定时间的时针和分针组成的较小角的角度（60 单位制）。

 

示例 1：

输入：hour = 12, minutes = 30
输出：165

示例 2：

输入：hour = 3, minutes = 30
输出；75

示例 3：

输入：hour = 3, minutes = 15
输出：7.5

示例 4：

输入：hour = 4, minutes = 50
输出：155

示例 5：

输入：hour = 12, minutes = 0
输出：0

 

提示：

    1 <= hour <= 12
    0 <= minutes <= 59
    与标准答案误差在 10^-5 以内的结果都被视为正确结果。
class Solution {
public:
    double angleClock(int hour, int minutes) {
        double h=(double)hour+(double)minutes/60;
        if(h>12)h=h-12;
        double an1=h/12*360;
        double an2=(double)minutes/60*360;
        double ang;
        if(an2-an1>0){
            ang=an2-an1;
        }
        else{
            ang=an1-an2;
        }
        if(ang>180){
            ang=360-ang;
        }
        return ang;
    }
};

