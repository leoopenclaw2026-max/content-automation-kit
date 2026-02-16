# 🎨 Content Automation Kit

> Plug-and-play templates for automating social media content creation, scheduling, and engagement.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Node.js 18+](https://img.shields.io/badge/node-18+-green.svg)](https://nodejs.org/)

Stop manually managing social media. Automate content generation, scheduling, and engagement with clean, extensible code.

## ✨ What You Get

- **📝 Text Generation** - Templates for creating platform-optimized posts
- **🖼️ Image Creation** - Automated image generation and editing workflows
- **🎬 Video Production** - Programmatic video templates (FFmpeg, Remotion, Motion Canvas)
- **📅 Smart Scheduling** - Cron-based content scheduling with timezone support
- **💬 Engagement Automation** - Poll-based comment/DM responses with deduplication
- **📊 Analytics Tracking** - Simple metrics collection and reporting

## 🚀 Quick Start

```bash
# Clone the repo
git clone https://github.com/leoopenclaw2026-max/content-automation-kit.git
cd content-automation-kit

# Install Python dependencies
pip install -r requirements.txt

# Install Node.js dependencies (for video generation)
npm install

# Copy and configure your environment
cp .env.example .env
# Edit .env with your API keys

# Run the example
python examples/basic_post_generator.py
```

## 📁 Project Structure

```
content-automation-kit/
├── src/
│   ├── content/          # Content generation modules
│   ├── video/            # Video creation tools
│   ├── social/           # Platform integrations (Meta, Twitter/X, LinkedIn)
│   ├── scheduling/       # Cron and queue management
│   └── utils/            # Shared utilities
├── templates/            # Reusable templates
│   ├── posts/            # Text post templates
│   ├── images/           # Image composition templates
│   └── videos/           # Video project templates
├── examples/             # Working examples
├── tests/                # Test suite
└── docs/                 # Documentation
```

## 🛠️ What's Included

### Content Generation
- `TextGenerator` - AI-powered post creation with platform-specific formatting
- `ImageComposer` - Layer-based image generation with templates
- `VideoRenderer` - Timeline-based video production

### Platform Integrations
- **Meta (Facebook/Instagram)** - Graph API wrapper with polling support
- **Twitter/X** - v2 API integration
- **LinkedIn** - REST API for posts and engagement

### Scheduling & State
- JSON-based state tracking (replied comments, sent DMs)
- Cron-based polling architecture
- Rate limiting and retry logic

## 💡 Example Use Cases

**Daily Motivation Posts**
```python
from src.content import TextGenerator, ImageComposer
from src.scheduling import Scheduler

gen = TextGenerator(style="motivational")
img = ImageComposer(template="gradient-quote")
scheduler = Scheduler(platforms=["instagram", "twitter"])

content = gen.create(theme="morning motivation")
image = img.render(text=content.text, background="sunrise.jpg")
scheduler.post(content=content, image=image, time="08:00")
```

**Auto-Reply to Comments**
```python
from src.social.meta import MetaManager

meta = MetaManager(page_id="123456", access_token="...")
comments = meta.poll_comments(since="30m ago")

for comment in comments:
    if not meta.already_replied(comment.id):
        reply = generate_reply(comment.text)
        meta.reply_to(comment.id, reply)
```

## 🤝 Contributing

This is a community project. Contributions welcome!

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Areas We Need Help

- [ ] Additional platform integrations (TikTok, YouTube, Pinterest)
- [ ] More video templates (Manim, Motion Canvas)
- [ ] Content analytics dashboard
- [ ] Multilingual content support
- [ ] Better documentation and tutorials

## 📜 License

MIT License - see [LICENSE](LICENSE) for details.

## 🙏 Acknowledgments

Built with:
- [FFmpeg](https://ffmpeg.org/) - Video processing
- [Remotion](https://www.remotion.dev/) - React-based video
- [Manim](https://www.manim.community/) - Mathematical animations
- [Motion Canvas](https://motioncanvas.io/) - Procedural animation

---

**Star ⭐ this repo if you find it useful!**

Built by an AI agent, maintained by the community.
