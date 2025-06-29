# T3_THF Game

単一責任の原則に従って設計されたモジュラーゲームアーキテクチャ

## ファイル構造

```
docs/
├── index.html          # メインHTMLファイル
├── main.js             # エントリーポイント
├── style.css           # スタイルシート
├── README.md           # このファイル
├── .gitattributes      # Git設定ファイル
├── core/               # ゲームの核となるクラス
│   ├── Game.js         # メインゲームクラス
│   ├── GameState.js    # ゲーム状態管理
│   └── Timer.js        # タイマー管理
├── managers/           # 各種マネージャークラス
│   ├── InputManager.js     # 入力管理
│   ├── RenderManager.js    # 描画管理
│   ├── CollisionManager.js # 衝突判定
│   ├── EnemyManager.js     # 敵管理
│   ├── ParticleManager.js  # パーティクル管理
│   ├── UIManager.js        # UI管理
│   ├── PauseManager.js     # ポーズ管理
│   ├── AttackManager.js    # 攻撃管理
│   ├── CameraManager.js    # カメラ管理
│   └── AmmoManager.js      # 弾薬管理
├── entities/           # ゲームエンティティ
│   ├── Character.js    # 基本キャラクタークラス
│   ├── Player.js       # プレイヤークラス
│   ├── Enemy.js        # 敵クラス（赤鬼、青鬼、黒鬼、ボス鬼）
│   └── Particle.js     # パーティクルクラス
├── components/         # コンポーネントクラス
│   ├── PlayerController.js # プレイヤー制御
│   ├── PlayerRenderer.js   # プレイヤー描画
│   └── HealthBar.js        # HPバー
├── utils/              # ユーティリティクラス
│   ├── Sprite.js       # スプライト描画
│   └── Utils.js        # 汎用ユーティリティ
└── assets/             # 将来的な画像・音声ファイル
```

## 開発環境

### 改行コード
このプロジェクトでは、すべてのテキストファイルで**LF（Line Feed）**改行コードを使用しています。

- **改行コード**: LF (`\n`)
- **設定ファイル**: `.gitattributes`で統一
- **理由**: クロスプラットフォームでの一貫性とGitでの差分管理の向上

### 推奨エディタ設定
- **VSCode**: `"files.eol": "\n"`
- **Sublime Text**: `"default_line_ending": "unix"`
- **Atom**: `core.fileEncoding: "utf8"`

## 設計原則

### 単一責任の原則 (Single Responsibility Principle)
各クラスは明確に定義された1つの責任のみを持ちます：

- **Game**: ゲーム全体の統合とメインループ制御
- **GameState**: ゲーム状態とスコア管理
- **Timer**: タイマー機能の管理
- **InputManager**: キーボード・マウス入力の処理
- **RenderManager**: 描画処理の管理
- **CollisionManager**: 衝突判定の処理
- **EnemyManager**: 敵の生成・管理
- **ParticleManager**: パーティクルエフェクトの管理
- **UIManager**: UI要素の管理
- **PauseManager**: ポーズ機能の管理
- **AttackManager**: 攻撃処理の管理
- **CameraManager**: カメラ（スクロール）の管理
- **AmmoManager**: 弾薬の管理

### モジュラー設計
- 各マネージャーは独立して動作
- 依存関係が明確
- テストしやすい構造
- 拡張しやすい設計

## ゲーム機能

- WASDキーでプレイヤー移動
- マウスクリックで攻撃
- Pキーでポーズ/再開
- Hキーでヘルプ表示（ポーズ中のみ）
- 時間制限（5分）
- スコアシステム
- パーティクルエフェクト

## 技術仕様

- **言語**: JavaScript (ES6+)
- **モジュール**: ES6 Modules
- **描画**: HTML5 Canvas
- **アーキテクチャ**: モジュラー設計
- **原則**: 単一責任の原則
- **改行コード**: LF (Unix形式) 
