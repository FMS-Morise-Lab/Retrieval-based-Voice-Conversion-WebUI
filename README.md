# Retrieval-based-Voice-Conversion-WebUI

このリポジトリは <https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI> を研究室で使用するために最適化したフォークです。

## 環境構築

下記のコマンドは，uv 環境で実行する必要があります。
本リポジトリでは CUDA 環境のみを想定し，ROCm 環境は想定しません。

```sh
uv sync
```

## その他の事前訓練されたモデルの準備

RVC は推論とトレーニングのために他のいくつかの事前訓練されたモデルが必要です。

これらのモデルは私たちの[Hugging Face space](https://huggingface.co/lj1995/VoiceConversionWebUI/tree/main/)でダウンロードできます。

### 1. assets のダウンロード

以下は、RVC に必要なすべての事前学習モデルとその他のファイルのリストです。`tools`フォルダーにこれらをダウンロードするスクリプトがあります。

- ./assets/hubert/hubert_base.pt

- ./assets/pretrained

- ./assets/uvr5_weights

v2 バージョンのモデルを使用する場合、追加で以下をダウンロードする必要があります。

- ./assets/pretrained_v2

### 2. ffmpeg のインストール

ffmpeg と ffprobe が既にインストールされている場合はスキップします。

#### Ubuntu/Debian ユーザー

```bash
sudo apt install ffmpeg
```

#### MacOS ユーザー

```bash
brew install ffmpeg
```

#### Windows ユーザー

ダウンロード後、ルートディレクトリに配置してください。

- [ffmpeg.exe をダウンロード](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/ffmpeg.exe)

- [ffprobe.exe をダウンロード](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/ffprobe.exe)

### 3. RMVPE 人間の声のピッチ抽出アルゴリズムに必要なファイルのダウンロード

最新の RMVPE 人間の声のピッチ抽出アルゴリズムを使用する場合、ピッチ抽出モデルのパラメータをダウンロードして RVC のルートディレクトリに配置する必要があります。

- [rmvpe.pt をダウンロード](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/rmvpe.pt)

#### dml 環境の RMVPE をダウンロード(オプション、A カード/I カードユーザー)

- [rmvpe.onnx をダウンロード](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/rmvpe.onnx)

## 使用開始

### 直接起動

以下のコマンドで WebUI を起動します
```bash
python infer-web.py
```

## 参考プロジェクト

- [ContentVec](https://github.com/auspicious3000/contentvec/)
- [VITS](https://github.com/jaywalnut310/vits)
- [HIFIGAN](https://github.com/jik876/hifi-gan)
- [Gradio](https://github.com/gradio-app/gradio)
- [FFmpeg](https://github.com/FFmpeg/FFmpeg)
- [Ultimate Vocal Remover](https://github.com/Anjok07/ultimatevocalremovergui)
- [audio-slicer](https://github.com/openvpi/audio-slicer)
- [Vocal pitch extraction:RMVPE](https://github.com/Dream-High/RMVPE)
  - 事前訓練されたモデルは[yxlllc](https://github.com/yxlllc/RMVPE)と[RVC-Boss](https://github.com/RVC-Boss)によって訓練され、テストされました。

## すべての貢献者の努力に感謝します

<a href="https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/graphs/contributors" target="_blank">
  <img src="https://contrib.rocks/image?repo=RVC-Project/Retrieval-based-Voice-Conversion-WebUI" />
</a>
