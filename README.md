# UI—第五弹，PopupWindow的用法你知道吗？

###一、前言：
**PopupWindow是一种弹出框，里面可以填充各种View，与AlertDialog类似。PopupWindow依附于View，AlertDialog依附于Activity。**

###二、微信公众号：
**关注微信公众号，获取密码，了解更多。**
**微信公众号：jike_android**

![公众号](https://github.com/wch0620/StatusBar/raw/master/WeiXin/qrcode.jpg)

###三、效果图：

![效果图](https://github.com/wch0620/PopupWindow/raw/popupwindow_dev/gif/popupwindow.gif)

###四、关键代码：

**1、顶部弹出动画，使用ObjectAnimator ：**

```
        view.setTranslationY(-height);
        final ObjectAnimator bgAnimator = new ObjectAnimator();
        final PropertyValuesHolder bgoffset = PropertyValuesHolder.ofFloat(
                "TranslationY", -height, 0f);
        final PropertyValuesHolder bgAlpha = PropertyValuesHolder.ofFloat(
                "alpha", 0.0f, 1.0f);
        bgAnimator.setTarget(view);
        bgAnimator.setValues(bgoffset, bgAlpha);
        bgAnimator.setInterpolator(new DecelerateInterpolator(1.5f));
        bgAnimator.setDuration(400);
```

**显示：**

```
mTopPopupWindow.showAsDropDown(top);
```

**2、底部弹出动画，换种方式使用xml：**

```
    <translate
        android:duration="400"
        android:fromYDelta="100%p"
        android:toYDelta="0"        
     /> 
```
