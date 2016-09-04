# drawableDemon
讲述Drawable文件夹的使用

在布局文件中给view设置 android:background="@drawable/button_seleter" 即可，实现在点击view时显示不同的背景图，有点击的效果反馈。

这里需要注意一点：
如果上边所说的view是 Button 的话，直接可以看到效果，但是，实际开发中，我们可能要给 LinearLayout、TextView 设置点击效果，使用上面的方法是没有效果的。

解决方法：给这个 view 添加点击事件的监听。




