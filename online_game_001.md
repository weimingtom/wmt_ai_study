## 多人在线游戏架构实战  
* http://www.hzbook.com/index.php/Book/search.html?k=多人在线游戏架构实战  
* search baidupan, 多人在线游戏架构实战  
* https://github.com/setuppf/GameBookServer  
* https://github.com/setuppf/GameBookClient  

## Unity UI Layout, Unity布局问题  
https://github.com/weimingtom/GalGame-1/tree/master/GalGameUnity5/Assets/Scenes  
双击打开end场景（end.unity），点上方的运行按钮，然后就可以看到一个最简单的布局，一个白色背景，一个背景图，三个按钮。  
这里演示了如何处理背景图和按钮的定位问题。  
（1）对于图片加载，你可以通过Unity自带的原生GUI的Image类来实现（层级窗口->右键菜单->UI->Image），  
当然这里也许有别的办法，我以后再讨论，不过这可能是最容易理解的方法。  
（2）背景图布局：设置好大小和对齐方式即可，这里就是写死了大小尺寸和坐标居中  
（3）按钮布局：类似背景图，不同的是，按钮的层级是在背景图CG的子对象，而不是在CG的旁边。另外这里大小是写死的，  
但位置不是居中，而是一个写死的坐标（Pos X、Pos Y）。  
于是这样就做好了最简单的游戏界面，一张图三个按钮，但这样的布局有一个很奇怪的问题：为什么运行后，  
背景图CG层实际显示的大小和写死的长宽值有出入？  
我认为这可能是Image类的特殊性导致的，导致在运行期width和height的数值会自动调整。  
我下一次再实际操作一下，解决这个疑惑    

## eq2  
http://sourceforge.net/projects/eq2emulator/  
search baidupan, eq2_Source_v1.7z  

## sogou/workflow  
https://github.com/sogou/workflow  
