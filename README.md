
# AudioSR：大规模的多功能音频超分辨率

[![arXiv](https://img.shields.io/badge/arXiv-2309.07314-brightgreen.svg?style=flat-square)](https://arxiv.org/abs/2309.07314)  [![githubio](https://img.shields.io/badge/GitHub.io-Audio_Samples-blue?logo=Github&style=flat-square)](https://audioldm.github.io/audiosr) [![Replicate](https://replicate.com/nateraw/audio-super-resolution/badge)](https://replicate.com/nateraw/audio-super-resolution)

传入您的音频，AudioSR 将使其具有高保真度！

处理所有类型的音频（例如，音乐、语音、狗、雨声等）和所有采样率。

在我们的 discord 频道中分享您的想法/样本/问题： https://discord.gg/HWeBsJryaf

![Image Description](https://github.com/haoheliu/versatile_audio_super_resolution/blob/main/visualization.png?raw=true)

## 更新日志
- 2023-09-24: 添加复制演示 （@nateraw）;修复 Windows 上的错误、librosa 警告等 （@ORI-Muchim）。 
- 2023-09-16: 修复 DC 移位问题。修复持续时间填充错误。将默认 DDIM 步长更新为 50。

## Gradio 演示

要在本地运行 Gradio 演示：

1. 安装依赖项：`pip install -r requirements.txt` 
2. 运行应用程序：`python app.py`
3. 打开显示的 URL 以查看演示

## 命令行用法

## 安装
```shell
# 自选
conda create -n audiosr python=3.9; conda activate audiosr
# 安装 AudioLDM
pip3 install audiosr==0.0.7
# 或者
# pip3 install git+https://github.com/haoheliu/versatile_audio_super_resolution.git
```

## 用法

处理文件列表，默认情况下，结果将保存在 ./output 中。

```shell
audiosr -il batch.lst
```

处理单个音频文件。
```shell
audiosr -i example/music.wav
```

完整使用说明

```shell
> audiosr -h

> usage: audiosr [-h] -i INPUT_AUDIO_FILE [-il INPUT_FILE_LIST] [-s SAVE_PATH] [--model_name {basic,speech}] [-d DEVICE] [--ddim_steps DDIM_STEPS] [-gs GUIDANCE_SCALE] [--seed SEED]

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT_AUDIO_FILE, --input_audio_file INPUT_AUDIO_FILE
                        Input audio file for audio super resolution
  -il INPUT_FILE_LIST, --input_file_list INPUT_FILE_LIST
                        A file that contains all audio files that need to perform audio super resolution
  -s SAVE_PATH, --save_path SAVE_PATH
                        The path to save model output
  --model_name {basic,speech}
                        The checkpoint you gonna use
  -d DEVICE, --device DEVICE
                        The device for computation. If not specified, the script will automatically choose the device based on your environment.
  --ddim_steps DDIM_STEPS
                        The sampling step for DDIM
  -gs GUIDANCE_SCALE, --guidance_scale GUIDANCE_SCALE
                        Guidance scale (Large => better quality and relavancy to text; Small => better diversity)
  --seed SEED           Change this value (any integer number) will lead to a different generation result.
  --suffix SUFFIX       Suffix for the output file
```


## TODO
[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/haoheliuP)

- [ ] 添加Gradio测试版
- [ ] 优化推理速度

## 引用我们的工作
如果您觉得此存储库有用，请考虑引用：
```bibtex
@article{liu2023audiosr,
  title={{AudioSR}: Versatile Audio Super-resolution at Scale},
  author={Liu, Haohe and Chen, Ke and Tian, Qiao and Wang, Wenwu and Plumbley, Mark D},
  journal={arXiv preprint arXiv:2309.07314},
  year={2023}
}
```
