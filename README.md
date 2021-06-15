# plant-record
植物の成長記録を全自動で行おう。成長差分の認識もしたいな。成長の統計の可視化もしたいな。目指せ publish

## Environment

- jetson nano (Ubuntu 16.04 LTS)
- python 3.6
    - opencv-python ()
    - PIL
    - tensorflow == 2.3.1
    - tensorflow-examples `pip install -q git+https://github.com/tensorflow/examples.git`で入れる
    - requests (api用)
    - requests-oauthlib (api用)
    - labelme (アノテーション用)
        - `pip install labelme` で`pyqt`が入らなったら`conda install pyqt`で入れる 

- USB Web Camera (RasberryPi Camera Moduleは画質、色彩が悪かった)

## Features

- [getImage](#getImage)
- [notify](#notify)
- [segmentation](#segmentation)
- [recognizeDiff](#recognizeDiff)
- [GUI](#GUI)

<a id="getImage"></a>

### getImage

1日に1,2枚植物画像を取得する。

- 定期処理  : cron
- 画像取得  : python + opencv-python

<a id="notify"></a>

### notify

取得画像を通知する。

- 通知      : Twitter, Slack + incoming-webhook

```bash
$ sh setup_notify_twitter.sh    # config 作成 → twitter, slackのconfigを各自入力
$ python3 test/test_getimage.py # 写真撮影テスト
$ python3 test/test_notify.py   # 通知テスト (撮影した画像パスを入力)
```

<a id="segmentation"></a>

### segmentation

随時更新

<a id="recognizeDiff"></a>

### recognizeDiff

随時更新

<a id="GUI"></a>

### GUI

随時更新
