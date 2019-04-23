# Jupyter Notebook スライド化

#### 手順

1. RISEをインストールする

```ターミナル
pip install RISE
jupyter-nbextension install rise --py --sys-prefix
jupyter-nbextension enable rise --py --sys-prefix
```

2. スライドの設定をする
使い方: "https://www.procrasist.com/entry/5-jupyter-slide"
セルのタイプはメニューの『View』＞『Cell Toolbar』＞『Slideshow』で変更できるようになる。
『Slideshow』を選ぶと、セルの右上で『Slide Type』を選べるようになる。

「-」：セルをそのまま表示する
Slide：セルを１枚のスライドにする
Sub-slide：前スライドのサブスライドにする
Fragment：前スライドの下に表示する（画面端は切れる）
Skip：表示しない
Notes：ノート扱い

ーーー　さらにwebで公開したい人は　ーーー

3. html化する
```ターミナル
jupyter nbconvert "day5-jupyter-slide.ipynb" --to slides --reveal-prefix "https://cdnjs.cloudflare.com/ajax/libs/reveal.js/3.1.0"
```
出力されたhtmlファイルは、デフォルトのスライドデザインなので、jupyterの冒頭に書いたcssをコピーして、htmlのスライドが始まる直前の<style></style>の間にはめ込んでやる(はじめのスライドのタイトルなどで検索すると見つかりやすい)
最後のところの
scroll = false
→ scroll = true
変更がおすすめ

4. reveal.jsを自分のgithubページにforkして、適当な名前に変更(末尾は.github.io?　→　違うかも、、試してない)
https://github.com/hakimel/reveal.js　にアクセスして、右上のforkボタンを押すと自分のリポジトリにコピーされる
forkしたら、プロジェクト名を変更する(右らへんの歯車のタブから)

5.　gh-pagesブランチを削除

```ターミナル
git branch -rd origin/gh-pages
git push origin --delete gh-pages
```

6. 自分で新しくgh-pagesブランチを作成

```ターミナル
git checkout -b gh-pages
```

7. index.htmlというhtmlファイルを先ほど出力した自分のスライドに差し替える
index.htmlを開いて、３で出力したhtmlの中身をコピー&ペースト

8. 上記で作ったブランチにpush

```ターミナル
git push origin gh-pages
```

9. https://ユーザまたは組織名.github.io/リポジトリ名 でアクセス!!

#### More reading
RISE install方法：　"https://qiita.com/cvusk/items/d425751ba663dc8c6517"
使い方: "https://www.procrasist.com/entry/5-jupyter-slide"
web上にアップロード： https://www.procrasist.com/entry/5-jupyter-slide
