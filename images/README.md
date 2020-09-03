##如何使用

### 自动方法
使用QQ截图Ctrl+Alt+A或者微信的Alt+A截图后，按下Ctrl+Shiht+P快捷键即可自动上传到github对应的repo中，上传完成后，会有提示，自动将对应的图片地址送入剪贴板中，直接Ctrl+V即可粘贴对应的地址出来了~~

### 归类方法：
图片放到本地git，按照日期或者博客名称分类，git pull到github，然后用相对地址写，然后进行全部替换：
Step 1: In markdown it will show as below:
```text
![pictures][TEMP/20200903/1.jpg]
```
Step 2: git push all pictures to ```dadongshang/CDN/images/20200903/```

Step 3: Replace:
By hand with replace_all
```text
substitute
TEMP
by
https://cdn.jsdelivr.net/gh/dadongshangu/CDN@1.0/images/
```
Or use perl script:
```shell
perl replace_TEMP.pl -i doc.md
```

作者：FelixCoder
链接：https://www.jianshu.com/p/d51258ef5484
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

## 测试：
https://cdn.jsdelivr.net/gh/dadongshangu/CDN@1.0/images/Q35_shanghai.jpg

![pictures](https://cdn.jsdelivr.net/gh/dadongshangu/CDN@1.0/images/Q35_shanghai.jpg)
![test](https://cdn.jsdelivr.net/gh/dadongshangu/CDN@1.0/images/Q35_Shanghai.jpg)

Put images here.
References:
https://www.itrhx.com/2019/08/01/A27-image-hosting/


通过jsDelivr引用资源
使用方法：https://cdn.jsdelivr.net/gh/你的用户名/你的仓库名@发布的版本号/文件路径
例如：https://cdn.jsdelivr.net/gh/TRHX/CDN-for-itrhx.com@1.0/images/trhx.png
    https://cdn.jsdelivr.net/gh/TRHX/CDN-for-itrhx.com@2.0.1/css/style.css
    https://cdn.jsdelivr.net/gh/moezx/cdn@3.1.3//The%20Pet%20Girl%20of%20Sakurasou.mp4

注意：版本号不是必需的，是为了区分新旧资源，如果不使用版本号，将会直接引用最新资源，除此之外还可以使用某个范围内的版本，查看所有资源等，具体使用方法如下：

// 加载任何Github发布、提交或分支
https://cdn.jsdelivr.net/gh/user/repo@version/file

// 加载 jQuery v3.2.1
https://cdn.jsdelivr.net/gh/jquery/jquery@3.2.1/dist/jquery.min.js

// 使用版本范围而不是特定版本
https://cdn.jsdelivr.net/gh/jquery/jquery@3.2/dist/jquery.min.js
https://cdn.jsdelivr.net/gh/jquery/jquery@3/dist/jquery.min.js

// 完全省略该版本以获取最新版本
https://cdn.jsdelivr.net/gh/jquery/jquery/dist/jquery.min.js

// 将“.min”添加到任何JS/CSS文件中以获取缩小版本，如果不存在，将为会自动生成
https://cdn.jsdelivr.net/gh/jquery/jquery@3.2.1/src/core.min.js

// 在末尾添加 / 以获取资源目录列表
https://cdn.jsdelivr.net/gh/jquery/jquery/
