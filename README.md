# Jupyter Notebook スライド化 & web上に公開法

#### 手順

1. RISEをインストールする

```ターミナル
pip install RISE
jupyter-nbextension install rise --py --sys-prefix
jupyter-nbextension enable rise --py --sys-prefix
```

2. スライドの設定をする
使い方: <br>
"https://www.procrasist.com/entry/5-jupyter-slide" <br>
セルのタイプはメニューの『View』＞『Cell Toolbar』＞『Slideshow』で変更できるようになる。 <br>
『Slideshow』を選ぶと、セルの右上で『Slide Type』を選べるようになる。 <br>

「-」：セルをそのまま表示する  <br>
Slide：セルを１枚のスライドにする  <br>
Sub-slide：前スライドのサブスライドにする  <br>
Fragment：前スライドの下に表示する（画面端は切れる）  <br>
Skip：表示しない  <br>
Notes：ノート扱い  <br>

ーーー　さらにwebで公開したい人は　ーーー  <br>

3. html化する  <br>
```ターミナル
jupyter nbconvert "day5-jupyter-slide.ipynb" --to slides --reveal-prefix "https://cdnjs.cloudflare.com/ajax/libs/reveal.js/3.1.0"
```
出力されたhtmlファイルは、デフォルトのスライドデザインなので、jupyterの冒頭に書いたcssをコピーして、  <br>
htmlのスライドが始まる直前の<style></style>の間にはめ込んでやる(はじめのスライドのタイトルなどで検索すると見つかりやすい)  <br>
最後のところの
```
// scroll = false //元の状態
scroll = true //新しい状態
```
変更がおすすめ　 <br>

4. reveal.jsを自分のgithubページにforkして、適当な名前に変更(しなくてもOK)　 <br>
https://github.com/hakimel/reveal.js　
にアクセスして、右上のforkボタンを押すと自分のリポジトリにコピーされる
forkしたら、プロジェクト名を変更する(右らへんの歯車のタブから)

5.　gh-pagesブランチを削除　 <br>　

```ターミナル
git branch -rd origin/gh-pages
git push origin --delete gh-pages
```

6. 自分で新しくgh-pagesブランチを作成　 <br>

```ターミナル
git checkout -b gh-pages
```

7. index.htmlというhtmlファイルを先ほど出力した自分のスライドに差し替える　<br>
index.htmlを開いて、３で出力したhtmlの中身をコピー&ペースト　<br>

8. 上記で作ったブランチにpush　<br>

```ターミナル
git push origin gh-pages
```

9. https://ユーザまたは組織名.github.io/リポジトリ名
でアクセス!!　<br>

#### More reading
RISE install方法： "https://qiita.com/cvusk/items/d425751ba663dc8c6517"　<br>
使い方: "https://www.procrasist.com/entry/5-jupyter-slide"　<br>
web上にアップロード： https://www.procrasist.com/entry/5-jupyter-slide　<br>
