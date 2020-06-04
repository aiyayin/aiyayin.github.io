https://cloud.tencent.com/developer/user/2898788

setContentView

getDelegate

->AppCompatDelegate.Create

->AppCompatDelegateImplV9.setContentView

->ensureSubDecor

->createSubDecor

(->requestWindowFeature

->mWindow.getDecorView();// 就是创建DecorView

->subDecor inflate

-> mWindow.setContentView(subDecor);)

**setContentView的过程就是通过PhoneWindow创建DecorView，然后创建SubDecor，最终将传递进来的布局add进来。**