# Swing

Swing 是一个用于 Java GUI 编程（图形界面设计）的工具包（类库） 。Swing 是跨平台的。也正是因为 Swing 的这种特性，人们通常把 Swing 控件称为轻量级控件。
组件可以划分为容器组件和非容器组件，容器组件包括 JFmme 和 JDialog。

#### JPanel 面板

JPanel 是一种中间层容器，它能容纳组件并将组件组合在一起，但它本身必须添加到其他容器中使用。JPanel 类的构造方法如下。JPanel()：使用默认的布局管理器创建新面板，默认的布局管理器为 FlowLayout。
JPanel(LayoutManagerLayout layout)：创建指定布局管理器的 JPanel 对象。

###### JPanel类的常用方法方法名及返回值类型说明

Component add(Component comp) 将指定的组件追加到此容器的尾部 
void remove(Component comp) 从容器中移除指定的组件 
void setFont(Font f) 设置容器的字体 
void setLayout(LayoutManager mgr) 设置容器的布局管理器 
void setBackground(Color c) 设置组件的背景色 

#### JFrame 窗口

JFrame 用来设计类似于 Windows 系统中窗口形式的界面。JFrame 是 Swing 组件的顶层容器，该类继承了 AWT 的 Frame 类，支持 Swing 体系结构的高级 GUI 属性。

JFrame()：构造一个初始时不可见的新窗体。
JFrame(String title)：创建一个具有 title 指定标题的不可见新窗体。

###### JFrame类的常用方法方法名称概述

getContentPane() 返回此窗体的 contentPane 对象 
getDefaultCloseOperation() 返回用户在此窗体上单击“关闭”按钮时执行的操作 
setContentPane(Container contentPane) 设置 contentPane 属性 
setDefaultCloseOperation(int operation) 设置用户在此窗体上单击“关闭”按钮时默认执行的操作 
setDefaultLookAndFeelDecorated (boolean
defaultLookAndFeelDecorated) 设置 JFrame 窗口使用的 Windows 外观（如边框、关闭窗口的 小部件、标题等） 
setIconImage(Image image) 设置要作为此窗口图标显不的图像 
setJMenuBar( JMenuBar menubar) 设置此窗体的菜单栏 
setLayout(LayoutManager manager)设 置 LayoutManager 属性 

####  Java Swing布局管理器

##### 边框布局管理器

BorderLayout（边框布局管理器）是 Window、JFrame 和 JDialog 的默认布局管理器。边框布局管理器将窗口分为 5 个区域：North、South、East、West 和 Center。提示：边框布局管理器并不要求所有区域都必须有组件，如果四周的区域（North、South、East 和 West 区域）没有组件，则由 Center 区域去补充。如果单个区域中添加的不只一个组件，那么后来添加的组件将覆盖原来的组件，所以，区域中只显示最后添加的一个组件。
BorderLayout 布局管理器的构造方法如下所示。BorderLayout()：创建一个 Border 布局，组件之间没有间隙。
BorderLayout(int hgap,int vgap)：创建一个 Border 布局，其中 hgap 表示组件之间的横向间隔；vgap 表示组件之间的纵向间隔，单位是像素。

##### 流式布局管理器

FlowLayout（流式布局管理器）是 JPanel 和 JApplet 的默认布局管理器。FlowLayout 会将组件按照从上到下、从左到右的放置规律逐行进行定位。与其他布局管理器不同的是，FlowLayout 布局管理器不限制它所管理组件的大小，而是允许它们有自己的最佳大小。
FlowLayout 布局管理器的构造方法如下。FlowLayout()：创建一个布局管理器，使用默认的居中对齐方式和默认 5 像素的水平和垂直间隔。
FlowLayout(int align)：创建一个布局管理器，使用默认 5 像素的水平和垂直间隔。其中，align 表示组件的对齐方式，对齐的值必须是 FlowLayoutLEFT、FlowLayout.RIGHT 和 FlowLayout.CENTER，指定组件在这一行的位置是居左对齐、居右对齐或居中对齐。
FlowLayout(int align, int hgap,int vgap)：创建一个布局管理器，其中 align 表示组件的对齐方式；hgap 表示组件之间的横向间隔；vgap 表示组件之间的纵向间隔，单位是像素。

##### 卡片布局管理器

CardLayout（卡片布局管理器）能够帮助用户实现多个成员共享同一个显不空间，并且一次只显示一个容器组件的内容。
CardLayout 布局管理器将容器分成许多层，每层的显示空间占据整个容器的大小，但是每层只允许放置一个组件。CardLayout 的构造方法如下。CardLayout()：构造一个新布局，默认间隔为 0。
CardLayout(int hgap, int vgap)：创建布局管理器，并指定组件间的水平间隔（hgap）和垂直间隔（vgap）。

##### 网格包布局管理器

GridBagLayout（网格包布局管理器）是在网格基础上提供复杂的布局，是最灵活、 最复杂的布局管理器。GridBagLayout 不需要组件的尺寸一致，允许组件扩展到多行多列。每个 GridBagLayout 对象都维护了一组动态的矩形网格单元，每个组件占一个或多个单元，所占有的网格单元称为组件的显示区域。

GridBagLayout 所管理的每个组件都与一个 GridBagConstraints 约束类的对象相关。这个约束类对象指定了组件的显示区域在网格中的位置，以及在其显示区域中应该如何摆放组件。除了组件的约束对象，GridBagLayout 还要考虑每个组件的最小和首选尺寸，以确定组件的大小。

为了有效地利用网格包布局管理器，在向容器中添加组件时，必须定制某些组件的相关约束对象。GridBagConstraints 对象的定制是通过下列变量实现的。1. gridx 和 gridy
用来指定组件左上角在网格中的行和列。容器中最左边列的 gridx 为 0，最上边行的 gridy 为 0。这两个变量的默认值是 GridBagConstraints.RELATIVE，表示对应的组件将放在前一个组件的右边或下面。2. gridwidth 和 gridheight
用来指定组件显示区域所占的列数和行数，以网格单元而不是像素为单位，默认值为 1。3. fill
指定组件填充网格的方式，可以是如下值：GridBagConstraints.NONE（默认值）、GridBagConstraints.HORIZONTAL（组件横向充满显示区域，但是不改变组件高度）、GridBagConstraints.VERTICAL（组件纵向充满显示区域，但是不改变组件宽度）以及 GridB卡片布局管理器
CardLayout（卡片布局管理器）能够帮助用户实现多个成员共享同一个显不空间，并且一次只显示一个容器组件的内容。
