# java-2
java实验二 计202 宋明扬 2020310606
# 一、实验目的
1.初步了解分析系统需求
<br>2.从学生选课角度了解系统中的实体及其关系，学会定义类中的属性以及方法
<br>3.掌握面向对象的类设计方法（属性、方法）
<br>4.掌握通过构造方法实例化对象；学会使用数组
# 二、业务要求
学校人员分为“教师”和“学生”，教师教授“课程”，学生选择“课程”。每名教师可讲授多门课程，每名学生可选修多门课程。
<br>多门课程，可用课程数组形式表达。
<br>对象：
<br>教师（编号、姓名、性别、所授课程）
<br>学生（编号、姓名、性别、所选课程）
<br>课程（编号、课程名称、上课地点、时间）
# 三、实验要求
1.编写上述实体类以及测试主类
<br>2.在测试主类中，实例化多个类实体，模拟
<br>1）教师开设某课操作；
<br>2）学生选课操作、退课操作
<br>3）打印学生课表信息（包括：编号、课程名称、上课地点、时间、授课教师）
<br>3.编写实验报告。
# 四、解题思路
## **步骤一**：
&emsp;&emsp;**编辑java类：Course，实现对课表的输出，使输出的课表包含课程ID，学生姓名，授课老师，上课地点，上课时间，上课周和学生数量这几个信息。**
## **步骤二**：
&emsp;&emsp;**编辑java类：Teacher，实现对老师进入时所需的功能。
<br>&emsp;&emsp;首先定义老师的类并设置老师的属性；
<br>&emsp;&emsp;再构造函数，然后定义daoru实现对老师课程的导入，定义tea_show实现对输出老师课标的格式的规定。**
## **步骤三**：
&emsp;&emsp;**编辑java类：Student，实现对学生进入时所需的功能。
<br>&emsp;&emsp;首先定义学生的类并设置学生的属性；
<br>&emsp;&emsp;再构造函数，然后定义xuanke实现学生对课程的选择，定义tuike实现学生退课的功能（因不知如何直接删除，选择的方法为创建一个新的数组a，将除删除的课程外的其他课程加入其中，再将数组a重新给stu_cour实现对课程的删除），定义stu_show实现对学生课表的显示。**
## **步骤四**：
&emsp;&emsp;**编辑java类：Simulate，实现对主函数的定义及程序的运行。
<br>&emsp;&emsp;首先将课表导入，并设计开始界面。
<br>&emsp;&emsp;再分别对学生和老师的操作进行设置。**
# 五、关键代码
1. Studengt类里面，xuanke函数实现了学生对课程进行选择，同时避免了学生重复选课。
```java 
void xuanke(int course_id, Course[] stu_c) {
        //输入的课程号与课组里某门课的课号相等，则将该门课添加到学生的个人课程数组里
        for (int a = 0; a < stu_c.length; a++) {
            if (course_id == stu_c[a].id) {
                for (int b=0; b<stu_cour.length; b++){
                    if(stu_cour[0] == null) {
                        stu_cour[i] = stu_c[a];
                        i++;
                        System.out.println("您已成功选上该课程！");
                        break;
                    }
                    if(stu_cour[0] != null){
                        if(course_id == stu_cour[b].id){
                            System.out.println("重复选择，请重新操作！");
                            break;
                        }
                        else{
                            stu_cour[i] = stu_c[a];
                            i++;
                            System.out.println("您已成功选上该课程！");
                            break;
                        }
                    }
                }
                break;
            }
        }
    }
```
2. Student类里面，tuike函数实现了对学生所选课程删除，采用了其他的方法。
```
    void tuike(int id){
        //数组a用来储存学生退课后的课程
        Course[] a = new Course[5];
        //输入的课号与学生个人课组里某门课的课号相等，则将除该门课以外的其他课添加到数组a里，再把数组a又给stu_cour
        for(int i=0, j=0; i<stu_cour.length; i++) {
            //如果学生选的课不足5门，则跳过数组中的空值
            if (stu_cour[i] == null) {
                continue;
            }
            else {
                if (id == stu_cour[i].id) {
                    continue;
                }
                else {
                    a[j] = stu_cour[i];
                    j++;
                }
            }
        }
```
# 六、系统运行截图
&emsp;&emsp;下图是本实验主程序TestBanking.java的运行结果。
<br>![avatar](https://github.com/songmingyang01/java-2/blob/main/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202021-11-22%20092448.png)
<br>![avatar](https://github.com/songmingyang01/java-2/blob/main/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202021-11-22%20092623.png)
<br>![avatar](https://github.com/songmingyang01/java-2/blob/main/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202021-11-22%20092634.png)
# 七、感想与体会
&emsp;&emsp;本次实验是我们的第二次上机实验，第一次自己进行代码的编辑，相对于实验一，难度有了较大的提升，花费了较长的时间才实现对代码的编辑。
<br>&emsp;&emsp;学习中，对程序的设计，代码的编辑，花费了大量的时间，期间自己也遇到了许多问题，但最后通过查阅资料，询问同学，最后都成功的将问题解决。完成本次试验后，我对课堂中学到的知识有了新的理解，运用起来也更加的熟练，使自己的水平有了较大的进步。
