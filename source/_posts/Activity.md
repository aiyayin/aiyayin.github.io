---
title: setContentView流程
categories: 
- Android
tags:
- Android
typora-root-url: ..
---


### setContentView

getDelegate

->AppCompatDelegate.Create

->AppCompatDelegateImplV9.setContentView

->ensureSubDecor

->createSubDecor

(->requestWindowFeature

->mWindow.getDecorView();// 就是创建DecorView

->subDecor inflate

-> mWindow.setContentView(subDecor);)

setContentView的过程就是通过PhoneWindow创建DecorView，然后创建SubDecor，最终将传递进来的布局add进来。



### LayoutInflater

LayoutInflater.inflate()

->Xml.asAttributeSet(XmlPullParser  parser)

->首先进行View的合理性校验，include、merge等标签

->createViewFromTag

(->final TypedArray ta = context.obtainStyledAttributes(attrs, ATTRS_THEME);

->Factory.onCreateView || onCreateView

(->clazz.getConstructor //反射获取这个View的构造器

->constructor.newInstance(args)))

->generateLayoutParams//根据当前标签的参数生成LayoutParams

->rInflateChildren

-> root.addView


### LayoutInflater Factory 

AppCompatActivity .onCreate

->delegate.installViewFactory

->AppCompatDelegateImpl.createView

->AppCompatViewInflater.createView

->switch (name)  createView

![LayoutInflater](/images/Activity/LayoutInflater-1594026178672.png)

参考：https://cloud.tencent.com/developer/user/2898788