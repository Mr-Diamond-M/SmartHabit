<div align="center">

  <img src="../images/Logo.png" width="180" alt="dmd-core-logo" />
  
  # スマートホームIoTシステム
  **設計・開発：dmd-core**

![ESP32](https://img.shields.io/badge/ESP32-IoT-blue)
![Blynk](https://img.shields.io/badge/Blynk-Cloud-green)
![Arduino](https://img.shields.io/badge/Arduino-C++-00979D)
![Wokwi](https://img.shields.io/badge/Wokwi-Simulation-orange)
![License](https://img.shields.io/badge/License-MIT-red)
</div>

ESP32、Blynk Cloud、および Wokwi シミュレーターを使用して構築された IoT ベースのスマートホーム自動化システムです。

本プロジェクトは、インターネット経由で家庭用機器を遠隔操作するための IoT 技術の実践的な活用例を示しています。ESP32 マイクロコントローラを中心に、Blynk クラウドプラットフォームを利用して照明、暖房、および冷房システムを制御します。

システム全体は Wokwi 上で設計・検証されているため、物理ハードウェアを用意しなくても学習、実験、およびデモンストレーションが可能です。

---

# 📚 目次

* プロジェクト概要
* 主な機能
* システムアーキテクチャ
* 使用技術
* ハードウェア構成
* ソフトウェア要件
* GPIO設定
* 回路設計
* インストールガイド
* Blynk設定
* Wokwiシミュレーション
* ソースコード解説
* 動作原理
* テスト手順
* トラブルシューティング
* セキュリティに関する注意事項
* 今後の改善点
* プロジェクトレポート
* レポート言語
* 著者
* ライセンス
* 謝辞

---

# 📌 プロジェクト概要

本プロジェクトの目的は、ESP32 マイクロコントローラを使用したシンプルで拡張可能なスマートホーム制御システムを構築することです。

システムは以下の3つの主要な家庭設備を制御します。

* 💡 照明システム
* 🔥 暖房システム
* ❄️ 冷房システム

ユーザーは Blynk モバイルアプリケーションを使用して、インターネット経由で各デバイスをリアルタイムに制御できます。

本プロジェクトは以下の学習分野に適しています。

* Internet of Things（IoT）
* クラウド通信
* 組み込みシステム
* ESP32 開発
* スマートホーム技術
* モバイルダッシュボード設計

---

# ✨ 主な機能

* スマートフォンからの遠隔操作
* Blynk Cloud によるリアルタイム通信
* ESP32 の Wi-Fi 接続
* クラウドベースのデバイス制御
* モジュール化されたファームウェア設計
* Wokwi シミュレーション対応
* 拡張可能なアーキテクチャ
* 初心者にも理解しやすい実装
* IoT 学習向けプロジェクト
* 将来的な機能拡張に対応

---

# 🏗 システムアーキテクチャ

```text
ユーザー
   │
   ▼
Blynk モバイルアプリ
   │
   ▼
Blynk Cloud
   │
   ▼
ESP32
 ├── 照明システム
 ├── 暖房システム
 └── 冷房システム
```

### データフロー

1. ユーザーが Blynk アプリのスイッチを操作します。
2. コマンドが Blynk Cloud に送信されます。
3. Blynk Cloud が ESP32 にコマンドを転送します。
4. ESP32 がコマンドを処理します。
5. 対応する GPIO の状態が変更されます。
6. 接続されたデバイスが動作します。

---

# 🛠 使用技術

| カテゴリ         | 技術                |
| ------------ | ----------------- |
| マイクロコントローラ   | ESP32             |
| プログラミング言語    | C++               |
| 開発フレームワーク    | Arduino Framework |
| IoT プラットフォーム | Blynk Cloud       |
| 通信方式         | Wi-Fi             |
| シミュレーション     | Wokwi             |
| バージョン管理      | Git               |
| リポジトリ管理      | GitHub            |

---

# 🔧 ハードウェア構成

| コンポーネント     | 数量 |
| ----------- | -- |
| ESP32 開発ボード | 1  |
| LED         | 3  |
| 220Ω 抵抗     | 3  |
| ジャンパーワイヤ    | 数本 |

---

# 💻 ソフトウェア要件

以下のソフトウェアを事前にインストールしてください。

* Arduino IDE
* ESP32 Board Package
* Blynk Library
* Wokwi アカウント
* Blynk モバイルアプリ
* Git（任意）

---

# 📍 GPIO設定

| 機能 | GPIO   |
| -- | ------ |
| 照明 | GPIO23 |
| 暖房 | GPIO22 |
| 冷房 | GPIO21 |

---

# 🔌 回路設計

本プロジェクトでは各設備を LED で表現しています。

### 照明

GPIO23 → 抵抗 → LED → GND

### 暖房

GPIO22 → 抵抗 → LED → GND

### 冷房

GPIO21 → 抵抗 → LED → GND

---

# 📸 プロジェクト画像

## 回路図

<img src="../images/circuit.png" width="180" alt="dmd-core-logo" />

## Blynk ダッシュボード

<img src="../images/dashboard.png" width="180" alt="dmd-core-logo" />

---

# 🚀 インストールガイド

## ステップ 1: Arduino IDE のインストール

Arduino IDE の最新版をダウンロードしてインストールしてください。

---

## ステップ 2: ESP32 ボードパッケージのインストール

以下を開きます。

```text
Tools → Board Manager
```

検索欄で「ESP32」を検索し、最新版をインストールしてください。

---

## ステップ 3: Blynk ライブラリのインストール

Library Manager を開き、「Blynk」を検索して最新版をインストールしてください。

---

## ステップ 4: リポジトリをクローン

```bash
git clone https://github.com/Dmd-core/SmartHome-ESP32.git
```

---

## ステップ 5: プロジェクトを開く

Arduino IDE で以下のファイルを開きます。

```text
sketch.ino
```

---

## ステップ 6: 認証情報の設定

以下のプレースホルダーを自分の情報に置き換えてください。

```cpp
#define BLYNK_TEMPLATE_ID   "YOUR_TEMPLATE_ID"
#define BLYNK_TEMPLATE_NAME "Smart Home"
#define BLYNK_AUTH_TOKEN    "YOUR_AUTH_TOKEN"

char ssid[] = "YOUR_WIFI_NAME";
char pass[] = "YOUR_WIFI_PASSWORD";
```

---

## ステップ 7: ファームウェアの書き込み

ボードとして「ESP32 Dev Module」を選択し、プログラムを書き込みます。

---

# ☁️ Blynk設定

## テンプレート作成

1. Blynk Console にログイン
2. 新しいテンプレートを作成
3. ハードウェアとして ESP32 を選択
4. 接続方式として Wi-Fi を選択

---

## Datastream 作成

| 機能 | Virtual Pin |
| -- | ----------- |
| 照明 | V0          |
| 暖房 | V1          |
| 冷房 | V2          |

---

## ダッシュボード作成

3つの Switch ウィジェットを追加します。

* V0 → 照明
* V1 → 暖房
* V2 → 冷房

---

# 🖥 Wokwiシミュレーション

1. Wokwi を開く
2. プロジェクトファイルをインポート
3. シミュレーションを開始
4. Blynk Cloud と接続
5. アプリからデバイスを制御

---

# ⚙️ ソースコード解説

### 照明制御

```cpp
BLYNK_WRITE(V0)
{
    int state = param.asInt();
    digitalWrite(LAMP_PIN, state);
}
```

照明システムを制御します。

---

### 暖房制御

```cpp
BLYNK_WRITE(V1)
{
    int state = param.asInt();
    digitalWrite(HEATING_PIN, state);
}
```

暖房システムを制御します。

---

### 冷房制御

```cpp
BLYNK_WRITE(V2)
{
    int state = param.asInt();
    digitalWrite(COOLING_PIN, state);
}
```

冷房システムを制御します。

---

# 🔄 動作原理

1. ESP32 が Wi-Fi に接続します。
2. ESP32 が Blynk Cloud に接続します。
3. ユーザーがアプリからコマンドを送信します。
4. Blynk Cloud がコマンドを転送します。
5. GPIO の状態が変更されます。
6. 接続されたデバイスが動作します。

---

# 🧪 テスト手順

### テスト 1

照明を ON にする

期待結果:

照明 LED が点灯する

---

### テスト 2

暖房を ON にする

期待結果:

暖房 LED が点灯する

---

### テスト 3

冷房を ON にする

期待結果:

冷房 LED が点灯する

---

# 🔍 トラブルシューティング

### Wi-Fi に接続できない

確認事項:

* SSID
* パスワード
* インターネット接続

---

### Blynk がオフライン

確認事項:

* Auth Token
* Template ID
* インターネット接続

---

### LED が反応しない

確認事項:

* 配線
* GPIO 設定
* 電源供給

---

# 🔒 セキュリティに関する注意事項

GitHub に公開する前に以下の情報を削除してください。

* Wi-Fi パスワード
* Blynk Auth Token
* API キー
* その他の機密情報

必ずプレースホルダーを使用してください。

---

# 🚧 今後の改善点

* DHT22 温湿度センサーの追加
* 湿度監視機能
* 自動温度制御
* エネルギー消費モニタリング
* プッシュ通知機能
* 音声アシスタント連携
* データロギング
* TinyML の導入
* AI ベースの自動制御
* ホームセキュリティ機能

---

# 📄 プロジェクトレポート

![System Diagram](IoT.ja.pdf)

本レポートでは、以下の内容について説明します。

* プロジェクトの目的
* IoTの概念
* ESP32の設定
* Blynkとの連携
* 回路設計
* 実装の詳細

---

レポートには以下の内容が含まれます。

* プロジェクト目的
* IoT 概念
* ESP32 設定
* Blynk 統合
* 回路設計
* 実装詳細

---

### 🌐 ドキュメントポータル
技術ドキュメントをご覧になるには、言語を選択してください：

* GB **[English Documentation](../README.md)** — *English*
* IR **[Persian Documentation](README.fa.md)** — *فارسی*
* DE **[German Documentation](README.de.md)** — *tysk*
---

# 👨‍💻 著者

**Mohammad Hossein Almasi**

コンピュータ工学専攻

興味分野:

* Internet of Things (IoT)
* 組み込みシステム
* ESP32 開発
* 人工知能
* スマートホーム自動化

GitHub:

https://github.com/Dmd-core

---

# 📜 ライセンス

このプロジェクトはMITライセンスの下で公開されています。

以下の行為は自由に行えます。

* 使用
* 改変
* 配布
* 学習
* プロジェクトを基にした開発

教育および研究目的の場合に限ります。

---

# 🙏 謝辞

以下のコミュニティおよびプラットフォームに感謝いたします。

* ESP32 開発コミュニティ
* Blynk IoT Platform
* Wokwi Simulation Platform
* Arduino Open Source Community

これらのツールとリソースが本プロジェクトの実現に大きく貢献しました。

---

## ⭐ サポート

このプロジェクトが役に立った場合は、

⭐ リポジトリにスターを付ける

🍴 フォークする

📢 他の人に共有する

ことで応援していただけると幸いです。

ご覧いただきありがとうございました。

<div align="center">
  <br>
  <a href="dmd.core.dev@gmail.com">
    <img src="https://img.shields.io/badge/Email-000000?style=for-the-badge&logo=gmail&logoColor=white&logoWidth=20" alt="Email" />
  </a>
</div>
