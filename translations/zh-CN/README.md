# Material Dialog v1.2.2

<!-- github-global:langs:start -->
## 翻译
[English](./translations/en/README.md) | [日本語](./translations/ja/README.md) | [繁體中文](./translations/zh-TW/README.md)
<!-- github-global:langs:end -->


这是一个 Android 库，我把它命名为 MaterialDialog。它非常易于使用，只需 `new` 一个实例并调用 `show()` 方法，美观的 AlertDialog 就会自动显示出来。它极具艺术感，符合 Google Material Design 规范。希望你会喜欢它，并享受它带来的体验。^ ^

## 截图

<img src="/screenshots/s1.png" alt="screenshot" title="screenshot" width="270" height="486" /><img src="/screenshots/s2.png" alt="screenshot" title="screenshot" width="270" height="486" />
<img src="/screenshots/s3.png" alt="screenshot" title="screenshot" width="270" height="486" /><img src="/screenshots/s4.png" alt="screenshot" title="screenshot" width="270" height="486" />

你还可以用自己喜欢的图片来更换背景，非常简单！：

<img src="/screenshots/s5.png" alt="screenshot" title="screenshot" width="270" height="486" /><img src="/screenshots/s6.png" alt="screenshot" title="screenshot" width="270" height="486" />

从 v1.0.6 开始，你可以使用 `setContentView()` 将 `message view` 替换为你的自定义视图。

示例：

<img src="/screenshots/s7.png" alt="setContentView" title="setContentView" width="270" height="486" /><img src="/screenshots/s8.jpg" alt="setContentView" title="setContentView" width="270" height="486" />
## 用法
### 第一步
####Gradle

```groovy
dependencies {
    compile 'me.drakeet.materialdialog:library:1.2.2'
}
```

如果它不起作用，请给我发邮件：drakeet.me@gmail.com

#### 或者

导入该库，然后将其添加到你的 `/settings.gradle` 和 `/app/build.gradle` 中。如果你不知道该怎么做，可以阅读我的博客寻求帮助。

[Android Studio 简介及导入 jar 包和第三方开源库方法](http://drakeet.me/android-studio)

### 第二步

非常简单，就像这样：

```java
MaterialDialog mMaterialDialog = new MaterialDialog(this)
    .setTitle("MaterialDialog")
    .setMessage("Hello world!")
    .setPositiveButton("OK", new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            mMaterialDialog.dismiss();
            ...
        }
    })
    .setNegativeButton("CANCEL", new View.OnClickListener() {
        @Override
        public void onClick(View v) {
            mMaterialDialog.dismiss();
            ...
        }
    });

mMaterialDialog.show();

// You can change the message anytime. before show
mMaterialDialog.setTitle("提示");
mMaterialDialog.show();
// You can change the message anytime. after show
mMaterialDialog.setMessage("你好，世界~");
```
在首次初始化并调用 `mMaterialDialog.show()` 后，对话框会自动显示。

此外，在实例化之后，你还可以调用 `setView (View v)` 和 `setContentView()` 来设置你喜欢或自定义的 View。这会替换掉标题和消息。
```java
EditText contentView = new EditText(this);
MaterialDialog mMaterialDialog = new MaterialDialog(this).setView(contentView);

mMaterialDialog.show();
```

另外，你可以调用 `setBackgroundResource(int resId)` 或 `setBackground(Drawable drawable)` 来更改背景：

```java
mMaterialDialog.setBackgroundResource(R.drawable.background);
```

## 1.2.1
现在，它已经可以在 L（Android 5.0）上完美运行。
修复了 L 上的按钮样式。
修复了相关问题，使其能够正确使用 `AutoCompleteTextView` 和 `EditText`。

## 1.1.0
修复了多次显示时的键盘/输入 bug。

## 1.0.9
如果标题为 null，则不显示标题，不过我觉得没有标题有点丑……；
新增通过字符串资源 ID 设置按钮文字的功能，例如 `setPositiveButton(android.R.string.yes, new View.OnClickListener() `

## 1.0.8
所有方法均返回 `this`，以支持链式调用

## 1.0.7
修复了 `焦点位于 EditText 上时无法自动弹出软键盘。` 的 bug

新增 `setCanceledOnTouchOutside()` // 你应该在 `show()` 之前设置它，否则不会生效。

新增 `setContentView()`

新增按钮按下样式；

...

我最近实在太忙了，如果你对这个库有任何建议，我建议你阅读源码，并尝试自己实现你的需求，然后我会将其合并进来。让我们一起创造美好的世界。

## BUG

## DEMO

[demo apk](/demo-release.apk)

## 关于我

一名来自中国大陆的学生。(^ ^ 感谢 daimajia)

我的博客：http://drakeet.me

更多关于我的信息：http://drakeet.me/about

License
============

    Copyright 2014 drakeet

	Licensed under the Apache License, Version 2.0 (the "License");
	you may not use this file except in compliance with the License.
	You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

	Unless required by applicable law or agreed to in writing, software
	distributed under the License is distributed on an "AS IS" BASIS,
	WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
	See the License for the specific language governing permissions and
	limitations under the License.