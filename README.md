// FGO_yangan
//FGO自动刷低级素材养肝明目狗急跳墙脚本，功能是在想要刷类似世界之树种子之类掉率低但需求量又大的材料时使用。
//功能是在想要刷类似世界之树种子之类掉率低Ap消耗少但需求量又大，刷起来特浪费时间的材料时使用。
//启动方法：在选择任务的界面启动就行，自动选择第一个任务。
//以下直接就是按键精灵脚本了，有识之士要是有空的话还请帮我优化一下……
//启动FGO养肝程序 狗急跳墙v0.2版
//本脚本仅适用于在Start BlueStacks模拟器下使用安卓版按键精灵助手，分辨率1440*900的情况下使用，没有兼容打算。
//请在选择副本界面启动脚本
ShowMessage "启动FGO养肝程序"
Dim intX, intY ,pass
pass=0
While true
pass=pass+1
If pass>20 Then
ShowMessage "尝试失败次数过多，直接选择卡片"
	Tap 150, 595
	Delay 510
	Tap 443, 595
	Delay 410
	Tap 726, 595
	Delay 460
	Tap 1006, 595
	Delay 460
	//选三张卡
	Tap 1072,757
	Delay 460 
	//防错按，点一下材料确认画面上的位置
	Tap 1193,190
	//防错按，点一下宝具画面的关闭按钮
pass=0
End If
Delay 1000
ShowMessage "寻找白框标志进入战斗,pass="&pass
FindColor 65,58,86,78,"D6D5D5",0,0.9,intX,intY
If intX > -1 And intY > -1 Then 
Delay 2000
FindColor 1369, 183, 1399, 211, "FFFFFF", 0, 1, intX, intY
If intX > -1 And intY > -1 Then 
ShowMessage "再次确认已经找到get标志进入战斗"
Delay 2000
FindColor 65,58,86,78,"D6D5D5",0,0.9,intX,intY
If intX > -1 And intY > -1 Then 
ShowMessage "第3次确认找到白框标志进入战斗"
pass=0
	//点击第一个任务上的get标志，如果想要打其他副本的话请自己改坐标
	Tap 1102, 246
ShowMessage "点击get标志"	
	Delay 3000
	Tap 788, 328
ShowMessage "点击好友"
	Delay 3000
	Tap 1341, 783
ShowMessage "点击开始"
	Delay 5000
End If
End If
End If
Delay 1000
//第一段
//第二段找寻attack标志
ShowMessage "寻找attack标志"
FindColor 1200,729,1364,742,"EDD500",0,0.9,intX,intY
//如果没有找到，intX和intY的值都会被置为-1
If intX > -1 And intY > -1 Then 
Delay 500
FindColor 1200, 636, 1364, 742, "EDD500", 0, 0.9, intX, intY
If intX > -1 And intY > -1 Then 
ShowMessage "再次确认找到attack标志"
pass=0
	Delay 1500
	Tap 1234, 739
	Delay 1500
	//找到，点击
	//有宝具放宝具
	Tap 150, 260
	Delay 100
	Tap 440, 260
	Delay 100
	Tap 740, 260
	Delay 100
	Tap 1000, 260
	Delay 100
	Tap 1300, 260
	Delay 100
	//选择一般卡
	Tap 150, 595
	Delay 510
	Tap 443, 595
	Delay 410
	Tap 726, 595
	Delay 460
	Tap 1006, 595
	Delay 460
End If
End If
//战斗结束
FindColor 89,213,127,253,"25BCE8",0,0.98,intX,intY
If intX > -1 And intY > -1 Then 
ShowMessage "发现战斗结束"
Delay 200
FindColor 546,108,601,166,"FFFFF8",0,0.98,intX,intY
If intX > -1 And intY > -1 Then 
ShowMessage "再次确认战斗结束"
Delay 200
FindColor 126,485,165,528,"590000",0,0.98,intX,intY
If intX > -1 And intY > -1 Then 
ShowMessage "第三次确认战斗结束"
pass=0
	Delay 3000
	Tap 150, 595
ShowMessage "点击确认战斗结束"	
	Delay 5000
	Tap 150, 595
ShowMessage "点击确认经验"	
	Delay 5000
	Tap 1255, 767
ShowMessage "点击确认掉落"	
	Delay 5000	
End If
End If
End If

Wend
