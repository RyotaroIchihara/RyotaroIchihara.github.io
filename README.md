## githubでVScodeをつかう
### ブラウザで、どこからでも、マルチプラットフォームで、turtleをやりたい
githubのあるリポジトリに入り、code>code>create codespace on mainを選ぶ。ほどなくして、メールで利用可能とくる。そうすると、visualstudio codeが使えるようになる。
ここで、jupyter notebook を起動し、turtleの特殊バージョン[mobilechelonian](https://github.com/takluyver/mobilechelonian/blob/master/README.rst)を動かせるようになるまでの手順

1. [こちら](https://atmarkit.itmedia.co.jp/ait/articles/2108/06/news030.html)の手順に従い、jupyterとenvを入れる
2. 以下のコードを、上で作成したenvフォルダに移動して、ターミナルを起動して、以下のコードを打つ

> conda env list
> conda create -n turtle python=3.6（3.10.4　自分がやった時）
> conda activate turtle

3. ここで、アクティベートするにはinitファイルがどうのこうのと出るので適当な名前でinitファイルを作って、ターミナルをいったん終了。またターミナルを立ち上げて、先ほどの仮想ディレクトリへ移動。次に以下を打つ
> conda activate turtle
> pip install mobilechelonian
> juypter notebook
5. するとしばらくすると以下の文字列が吐き出されるので、ブラウザで新しく開くjupyter notebookのtokenを入れろというフィールドに、token=で示された文字列を入れる。
> copy and paste one of these URLs:
>         http://localhost:8888/? token=482238d55a25c3c0268af7da04b579091b79a5f386ee949d
6. 無事にjupyter notebookが動き出した。
7. 右のほうにあるNewのNotebook: Python3(ipykernel)を選ぶとコードをいじれるウィンドウが立ち上がる（ブラウザの別タブ）
8. ここに、以下のコードを張り付けて、ctrl+enterでついにできる。
> from mobilechelonian import Turtle
> t = Turtle()
> t.speed(5)
> colours=["red","blue","yellow","brown","black","purple","green"]
> 
> t.penup(); t.left(90); t.forward(200);t.right(90);t.pendown()
> for i in range (0,18):
>     t.pencolor(colours[i%7])
>     t.right(20)
>     t.forward(50)
> 
> t.right(180)
> t.home()
