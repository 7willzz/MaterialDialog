# Material Dialog v1.2.2

<!-- github-global:langs:start -->
## 翻譯
[English](./translations/en/README.md)
<!-- github-global:langs:end -->

這是一個 Android 函式庫，我稱它為 MaterialDialog。它非常容易使用，只要 `new` 它並呼叫 `show()` 方法，美觀的 AlertDialog 就會自動顯示。它富有美感，符合 Google Material Design。希望你會喜歡它，並享受它。^ ^

## 截圖

<img src="/screenshots/s1.png" alt="screenshot" title="screenshot" width="270" height="486" /><img src="/screenshots/s2.png" alt="screenshot" title="screenshot" width="270" height="486" />
<img src="/screenshots/s3.png" alt="screenshot" title="screenshot" width="270" height="486" /><img src="/screenshots/s4.png" alt="screenshot" title="screenshot" width="270" height="486" />

你也可以用自己喜歡的圖片來更換背景，非常簡單！：

<img src="/screenshots/s5.png" alt="screenshot" title="screenshot" width="270" height="486" /><img src="/screenshots/s6.png" alt="screenshot" title="screenshot" width="270" height="486" />

從 v1.0.6 開始，你可以使用 `setContentView()` 將 `message view` 換成你的自訂 view。

範例：

<img src="/screenshots/s7.png" alt="setContentView" title="setContentView" width="270" height="486" /><img src="/screenshots/s8.jpg" alt="setContentView" title="setContentView" width="270" height="486" />
## 使用方式
### 步驟 1
####Gradle

```groovy
dependencies {
    compile 'me.drakeet.materialdialog:library:1.2.2'
}
```

如果無法運作，請寄信給我：drakeet.me@gmail.com

####或者

匯入此函式庫，然後將它加入你的 `/settings.gradle` 和 `/app/build.gradle`，如果你不知道怎麼做，可以閱讀我的部落格尋求協助。

[Android Studio 簡介及導入 jar 包和第三方開源庫方法](http://drakeet.me/android-studio)

### 步驟 2

非常簡單，就像這樣：

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
在第一次初始化並呼叫 `mMaterialDialog.show()` 之後，它就會自動顯示。

此外，你可以在實例化之後呼叫 `setView (View v) ` 與 `setContentView()` 來設定你喜歡的 View 或自訂 View。這會取代標題與訊息。
```java
EditText contentView = new EditText(this);
MaterialDialog mMaterialDialog = new MaterialDialog(this).setView(contentView);

mMaterialDialog.show();
```

而且，你可以呼叫 `setBackgroundResource(int resId)` 或 `setBackground(Drawable drawable)` 來更換背景：

```java
mMaterialDialog.setBackgroundResource(R.drawable.background);
```

## 1.2.1
現在，它已經可以在 L 上完美執行。
修正 L 上的按鈕樣式。
修正了一個問題，讓它能正確使用 `AutoCompleteTextView` 與 `EditText`。

## 1.1.0
修復多次顯示時的鍵盤／輸入 bug。

## 1.0.9
如果標題為 null，就不顯示它，但我覺得沒有標題有點醜……；
新增透過字串資源 ID 設定按鈕文字，例如 `setPositiveButton(android.R.string.yes, new View.OnClickListener() `

## 1.0.8
新增每個方法都回傳 `this`

## 1.0.7
修復 `當焦點在 EditText 上時無法自動顯示軟鍵盤` 的 BUG。

新增 `setCanceledOnTouchOutside()` // 你應該在 `show()` 之前設定它，否則它不會生效。

新增 `setContentView()`

新增按鈕按下樣式；

...

我最近實在太忙了，如果你對這個函式庫有任何建議，我鼓勵你閱讀原始碼，並嘗試實現你的需求，然後我會將它合併進來。讓我們一起創造美好的世界。

## BUG

## DEMO

[demo apk](/demo-release.apk)

## 關於我

一位來自中國大陸的學生。(^ ^ 感謝 daimajia)

我的部落格：http://drakeet.me

更多關於我的資訊：http://drakeet.me/about

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