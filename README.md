# AR画像表示アプリ

ARマーカーを使用して画像を表示するWebアプリケーションです。

## 必要なファイル

- `images/armarker.png` - ARマーカー画像
- `images/obake01.png` - 表示する画像

## セットアップ

### 1. 依存関係のインストール（オプション）

```bash
npm install
```

### 2. マーカーパターンファイルの生成

AR.jsで使用するには、マーカー画像からパターンファイル（.patt）を生成する必要があります。

以下の手順で生成できます：

1. [AR.js Marker Training](https://jeromeetienne.github.io/AR.js/three.js/examples/marker-training/examples/generator.html) にアクセス
2. `images/armarker.png` をアップロード
3. 生成された `.patt` ファイルをダウンロード
4. `images/armarker.patt` として保存

または、コマンドラインツールを使用：

```bash
# AR.js marker generator を使用
# https://github.com/AR-js-org/AR.js/tree/master/tools/marker-training
```

### 3. アプリの起動

#### 方法1: npmスクリプトを使用

```bash
npm start
```

ブラウザで `http://localhost:8080` を開きます。

#### 方法2: 直接HTTPサーバーを起動

```bash
npx http-server -p 8080 -c-1
```

#### 方法3: Pythonを使用（Python 3の場合）

```bash
python3 -m http.server 8080
```

## 使い方

1. アプリを起動してブラウザで開く
2. カメラのアクセス許可を許可する
3. `images/armarker.png` を印刷するか、別のデバイスの画面に表示する
4. カメラをマーカーに向けると、`obake01.png` が表示されます

## 注意事項

- HTTPSまたはlocalhostで実行する必要があります（カメラアクセスのため）
- マーカーは十分な明るさとコントラストが必要です
- マーカーは平らな面に置き、カメラから適切な距離（30-50cm）を保ってください

## 技術スタック

- [A-Frame](https://aframe.io/) - WebVR/ARフレームワーク
- [AR.js](https://ar-js-org.github.io/AR.js-Docs/) - WebベースのARライブラリ

