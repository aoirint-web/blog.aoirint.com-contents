---
title: Hexoで日記用のブログを用意した
date: '2021-11-17 04:00:00'
draft: false
noindex: true
channel: 雑記
---

# Hexoで日記用のブログを用意した

Twitterは開かれすぎていて恥ずかしいし、下手な投稿をすると、エゴサする人とか、有識者とかを変に刺激して、攻撃的な反応をされることがある場所になっている。
それはとても疲れるので、そういう攻撃にさらされにくく、個人的な文章を公開できる場所がほしかった。
自分の考えを整理する機会がないので、半分自虐のお気持ち表明みたいなこともやるかもしれない。
そういう意味で、自分への免罪符と、覗きに来る人への立て札として、サイト名をVent・排気口としている（あもあすの影響）。

こういった自分の思っていることを書く文章というのは、大抵の場合、恥ずかしくなったり、書くことがなかったりで、1つ2つ書いた時点で消したり、使わなくなってしまったりする。
過去の記事タイトルや概要が一覧表示されると、恥ずかしくて消したくなってしまう。

そのあたりを考えると、細かいことを気にせずに書ける方法がいい。
はてなブログは、UIは使いやすくて好きなのけれど、PRO版でないと、はてなキーワード機能で有識者を引き寄せてしまうのが怖い。SNS化されていない場所がいい。
それならWordPressか、と思って一度VPSに立ててみたけれど、Markdownで書けない（プラグインのことは考えたくない）のがつらい。Markdownといっても、ソフトブレークなちゃんぽんだけど。
DokuWikiとかMediaWikiが向いているとは思わない。Sphinxもカテゴリ/タグ機能がない感じが微妙。
DBが必要というのはイケていない。
ならGit管理だ、GitHubだ、SSGだ、となる。
それで、なんかモダンなTypeScriptで書かれたHexoを試しに使ってみた、ということになる。
ふだんはPythonで書かれたMiyadaikuを使っているのだけれど、ユーザが少ないので、あまりいいテーマがない。
となると自作することになるのだけれど、2,3記事で爆破するかもしれないものにそこまでの労力をかけたくない。
といっても、いまこのブログもデフォルトテーマのLandscapeを使っていて、その理由はあまりいいテーマがなかったからなのだけれども。Lightはよかったけどコメント欄が消せねえ。
Git管理結構、GitHub結構、SSG結構なのだけれども、_postsディレクトリに過去の記事が全部出てくるのがイケてない。slugという仕組みとマッチしていない（なんでURLに2回日付が出てくるんですかね）。記事を作るときに記事の名前が必要なのもイケてない。
画像を追加したら、音声を追加したら、どんどんリポジトリが重くなる。まあフルクローンする機会もそうそうないか。世の中のサービスはすぐにサ終するので、外部にアップロードはしたくない。
ほかにもURLの永続性とか、いろいろ考え始めるとキリがないので、そのあたりの運用は適当になることをご承知おきいただきたい。
あまり納得のいっていないHexoから乗り換えるときにURLをリダイレクトさせるとか面倒くさいので。
あとなんか記事ジェネレータがバグっていて、生成されたmdファイルがそのままだとビルドできない（なぜか`{}`がfront-matterに入り込んでいて、タイトルもUTC時刻になっている）

うーん、万が一この記事が攻撃の対象になったときに、言及している対象に迷惑がかからないように、とか余計なことを考えてしまう。
それだったら記事を分割して、余計な言及をあいまいにして...としたりしなかったり（戻したり）しながら書いている。とても無駄だし、とてもストレスになる。
はてなキーワードはこの意味でよくない。
記事を分割すると書くまでもない、みたいなことが拾えずに気になってしまう。

リンクを張るならnoreferrerしないと、解析に残ってしまうな...。

- <https://github.com/hexojs/hexo-filter-nofollow>

これでよさそう。


悪意があるのかないのかわからないけど、攻撃的な反応と受け取ったことで、
精神ダメージを受けている人を同時に2人観測するのはあんまりよくない（ふにちかさんとヒホさん）。
そしてこういうのがエゴサにひっかかってしまうので、noindexせざるを得ない。