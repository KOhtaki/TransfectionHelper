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
## 1.部位特異的変異を導入した際のアミノ酸配列・塩基配列の変化予測
### 1-1.元になる塩基配列の選択
"Open the original seqence"の"open"ボタンをクリックし、元になる塩基配列が記録されているFASTAファイルを選択。<br>
もしくは、"Direct input of sequence data"の項目をチェックした後に、右側の大きな欄に元になる塩基配列を直接入力。"open"ボタンをクリック。<br>
<br>
元になる塩基配列が読み込めると、右側の大きな欄の下に新たな欄が形成されます。<br>
この欄には入力された塩基配列を参考にしたアミノ酸配列が自動的に書き込まれます。
### 1-2.変異させたいアミノ酸配列・塩基配列の場所の検索
#### 変異させたいアミノ酸配列が分かっている場合
"Enter the target Amino"の欄に変異させたいアミノ酸配列を入力して"Search"ボタンをクリック。<br>
元となる塩基配列と"Enter the target Amino"の欄に入力されたアミノ酸配列を参考に該当箇所の塩基配列が"Enter the target Gene"の欄に自動的に入力されるので、そのまま"Search"ボタンをクリック。<br>
#### 変異させたい塩基配列が分かっている場合
"Enter the target Amino"の欄が空白の状態で"Search"ボタンをクリック。<br>
"Enter the target Amino"の欄に変異させたい塩基配列を入力して"Search"ボタンをクリック。<br>
<br>
検索が正常に行われると、元になる塩基配列の右隣に欄が追加され、該当箇所の塩基配列が-(ハイフン)で抜けた塩基配列が自動的に入力されます。<br>
もし検索が上手くいかない場合は以下を疑ってください。
- 入力した配列が間違っている
- 入力した配列が短すぎて、該当箇所が複数ある。
- ~~配列内で大文字と小文字が入り乱れている。*現在大文字と小文字を別の文字として認識してしまうバグが発生しています。~~(220216修正)
### 1-3.希望する変異を導入した配列の作成
#### アミノ酸配列から塩基配列に変換する際の"最適化"にこだわらない場合
"Enter the new amino"の項目に変異させたいアミノ酸配列と"同じ長さ"の配列を入力し、"変換(amino)"ボタンをクリック。<br>
"Enter the new gene"の項目に変異させたいアミノ酸配列から塩基配列に変換された配列が自動的に入力されるので、そのまま"substitution"ボタンをクリック。<br>
- 配列の変換で選択されるコドンは、マウスにおいて最も選択確率の高いコドンが選択されています。
- 希望するアミノ酸配列と変異させたいアミノ酸配列の長さが異なると、塩基配列に変換した後の操作でエラーが発生します。
#### アミノ酸配列から塩基配列に変換する際に最適化する、既に導入したい塩基配列が決まっている場合。
本プログラムの行うアミノ酸配列から塩基配列への変換は最適化がされていません。<br>
別のプログラム、もしくはサイトで最適化を行ってください。
"Enter the new gene"の項目に変異させたいアミノ酸配列から塩基配列に変換した配列を入力し、"substitution"ボタンをクリック。<br>
<br>
希望する変異を導入した配列が作成されると、先の操作で作られた塩基配列の-(ハイフン)部分に希望する変異が赤字で置き換わります。<br>
配列の作成が上手くいかない場合は以下を疑って下さい。<br>
- 変異させたい配列と希望する変異を導入した配列の長さが異なっている。*現在の本プログラムは、インサーションやデリーションの作成に対応していません。<br>
### 1-4.元になった配列と新しく作成した配列の比較確認
"Result Confirmation"の
- gene_checkボタンをクリック＞元になった塩基配列と新しく作成した塩基配列が比較されます
- amino_checkボタンをクリック＞元になったアミノ酸配列と新しく作成したアミノ酸配列が比較されます
#### 表記
- a:元になった配列
- b:新しく作成した配列
- |:元になった配列と新しく作成した配列に置いて同一の箇所。
- *:元になった配列と新しく作成した配列に置いて異なっている箇所。
## 2.二つの配列の比較
### 2-1.一つ目の配列の選択
"Open the original seqence"の"Comparison of original and new"にチェック。<br>
"Open the original seqence"の"open"ボタンをクリックし、一つ目の塩基配列が記録されているFASTAファイルを選択。<br>
もしくは、"Direct input of sequence data"の項目をチェックした後に、右側の大きな欄に一つ目の塩基配列を直接入力。"open"ボタンをクリック。<br>
<br>
一つ目の塩基配列が読み込めると、右側の大きな欄の下に新たな欄が形成されます。<br>
この欄には入力された塩基配列を参考にしたアミノ酸配列が自動的に書き込まれます。
### 2-2.二つ目の配列の選択
"Open the new sequence"の"open"ボタンをクリックし、二つ目の塩基配列が記録されているFASTAファイルを選択。<br>
もしくは、"Direct input of sequence data"の項目をチェックした後に、右側の大きな欄に二つ目の塩基配列を直接入力。"open"ボタンをクリック。<br>
<br>
二つ目の塩基配列が読み込めると、一つ目の塩基配列の右隣に新たな欄が形成され、二つ目の塩基配列が入力されます。<br>
また、二つ目の塩基配列が入力された欄の下に、二つ目の塩基配列を参考にしたアミノ酸配列が自動的に書き込まれます。
### 2-3.二つの配列の比較
Result Confirmation"の
- gene_checkボタンをクリック＞一つ目の塩基配列と二つ目の塩基配列が比較されます
- amino_checkボタンをクリック＞一つ目のアミノ酸配列と二つ目のアミノ酸配列が比較されます
#### 表記
- a:一つ目の配列
- b:二つ目の配列
- |:一つ目の配列と二つ目の配列に置いて同一の箇所。
- *:一つ目の配列と二つ目の配列に置いて異なっている箇所。
