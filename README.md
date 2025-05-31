# audio-to-srt-siliconflow-api
将音频文件转换为SRT字幕文件的html客户端应用，使用siliconflow的api


# 音频转SRT字幕 (客户端工具)

这是一个纯客户端的Web工具，可以将本地音频文件转换为SRT格式的字幕文件。它利用浏览器的Web Audio API进行音频处理和VAD（语音活动检测），并通过调用硅基流动 (SiliconFlow) API 进行语音识别。

https://cloud.siliconflow.cn/account/ak
你可以从这里得到硅基流动的key，这个接口目前是免费的，不会消耗key的额度。

灵感来源https://linux.do/t/topic/691182/4

**安全警告：在浏览器 (localStorage) 中存储 API 密钥是不安全的，仅适用于您是唯一用户的个人本地工具。请勿在可公开访问的 Web 应用程序中使用此方法。**

## 功能特性

*   纯HTML、CSS、JavaScript实现，无需后端服务器（API调用除外）。
*   在浏览器端进行音频解码和VAD处理。
*   支持常见的音频格式 (WAV, MP3, AAC, M4A, OGG, FLAC等)。
*   调用硅基流动 (SiliconFlow) API 进行语音转文字。
*   可自定义VAD参数（最小静音长度、静音阈值等）。
*   自动生成 `.srt` 字幕文件并触发下载。
*   支持中英文界面切换。

## 如何使用

1.  下载本仓库中的 `audio_to_srt_tool.html` 文件，或通过 `git clone https://github.com/你的用户名/你的仓库名.git` 克隆整个仓库。
2.  使用现代浏览器 (如 Chrome, Firefox, Edge) 打开 `audio_to_srt_tool.html` 文件。
3.  在“配置”部分输入你的有效“硅基流动 API 密钥”和“模型名称”（例如 `FunAudioLLM/SenseVoiceSmall`）。API密钥会存储在浏览器的 localStorage 中，仅供本地使用。
4.  点击“选择一个音频文件”按钮，选择你要处理的音频。
5.  （可选）展开“VAD 参数”调整参数。
6.  点击“处理音频并生成 SRT”按钮。
7.  处理过程和状态会显示在状态区域。完成后，SRT文件会自动开始下载。

## 许可证 (License)

本项目采用 [MIT License](LICENSE) 开源。

