# 🧀 Cheese Run! – HTML5 Canvas Action Game

かわいい “ネズミ vs ネコ＆カラス” の横スクロール・アクションゲーム。
**チャージバスター** と **超サイヤ鼠モード** で巨大ボスを倒し、ゴールポールを目指そう！
ブラウザだけで動作し、画像リソースも不要。ローカルで `index.html` を開くだけでプレイできます。
![image](https://github.com/user-attachments/assets/1e7e7306-5756-40ce-abf8-4d8677cf30d5)


---

## 🎮 プレイ方法

| キー                    | 動作                                 |
| --------------------- | ---------------------------------- |
| **← / →**             | 移動                                 |
| **Space**             | ジャンプ（ブロックやボスを飛び越える）                |
| **Z（タップ）**            | 通常バスター  (ダメージ 1)                   |
| **Z 長押し ≥ 0.7s → 離す** | チャージバスター (ダメージ 3)・発射前は黄金オーラで超サイヤ鼠化 |
| **Enter**             | ゲームオーバー / クリア後にリスタート               |

---

## 📂 ファイル構成

```
project-root/
├─ index.html   # ゲーム本体（1 ファイル完結）
├─ README.md    # このファイル
└─ LICENSE      # MIT ライセンス（例）
```

> **画像や外部音源は一切不要**
> すべて Canvas API で描画しているため、`index.html` だけで完結します。

---

## 🚀 遊び方 & 開発環境

### 1. クローン & 実行

```bash
git clone https://github.com/<YOUR-USERNAME>/cheese-run.git
cd cheese-run
# ファイルをダブルクリックしてブラウザで開く
```

Chrome でローカル `file://` を開いても動作しますが、
簡易 HTTP サーバを立てると Live Reload が楽です。

```bash
# Python 3.x
python -m http.server 8000
# → http://localhost:8000 で index.html を開く
```

### 2. コードのポイント

* **Pure JavaScript**（ES5 相当）＋ **HTML5 Canvas**
* 外部ライブラリなし・画像なし
* シングルループ (`requestAnimationFrame`) 内で `update()` / `draw()` を実装
* 敵はシンプル AI、ボスは HP 制・バスター射撃付き
* すべての定数（速度・HP・発射間隔など）は上部の **定数定義ブロック** で一元管理

---

## 🛠️ カスタマイズ

| 変更項目     | 該当定数 / コード例                  |
| -------- | ---------------------------- |
| ボス発射間隔   | `const BOSS_SHOT_MS = 2200;` |
| ボス HP    | `boss = { hp: 30, … }`       |
| チャージ時間   | `const CHARGE_MS = 700;`     |
| ステージ長さ   | `const WORLD = 4300;`        |
| ブロック配置   | `const blocks = […]` 配列を編集   |
| 敵の種類を増やす | `spawnEnemy()` にタイプ追加        |

---

## 🤝 コントリビューション

1. **Fork** → **Branch** → **Commit**
2. PR の前に `README.md` を更新して変更内容を説明
3. 動作確認用に最低 1 プレイスルー動画 (GIF でも可) を添付していただけると助かります

---

## 📜 ライセンス

MIT License
© 2025 Beans&#x20;
