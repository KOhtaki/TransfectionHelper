# Site-Directed-Mutagenesis_designer
## 使用前に
”SDM_designer”は”Biopython”を利用しています。使用前に”Biopython”のインストールを行ってください。
```
pip install biopython
```

## 使い方
### 0-1.コードのダウンロード
右上の”Code”ボタンからzip形式でプログラムのコードをダウンロード。
### 0-2.プログラムの立ち上げ(windowsの場合)
ダウンロードが完了したら、解凍し、解凍後のファイルを展開。<br>
エクスプローラー上部のpathが記載されている所に”cmd”と入力してコマンドプロントを起動。<br>
起動後のコマンドプロントの作業場所が解凍後のファイルになっていることを確認し、以下のコマンドを入力。<br>
```
python SDM_designer.py
```
エラーメッセージが表示されずに立ち上がればプログラムの立ち上げが完了です。<br>
もしエラーメッセージが表示された場合は以下を疑ってください。
- 作業場所が解凍後のファイルになっていない。
- 解凍後のファイルから”SDM_designer.py”を移動している。
- パッケージ”Biopython”がお使いのPCにインストールされていない。
### 1.部位特異的変異を導入した際のアミノ酸配列・塩基配列の変化予測
### 1-1.元になる塩基配列の選択
"Open the original seqence"の"open"ボタンをクリックし、元になる塩基配列が記録されているFASTAファイルを選択。<br>
もしくは、"Direct input of sequence data"の項目をチェックした後に、右側の大きな欄に元になる塩基配列を直接入力。"open"ボタンをクリック。<br>
<br>
元になる塩基配列が読み込めると、右側の大きな欄の下に新たな欄が形成されます。<br>
この欄には入力された塩基配列を参考にしたアミノ酸配列が自動的に書き込まれます。
### 1-2.導入したいアミノ酸配列・塩基配列の場所の検索
#### 変異させたいアミノ酸配列は分かっているが、塩基配列は未確認の場合
"Enter the target Amino"の欄に変異させたいアミノ酸配列を入力して"Search"ボタンをクリック。<br>
元となる塩基配列と"Enter the target Amino"の欄に入力されたアミノ酸配列を参考に該当箇所の塩基配列が"Enter the target Gene"の欄に自動的に入力されるので、そのまま"Search"ボタンをクリック。
検索が正常に行われると、元になる塩基配列の左隣に欄が追加され、該当箇所の塩基配列が-(ハイフン)で抜けた塩基配列が自動的に入力されます。
