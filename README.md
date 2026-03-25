# MiniMax Skills

将 MiniMax 开放平台的语音、图片、视频、音乐功能封装成 4 个独立的技能。

## 技能列表

| 技能 | 功能 |
|------|------|
| minimax-speech | 语音合成、克隆、设计 |
| minimax-image | 图片生成、编辑 |
| minimax-video | 视频生成 |
| minimax-music | 音乐生成 |

## 环境配置

```bash
export MINIMAX_API_KEY="your-api-key"
export MINIMAX_REGION="cn"  # cn=国内, int=国际
```

### 依赖

```bash
pip install requests
```

## 安装

首先克隆项目：
```bash
git clone <repo-url>
cd minimax-skills
```

### Claude Code

```bash
# 复制技能
cp -r minimax-skills/* ~/.claude/skills/
```

### OpenClaw

```bash
mkdir -p ~/.openclaw/skills
cp -r minimax-skills/* ~/.openclaw/skills/
```

配置 API Key：
```bash
# .env 文件
MINIMAX_API_KEY=your-api-key
MINIMAX_REGION=cn
```

---

## minimax-speech

语音合成、克隆和设计技能。

### 功能

- **同步语音合成**：短文本快速转语音，直接返回音频
- **异步语音合成**：长文本异步处理，返回任务ID
- **音色克隆**：上传参考音频，快速复刻相似音色
- **音色设计**：通过文字描述设计全新音色
- **音色管理**：查询、删除已创建的音色

### 支持的音色

- female-tianmei（女声甜美）
- male-yunyang（男声播音）
- female-badu（女声巴度）

### Claude Code / OpenClaw 使用

```
/minimax-speech
```

或对话中调用：
```
帮我用 minimax-speech 生成一段语音："你好世界"
用 minimax-speech 克隆音色：从 audio.wav 克隆一个"我的音色"
```

---

## minimax-image

图片生成和编辑技能。

### 功能

- **文生图**：根据文本描述生成图片
- **图生图**：上传参考图，结合文字描述生成新图片
- **多种宽高比**：1:1、16:9、9:16、4:3、3:4
- **直接保存**：自动下载图片到本地

### Claude Code / OpenClaw 使用

```
/minimax-image
```

或对话中调用：
```
用 minimax-image 生成一张图片：一只可爱的橘猫在阳光下打盹
用 minimax-image 生成一张16:9的风景图：日出时分的大海
用 minimax-image 编辑图片：把这只猫变成老虎
```

---

## minimax-video

视频生成技能。

### 功能

- **文生视频**：根据文本描述生成视频
- **图生视频**：上传参考图，让图片动起来
- **首尾帧视频**：上传起始帧和结束帧，生成过渡动画
- **主体参考视频**：上传人物主体，生成动态效果
- **自动下载**：生成完成后自动保存到本地

### 视频规格

- 默认生成 5 秒视频
- 分辨率 1280x720 (720P)
- 格式 MP4

### Claude Code / OpenClaw 使用

```
/minimax-video
```

或对话中调用：
```
用 minimax-video 生成一个视频：海浪拍打沙滩
用 minimax-video 从图片生成视频：使用 cat.jpg 让它动起来
用 minimax-video 生成首尾帧视频：从 start.jpg 到 end.jpg
```

---

## minimax-music

音乐生成和歌词创作技能。

### 功能

- **音乐生成**：根据歌词和描述生成完整音乐
- **歌词生成**：根据描述和关键词自动创作歌词
- **同步生成**：直接返回音频数据，无需等待
- **多种风格**：流行、摇滚、民谣、电子等

### 歌词格式

支持分段标记：
- [verse] 主歌
- [chorus] 副歌/高潮
- [bridge] 桥段
- [intro] 前奏
- [outro] 尾奏

### Claude Code / OpenClaw 使用

```
/minimax-music
```

或对话中调用：
```
用 minimax-music 生成一首关于梦想的歌
用 minimax-music 生成歌词：关于夏天的歌，关键词：阳光、沙滩、海浪
```

---

## 项目结构

```
minimax/
├── .claude/skills/
│   ├── minimax-speech/     # 语音技能
│   ├── minimax-image/     # 图片技能
│   ├── minimax-video/     # 视频技能
│   └── minimax-music/     # 音乐技能
└── README.md
```

每个技能包含：
- `SKILL.md` - 技能指令
- `scripts/` - Python 实现
- `references/` - API 参考

---

## API 配置

| 配置项 | 国内 | 国际 |
|--------|------|------|
| Base URL | `https://api.minimaxi.com/v1` | `https://api.minimax.io/v1` |

---


## 友链

- [Linux.do](https://linux.do) 

## 联系与支持

<div style="display:flex;gap:20px;">
  <div style="text-align:center;">
    <img src="assets/个人微信.jpg" width="300"/>
    <p>个人微信</p>
  </div>
  <div style="text-align:center;">
    <img src="assets/交流群.jpg" width="300"/>
    <p>交流群</p>
  </div>
  <div style="text-align:center;">
    <img src="assets/赞赏码.jpg" width="300"/>
    <p>赞赏码</p>
  </div>
</div>
