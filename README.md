# style-transfer

![sample1](https://user-images.githubusercontent.com/40655712/55858535-e4a38380-5baa-11e9-8db1-29cc0fac78b4.jpg)
![sample2](https://user-images.githubusercontent.com/40655712/55858515-d8b7c180-5baa-11e9-912d-d90515b63418.jpg)

スタイル変換を実装しました。 
ここで示した画像は炎のスタイルを取り入れて、元画像が燃えているような変換がなされます。  
  
google colaboratory上で実行することを想定しています。  
  
google colaboratory以外の環境で実行するときは、
・先頭に!がついているshellコマンドは使えない
・パスの設定を適宜変更する
事に気を付ければOKです。  

## サンプルパラメータ
parameterファイルに学習済みパラメータ（net_81280.prm）を入れておきました。  
上で紹介した炎のスタイル変換です。

##パラメータ調整
スタイル画像と元画像の組み合わせによって、適切なスタイル画像と元画像の強さの割合が異なるので、パラメータで調整できるようにしておきました。

```
#weightは重みパラメータ。スタイル画像の強さを決める
#第一変数がそのほかに比べて小さいほどスタイル画像が強く表れる
weight=torch.tensor([1.0,40.0,40.0,40.0,40.0])
weight0=weight[0].to("cuda:0")
```
