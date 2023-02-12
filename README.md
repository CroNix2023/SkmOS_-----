# SkmOS_一个可以实现计算、查看当前时间的小系统。
# 作者BiliBili:-CroNix-
# https://space.bilibili.com/1175569247 
# 源代码：




------------------------------





import time

localtime = time.asctime()

print(f"""************************************************************
SkmOS系统

系统版本:0.1

你好！很高兴为你服务。

{localtime}
************************************************************""")


def jisuan():
    print("----------\n计算程序")
    print("请选择：1.加法/2.减法/3.乘法/4.除法\n---------")

    ms = input("SkmOS>>>")
    if not ms.isdigit():
        return
    ms = int(ms)
    if ms >= 5 or ms <= 0:
        return

    try:
        num = float(input("计算程序>>>请输入一个数字："))
        num2 = float(input("计算程序>>>请输入另一个数字："))
    except ValueError:
        print("非法输入")
        return

    if ms == 1:
        res = num + num2
    elif ms == 2:
        res = num - num2
    elif ms == 3:
        res = num * num2
    elif ms == 4:
        if not num2:
            print("除数不可为0")
            OS()
            return
        res = num / num2
    print(f"计算程序>>>计算结果：{res}")
    OS()

ml = {"help": "----------\n帮助:\n'system'(查看系统信息)\n'quit'(退出程序)\n'time'(显示当前时间)\n'calc'(计算程序)\n----------"}
ml['system'] = "----------\n系统信息\nSkmOS系统\n系统版本:0.1\n----------"
ml['time'] = f"----------\n当前时间:{localtime}\n----------"



def OS():
    num1 = str(input('SkmOS>>>'))
    if num1 in ml:
        print(ml[num1])
        OS()
    elif num1 == 'quit':
        quit()
    else:
        if num1 == 'calc':
            jisuan()
        else:
            print('Command error!')
            print("(可使用'help'指令获取帮助)")
            OS()
    return


OS()
