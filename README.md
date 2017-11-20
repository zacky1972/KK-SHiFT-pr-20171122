# README.md: KK-Shift-pr-20171122

## インストール方法

```
$ gem install slim html2slim
$ npm install -g bower yo grunt-cli generator-reveal gulp
$ git clone git@github.com:zacky1972/KK-SHiFT-pr-20171122.git
$ cd KK-Shift-pr-20171122
$ npm install
$ bower install
```

## プレゼンテーション表示方法

```
$ cd KK-Shift-pr-20171122
$ grunt serve
```

## GitHub Pages への公開

```
$ grunt deploy
```

[このページを開きます](https://zacky1972.github.io/KK-SHiFT-pr-20171122/)

## スライドの追加

### Markdown のスライドの追加

```
$ yo reveal:slide "slide-title" --markdown
$ subl slides/slide-title.md
```

next-slide-title には英語のタイトルを入れる(そのままファイル名になる)。残念ながら日本語は通らない。

### HTML のスライドの追加

```
$ yo reveal:slide "slide-title"
$ subl slides/slide-title.html
```

slide-title には英語のタイトルを入れる(そのままファイル名になる)。残念ながら日本語は通らない。

スライドごとの CSS は style タグを作って書く。

```html
<style>
	h2 {
		color: red !important;
	}
</style>

<h2>slide-title</h2>

<p>Please change me!</p>
```

### Slim のスライドの追加

HTML のスライドの追加をした後，同名の slim ファイルを追加する

```
$ yo reveal:slide "slide-title"
$ html2slim slides/slide-title.html slides/slide-title.slim
$ subl slides/slide-title.slim
```

slide-title には英語のタイトルを入れる(そのままファイル名になる)。残念ながら日本語は通らない。

スライドごとの CSS は style タグを作って書く。

```slim
style
  |  h2 { color: red !important; }
h2
  | slide-title
p
  | Please change me!
```

Slim を追加した場合は，スライドを表示したりデプロイしたりする前に gulp を実行して slides/\*.slim を変換しておく

```
$ gulp
```
