# Retrieval-based-Voice-Conversion-WebUI

このリポジトリは <https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI> を研究室で使用するためのフォークです。

## 環境構築

Python 環境は[【uv】](https://docs.astral.sh/uv/getting-started/installation/)で，事前学習の重みは[【git-lfs】](https://docs.github.com/ja/repositories/working-with-files/managing-large-files/installing-git-large-file-storage)でそれぞれ管理しています。
また本リポジトリではオリジナルと異なり CUDA 環境のみを想定し，ROCm 環境は想定していません (CPU は未検証)。
リポジトリに RVC の weights が含まれているため `git clone` に時間がかかりますが，気長に待ってください。

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

### ffmpeg・ffprobeのインストール

[【Winget (Windows)】](https://qiita.com/Tadataka_Takahashi/items/9dcb0cf308db6f5dc31b#%E6%96%B9%E6%B3%951-winget%E3%81%A7%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB),
[【HomeBrew (MacOS)】](https://formulae.brew.sh/formula/ffmpeg),
[【Apt (Debian, Ubuntu)】](https://packages.debian.org/trixie/ffmpeg)
などから FFmpeg を各自インストールしてください（ffprobe は ffmpeg をインストールすれば一緒にはいるはずです）。

```sh
$ ffmpeg -version
ffmpeg version 4.4.2-0ubuntu0.22.04.1 Copyright (c) 2000-2021 the FFmpeg developers...

$ ffprobe -version
ffprobe version 4.4.2-0ubuntu0.22.04.1 Copyright (c) 2007-2021 the FFmpeg developers...
```

## 使用開始

以下のコマンドで WebUI を起動します

```bash
uv run python infer-web.py
```

## 関連プロジェクト

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

以下のリストには元リポジトリへの貢献者も含まれます。

![Contributors to this repo, including those from the original repository.](https://contrib.rocks/image?repo=FMS-Morise-Lab/Retrieval-based-Voice-Conversion-WebUI)

Made with [contrib.rocks](https://contrib.rocks).
