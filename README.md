# style_them_error
在style和主题中遇到的问题

    java.lang.IllegalStateException: You need to use a theme.appcompat theme (or descendant) with this activity
    错误描述：java.lang.IllegalStateException: You need to use a theme.appcompat theme (or descendant) with this activity
    产生原因：Activity继承自AppCompatActivity，在style.xml中使用了不兼容的Theme。

    从错误提示中提到Theme.AppCompat theme，这是因为我们的activity一定是继承了兼容包中的类，
    比如我这里就无意中继承了AppCompatActivity，它来自android.support.v7.app.AppCompatActivity。
    所以就要使用与其配合的AppCompat的theme才行。

    解决：1、使用AppCompat theme；
            
              <style name="AppBaseTheme" parent="Theme.AppCompat.Light.DarkActionBar"></style>

       2、直接继承自Activity。
