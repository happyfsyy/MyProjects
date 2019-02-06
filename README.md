### Alarm
---
做一个闹钟的小项目，模仿iphone的闹钟界面，暂不采用Android X，继续使用support-v4包和v7包。  
需要的几个界面如下：  
1、主界面，显示所有闹钟的列表，采用RecyclerView实现。  
2、主界面每个item点击，可以进入闹钟的编辑界面，可以重新设置闹钟的时间。  
3、闹钟时间到了，响铃的界面，transparent，显示手机壁纸。  
具体思路如下：  
难点，一个是在于闹钟的“编辑”界面，那个滑轮，我准备自己自定义，不过可以先用TimePicker，之后再采用自定义WheelView。还有一个是具体的闹钟思路。  
闹钟功能的实现，首先，退出程序之后，闹钟肯定是可以继续使用的，肯定是要采用Service的。  
定时功能，采用AlarmManager。需不需要采用广播呢？简单的，到时，直接binder.start()方法内部开始pendingIntent到另一个闹钟Activity，播放音乐。  
或者，binder.start()中是发送广播，在广播里，再去进行startActivity()。  
