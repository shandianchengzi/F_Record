# F_Record
一款用来录制绘画过程的轻量级PS插件。  
插件原理：调用PS生成器的接口，当画布发生变化时截取过程图片，最后将图片连起来生成录像。  
支持版本：PS 2019及以后（感谢srylyx帮忙兼容）  
支持系统：Windows、Mac（github上暂时只放了Windows）  
Github：https://github.com/F-know/F_Record  
网盘下载：https://pan.quark.cn/s/d3aaf46abc5e  
免责声明：该插件不保证能让任何电脑都能完美运行不出bug，所以对于重要的录制过程请做好Plan B，否则造成的损失我不负责哦，毕竟是免费的。看完下面所有内容还有问题可以来b站（id：F_know）私信我，看到后会回复。  
PS插件开发博客：https://uiscripting.com  这个插件的所有内容都是我跟着这位大佬写的博客一步步完成的，耗时一周。  
## 安装方法
如果之前安装了1.0版本的请先把1.0删掉。同一个绘画过程不要两个版本各录一部分。  
下面这些路径PS没有自带的话就自己新建一个出来就行。  
### win
将F_Record-CEP放在/Adobe Photoshop/Required/CEP/extensions中  
将F_Record-generator放在/Adobe Photoshop/Plug-ins/Generator中  
### mac
将F_Record-CEP放在/Users/{用户名}/Library/Application Support/Adobe/CEP/extensions中  
将F_Record-generator放在/Adobe Photoshop/Plug-ins/Generator中  
  
最后打开PS，编辑-首选项-增效工具-启用生成器（勾上）、载入扩展面板（勾上），重启PS，在最上面一栏的 窗口-扩展 就能找到插件了。  
## 插件界面的参数介绍
路径：这里填保存过程图片和输出录像的路径，不是插件安装的位置。随便在哪儿新建一个文件夹，把路径复制进去就行。  
已保存图片数：已保存的过程图片数量。开始录制后会随着操作进行逐渐增加。  
最小保存间隔：用来控制保存图片的频率，通常设为0就行。如果画布较大（如5000*5000像素以上，当然也看你电脑性能），保存图片的用时较长，相当于最小保存间隔会比较大。  
录像时长：用来控制最后输出的录像的时间，可以录制好后再填写，建议5分钟以内，与生成录像花费的时间正相关（当然你不介意多等一会儿也行）。  
## 常见问题
问：插件提示未经正确签署？  
答：里面有文件被修改或者损坏了，先重新下载试试，还是不行可以百度一下，网上有许多解决办法。  
问：按照上面的教程安装，插件没在扩展中找到？  
答：大概率是F_Record-CEP文件夹位置没放对。  
问：点开始录制后提示“没有找到这个路径”？  
答：填的路径信息别带引号哦。  
问：开始录制后图片数一直是零？  
答：要不然是F_Record-generator文件夹位置没放对，要不然是画布开太大了，它保存得很慢。  
问：关掉PS后下次还能继续录制吗？  
答：能，记得点一下继续录制。  
问：录到一半不想画这幅画了，想换一幅画录，该怎么办？  
答：再新建一个文件夹，用新的路径就行，以后想画了可以再换回来。  
问：录制过程中画布被裁剪或者扩张会影响录像吗？  
答：录像会自行调整。  
问：缩放、翻转、旋转画布会被记录进录像吗？  
答：只要改变的仅仅是画布的视图而不是画布本身，就不会被记录。  
问：有多张画布时录制的是哪一张？  
答：点开始录制时选中的那一张。  
问：输出录像的耗时跟什么有关？  
答：主要取决于你设置的录像时长，然后跟图片数也有点关系，但跟画布尺寸无关。  
问：输出录像为什么一直卡在0%？  
答：可能是录像时长设置得太长了。或者是图片数太少了，多等一会儿它就会直接跳到90%。  
问：输出录像到一半出现undefined错误？  
答：要不然是你用的第一版并且画布开的很大，这种情况只能把图片放PR之类的剪辑软件里面去导出视频了，要不然是你的过程图片中有损坏的图片，比如某张图片保存到一半的时候你把PS关了（我推测的），这种情况找到损坏的图片删掉就行。  
## 暂时没解决的问题
问：F_Record和其它某些插件同时使用时不兼容？  
答：由于我用的其它PS插件很少，暂时不知道是什么原因。  
问：插件打开后闪了一下就没了？  
答：目前反应这个问题的好像都是个别2019版本的，我也不知道为啥，但评论区有人说重下了一个PS就解决了。  
问：插件会录制到隐藏的图层？  
答：极少数人会出现这种情况，也不知道原因，猜测是PS的生成器有损坏，也可以尝试重下一个PS。  
问：录制出来的视频有色差？  
答：是有一点，我也是经人提醒才发现的，我用的ffmpeg合成视频，但对这个东西我了解的也不多，猜测是颜色空间转化时带来了一点误差，但还不知道咋改。  