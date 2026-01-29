# Retrieval-based-Voice-Conversion-WebUI

このリポジトリは <https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI> を研究室で使用するためのフォークです。

## 環境構築

Python 環境は uv で，事前学習の重みは git-lfs でそれぞれ管理しています。
また本リポジトリではオリジナルと異なり CUDA 環境のみを想定し，ROCm・CPU 環境は想定していません。

```sh
$ uv --version
uv 0.9.26
```

```sh
$ git lfs --version
git-lfs/3.0.2 (GitHub; linux amd64; go 1.18.1)
```

### Python 依存関係のインストール

```sh
uv sync
```

### ffmpeg のインストール

ffmpeg と ffprobe が既にインストールされている場合はスキップします。

```sh
$ ffmpeg -version
ffmpeg version 4.4.2-0ubuntu0.22.04.1 Copyright (c) 2000-2021 the FFmpeg developers...

$ ffprobe -version
ffprobe version 4.4.2-0ubuntu0.22.04.1 Copyright (c) 2007-2021 the FFmpeg developers...
```

#### Ubuntu/Debian ユーザー

```bash
sudo apt install ffmpeg
```

#### MacOS ユーザー

```zsh
brew install ffmpeg
```

#### Windows ユーザー

```pwsh
winget install Gyan.FFmpeg
```

### 3. RMVPE 人間の声のピッチ抽出アルゴリズムに必要なファイルのダウンロード

最新の RMVPE 人間の声のピッチ抽出アルゴリズムを使用する場合、ピッチ抽出モデルのパラメータをダウンロードして RVC のルートディレクトリに配置する必要があります。

- [rmvpe.pt をダウンロード](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/rmvpe.pt)

## 使用開始

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

![Contributors to this repo, including those from the original repository.](https://contrib.rocks/image?repo=FMS-Morise-Lab/Retrieval-based-Voice-Conversion-WebUI)

Made with [contrib.rocks](https://contrib.rocks).
