## 一、基本概念介绍
### 1、什么是屏幕像素密度（dpi）
	屏幕像素密度（dpi-->dots per inch）就是指每一英寸长度中，可显示输出的像素个数
	
	屏幕分辨率：1920*1080   屏幕尺寸：6寸
	计算公式：（1920和1080的平方和）再开平方，再除以6
### 2、px、dip、dp是什么？与dpi有什么关系
	px：构成图像的最小单位，也是屏幕分辨率的单位
	dip：Desity Independent pixels的缩写,即密度无关像素
	dp：等同于dip，类似简写
	
	与dpi的关系：
	1、Android内部在识别图像像素时，有一个基准，即当手机的dpi为160dpi时，在布局中使用的1dp就等价于1px
	2、Android会根据设备的dpi与160dpi的比例关系，去换算翻译布局中dp跟px之间的对应关系
	
### 3、mdpi,hdpi,xdpi,xxdpi,xxxdpi?如何计算和区分?

	名称                  像素密度范围         图片大小
	mdpi                 120dp~160dp         48×48px
	hdpi                 160dp~240dp         72×72px
	xhdpi                240dp~320dp         96×96px
	xxhdpi               320dp~480dp         144×144px
	xxxhdpi              480dp~640dp         192×192px

在Google官方开发文档中，说明了 **mdpi：hdpi：xhdpi：xxhdpi：xxxhdpi=2：3：4：6：8** 的尺寸比例进行缩放
## 二、几种屏幕适配处理方式
### 1、尽量使用"wrap_content"和"match_parent","weight"
### 2、使用相对布局RelativeLayout
### 3、使用.9图
### 4、限定符
1、限定符分类：
>屏幕尺寸    
>>small   小屏幕   
>>normal  基准屏幕   
>>large   大屏幕   
>>xlarge  超大屏幕

>屏幕密度
>>ldpi    <= 120dpi   
>>mdpi    <= 160dpi   
>>hdpi    <= 240dpi    
>>xhdpi   <= 320dpi   
>>xxhdpi  <= 480dpi   
>>xxxhdpi  <= 640dpi(一般只用来存放icon)   
>>nodpi   与屏幕密度无关的资源.系统不会针对屏幕密度对其中资源进行压缩或者拉伸   
>>tvdpi   介于mdpi与hdpi之间,特定针对213dpi,专门为电视准备的,手机应用开发不需要关心这个密度值.     

>屏幕方向    
>>land    横向   
>>port    纵向

>屏幕宽高比   
>>long    比标准屏幕宽高比明显的高或者宽的这样屏幕   
>>notlong 和标准屏幕配置一样的屏幕宽高比

## 三、两种常用的解决方案
### 1、通过自定义布局组件来完成
	核心原理是根据一个参照分辨率进行布局，然后在代码中提取当前机器的分辨率，通过比例换算得出比例系数，再通过重新测量的方式来达到适配的效果

### 2、
