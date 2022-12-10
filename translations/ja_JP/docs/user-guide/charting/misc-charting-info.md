# その他の譜面作成に関する情報
---

## ノーツの色設定
楽曲の雰囲気に合わせてノーツの色を変更したいって思いませんか？...なんと出来ます！ `song.tmb` をお気に入りのテキストエディタ(Notepad++やIntelliJ IDEA等)で開き、 `note_color_start` と `note_color_end` を以下のように配列の末尾に追加してください。
```
... "timesig": 2, "tempo": 100, "UNK1": 0} 
// 追加前 ↑
... "timesig": 2, "tempo": 100, "UNK1": 0, "note_color_start": [0.0, 0.0, 0.0], "note_color_end": [1.0, 1.0, 1.0]}
// 追加後 ↑
```
色の表示はRGB1で、上記の例では黒から白に変わります。 このような数値にするには <https://rgbacolorpicker.com/> などのカラーピッカーを利用し、使用する色をRGB値で取得します。 それでは試しに、`rgb(84, 14, 50)` のような素敵な深みのある紫色を使いたいと仮定しましょう。 これらを使うにはR、G、Bのすべての値を `255` で割ります。84÷255など(四捨五入して、せめて少数第九位まで入力)
```
... "timesig": 2, "tempo": 100, "UNK1": 0, "note_color_start": [0.329411765, 0.0549019608, 0.196078431], "note_color_end": [0.329411765, 0.0549019608, 0.196078431]}
```
これでノーツの最初と最後も、深みのある紫色に変わります！


## その他の .trombackgroundに関する情報

### トロンボーン奏者の表示
`.trombackground`を作成するときカメラの深度を１に設定するとトロンボーン奏者を上に表示することができます。

### トロンボーン奏者をシーンに追加
`.trombackground` を作成していて、自由に動かせるトロンボーン奏者が欲しい場合は　`Prefabs/Tromboner` のプリセットを背景に追加してください。

ゲームがロードされると、プレイヤーの完全なクローンに置き換えられます。

また、演奏者と全く同じにしたくない場合は、演奏者モデル &トロンボーンのスキンを変更することができます。

(上記のカメラ深度の表示方法のヒントと組み合わせて使用すると、トロンボーン奏者のレンダリング方法を完全に変更することができます)