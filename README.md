# drawableDemon
讲述Drawable文件夹的使用

selector 节点 属性：

属性	参数类型	说明
android:autoMirrored	boolean	设置图片是否需要镜像反转
android:constantSize	boolean	设置自身大小是否随着其状态改变而改变
android:enterFadeDuration	int	状态改变时，新状态展示时的淡入时间，以毫秒为单位
android:exitFadeDuration	int	状态改变时，新状态消失时的淡入时间，以毫秒为单位
android:variablePadding	boolean	padding是否随状态的改变而改变，默认false
子节点 item 属性：

属性	参数类型	说明
android:drawable	drawable	对应drawable，可以为color、bitmap、shape等单一drawable
android:android:state_xxx	boolean	设置不同的状态
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:drawable="@color/button_press"
          android:state_pressed="true"/>
    <item android:drawable="@color/button_norm"
          android:state_pressed="false"/>
</selector>
子节点 item 还可以包含许多子节点，如bitmap、shape、color、动画相关的等，下面给出两个例子说明用法。

在布局文件中给view设置 android:background="@drawable/button_seleter" 即可，实现在点击view时显示不同的背景图，有点击的效果反馈。

这里需要注意一点：
如果上边所说的view是 Button 的话，直接可以看到效果，但是，实际开发中，我们可能要给 LinearLayout、TextView 设置点击效果，使用上面的方法是没有效果的。

解决方法：给这个 view 添加点击事件的监听。

上边代码中的 android:drawable 不只可以设置为color类型的drawable，还可以设置为bitmapDarwable、ShapeDrawable等，下面看一个圆角点击效果的例子。

<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:state_pressed="false">
        <shape>
            <corners android:radius="10dp"/>
            <solid android:color="@color/button_norm"/>
        </shape>
    </item>
    <item android:state_pressed="true">
        <shape>
            <corners android:radius="10dp"/>
            <solid android:color="@color/button_press"/>
        </shape>
    </item>
</selector>
设置在view上的效果为有圆角效果，并且按下的时候，背景后改变。
以上代码在 selector 节点下有两个 item 节点，item节点设置了是否点击的状态，并且包含了一个 shape 节点，作为对应状态下的drawable对象。
