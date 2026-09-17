# Material Dialog v1.2.2

<!-- github-global:langs:start -->
## 翻訳
[English](./translations/en/README.md)
<!-- github-global:langs:end -->

これは Android ライブラリで、MaterialDialog と呼んでいます。とても簡単に使えます。`new` して `show()` メソッドを呼ぶだけで、美しい AlertDialog が自動的に表示されます。Google Material Design に準拠した芸術的なライブラリです。皆さんに気に入って楽しんでいただけたら嬉しいです。^ ^

## スクリーンショット

<img src="/screenshots/s1.png" alt="screenshot" title="screenshot" width="270" height="486" /><img src="/screenshots/s2.png" alt="screenshot" title="screenshot" width="270" height="486" />
<img src="/screenshots/s3.png" alt="screenshot" title="screenshot" width="270" height="486" /><img src="/screenshots/s4.png" alt="screenshot" title="screenshot" width="270" height="486" />

お好みの画像で背景を変更することもできます。とても簡単です！：

<img src="/screenshots/s5.png" alt="screenshot" title="screenshot" width="270" height="486" /><img src="/screenshots/s6.png" alt="screenshot" title="screenshot" width="270" height="486" />

さらに v1.0.6 からは、`setContentView()` を使って `message view` を独自のカスタムビューに変更できるようになりました。

例：

<img src="/screenshots/s7.png" alt="setContentView" title="setContentView" width="270" height="486" /><img src="/screenshots/s8.jpg" alt="setContentView" title="setContentView" width="270" height="486" />
## 使い方
### ステップ 1
####Gradle

```groovy
dependencies {
    compile 'me.drakeet.materialdialog:library:1.2.2'
}
```

うまく動作しない場合は、drakeet.me@gmail.com までメールしてください。

####または

ライブラリをインポートし、`/settings.gradle` と `/app/build.gradle` に追加してください。方法がわからない場合は、私のブログを参考にしてください。

[Android Studio 簡介及び jar パッケージとサードパーティオープンソースライブラリの導入方法](http://drakeet.me/android-studio)

### ステップ 2

とても簡単です。以下のようにするだけです：

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

// 表示前なら、いつでもメッセージを変更できます
mMaterialDialog.setTitle("ヒント");
mMaterialDialog.show();
// 表示後でも、いつでもメッセージを変更できます
mMaterialDialog.setMessage("こんにちは、世界〜");
```

最初に初期化して `mMaterialDialog.show()` を呼ぶと、自動的に表示されます。

さらに、インスタンス化した後に `setView (View v)` や `setContentView()` を呼び出して、お好みの View やカスタムビューを設定することもできます。これはタイトルとメッセージを置き換えます。
```java
EditText contentView = new EditText(this);
MaterialDialog mMaterialDialog = new MaterialDialog(this).setView(contentView);

mMaterialDialog.show();
```

また、`setBackgroundResource(int resId)` または `setBackground(Drawable drawable)` を呼び出して背景を変更することもできます：

```java
mMaterialDialog.setBackgroundResource(R.drawable.background);
```

## 1.2.1
現在、L（Android L）で完璧に動作するようになりました。
L でのボタンスタイルを修正しました。
問題を修正し、`AutoCompleteTextView` と `EditText` を正しく使用できるようにしました。

## 1.1.0
複数回表示した際のキーボード/入力のバグを修正しました。

## 1.0.9
タイトルが null の場合は表示しないようにしました。ただし、タイトルがないと見栄えが悪いと思います…；
string resId でボタンのテキストを設定できるようにしました。例： `setPositiveButton(android.R.string.yes, new View.OnClickListener() `

## 1.0.8
すべてのメソッドが `this` を返すようにしました。

## 1.0.7
`フォーカスが EditText にあるときにソフトキーボードが自動的に表示されない` というバグを修正しました。

`setCanceledOnTouchOutside()` を追加しました。// `show()` の前に設定する必要があります。そうしないと反映されません。

`setContentView()` を追加しました。

ボタンの押下スタイルを追加しました。

...

最近とても忙しいので、このライブラリへのご提案があれば、ソースコードを読んでご自身の要件を実装してみていただければ、マージいたします。共に良い世界を作りましょう。

## バグ

## デモ

[demo apk](/demo-release.apk)

## 私について

中国本土の学生です。(^ ^ Thanks daimajia)

私のブログ： http://drakeet.me

私について詳しく： http://drakeet.me/about

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