
# NFLチームロゴ用スタイルファイル

このページはNFL関係のブログを作っている人のために、32チームのチームロゴ、チームバナーのグラフィックスデータを綺麗に出力するためのスタイルファイルを提供しています。

## Website  
NFLには32チームあって、それぞれチームロゴを持っています。そのデータはいろいろなところで公開されています。今回参考/引用しているのは、Chris Creamerという人のサイトです。

http://www.sportslogos.net/

ここからFootball、National Football Leagueを辿ると、

http://www.sportslogos.net/teams/list_by_league/7/National_Football_League/NFL/logos/

にきて、ここからチームごとのページに行けます。必要なファイルは全てダウンロード済みで、このサイトにあります。ですから後述するようにロゴが変更された時以外にはダウンロードの必要はありません。ただ、このサイトを歩き回って見のはNFLファンにとって面白いと思います。

## Files

このサイトにあるファイル。
#### banners/
32チームのバナーファイル。
#### logos/
32チームのロゴファイル。

元々のChris Creamerさんのページで公開された時期によって、GIFである場合と、PNGである場合があります。ファイル名はそのチームの略称で、以下の通り。

| 略称 | チーム名 (AFC)||略称|チーム名 (NFC)|
|----|----|----|----|----|
|BUF|Buffalo Bills||DAL|Dallas Cowboys|
|MIA|Miami Dolphins||NYJ|New York Giants|
|NE|New England Patriots||PHI|Philadelphia Eagles|
|NYJ|New York Jets||WAS|Washington Redskins|
|BAL|Baltimore Ravens||CHI|Chicago Bears|
|CIN|Cincinnati Bengals||DET|Detroit Lions|
|CLE|Cleveland Browns||GB|Green Bay Packers|
|PIT|Pittsburgh Steelers||MIN|Minnesota Vikings|
|HOU|Houston Texans||ATL|Atlanta Falcons|
|IND|Indianapolis Colts||CAR|Carolina Panthers|
|JAX|Jacksonville Jaguars||NO|New Orleans Saints|
|TEN|Tennessee Titans||TB|Tampa Bay Buccaneers|
|DEN|Denver Broncos||ARI|Arizona Cardinals|
|KC|Kansas City Chiefs||LAR|Los Angeles Rams|
|LAC|Los Angeles Chargers||SF|San Francisco 49ers|
|OAK|Oakland Raiders||SEA|Seattle Seahawks|

以下はサンプルファイル。

#### banners.html
バナーの一覧。
#### logos.html
ロゴの一覧。
#### opponents.html
対戦相手一覧。毎年レギュラーシーズンが終了すると来期の対戦相手が決まります。「NFLの黄金郷」では具体的な日程が決まるまで、この対戦相手のリストを出しています。
#### score.html
試合のスコア。ロゴ版とバナー版を載せています。
#### standing.html
順位表。「NFLの黄金郷」ではSan Francisco 49ersを応援しているのでNFC西地区だけ載せていますが、チームを変えればどの地区の物でも作れます。

これはサンプルのHTMLファイルで、バナーとロゴの一覧、それに私が「NFLの黄金郷」で使ってきた「翌年シーズンの対戦相手」、「スコアボード」、「順位表」のサンプルです。

ファイルの中を見れば分かりますが、ここではbanners、logosの下にセーブされたイメージファイルを
```
<img src="">
```
ではなく、テーブルのTDのバックグラウンドとして引用しています。具体的には、各HTMLの中では、
```
<td class="logo SF_logo"></td>
```
とありますが、このTDには内容がありません。nfl.cssの中で、
```
.SF_logo {background-image: url("logos/SF.gif");}
```
というスタイルクラスが定義されており、SF.gifがこのセル（TD）の背景イメージとして使われます。

#### nfl.css

これが一番大切なCSS(スタイル)ファイルです。上で説明したように、このCSSの中で、
```
.BUF_logo {background-image: url("logos/BUF.gif");}
```
という形でロゴやバナーのファイルを参照しています。そしてこのCSSファイルは、HTMLファイルの中で、
```
<link rel="stylesheet" href="nfl.css" type="text/css">
```
で読み込まれています。

これは今、全てのファイルが同じディレクトリにあることを想定しています。しかし、ブログのプロバイダによって書いた記事が保管される場所が、上記のグラフィックデータファイルやCSSファイルを置いた場所と異なる場合があります。またタイトルバーやサイドバーに置かれるウィジェットが独自の場所に置かれることもあるかも知れません。その場合は、絶対パスを使うなどしてGIFやCSSファイルを指定してください。

## ファイルの更新

NFLには32ものチームがあって、そのいくつかは何年かに一度ロゴやバナーをマイナーチェンジします。このサイトでもなるべく更新していく予定ですが、間に合わない場合は、

http://www.sportslogos.net/teams/list_by_league/7/National_Football_League/NFL/logos/

から直接更新してください。ただ、このサイトのグラフィックデータファイルは、全くランダムなファイル名になっています。そのため、ダウンロードする時にファイル名を適切な物（チームの略称）に変更する必要があります。

また、チームによってはバナーの色を変えて2つか3つ提供しているところもあります。このブログではバックグラウンドが白のものを選んでいますが、人によっては別の色、バックグラウンドが違う色が好みの人もいるでしょう。その場合はご自分で好きなパターンをダウンロードするといいでしょう。

やり方は、上記のページから行きたいチームをクリック。次にPrimary LogoかWordmark Logosに新しいものがあるかどうかをチェック。もしあれば、そのロゴなりバナーをクリックすると大きなグラフィックデータが表示されるので、それをセーブ。この時、上にあるチームの略称でセーブします。

1つ注意が必要なことは、GIFの場合とPNGの場合があること。それを確認してnfl.cssの中で正しく指定すればOK。
