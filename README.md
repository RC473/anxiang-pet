# 安巷宠物医院 · 一个伪装成小诊所官网的 ARG

表面上是一家再普通不过的社区宠物医院官网——首页、关于我们、医生团队、服务项目、环境展示、领养信息、公告栏、联系我们，什么都有，唯独没有"游戏"两个字。

线索都藏在看起来最不起眼的地方：某位医生简介里一个不显眼的词、公告栏最后一条通知里一句顺嘴带过的话、一张说是"旧硬盘里翻出来的"照片、`robots.txt` 里两行本该被忽略的路径、还有这个仓库自己的提交记录。全程没有"输入答案"这种游戏化的界面，找到就是找到了，找不到，就当真的是一家普通诊所的官网。

对照参考风格：这是一个可以直接部署在 **GitHub Pages** 上的中文 ARG，全站约18个页面，规模适中，没有强制的通关校验机制，纯靠探索和眼力。

## 怎么玩

从首页开始，像逛一个真的小诊所网站一样正常逛：看看医生、翻翻公告、看看有没有能领养的猫狗。

- 别的什么都不用做，认真读就行。有些不起眼的词、不太寻常的一句话，可能就是入口。
- 有几关会用到一些基础的编码/密码知识（凯撒密码、Atbash、摩斯电码、Base64、十六进制、栅栏密码），网上都能查到对照表。
- 这个网站本身也是一份"病历"——它有自己的提交历史，认真翻一翻。

## 部署到 GitHub Pages

1. 新建一个 Public 仓库。
2. 推送本项目（**保留提交历史，不要 squash**，这是线索的一部分）：
   ```bash
   git remote add origin https://github.com/<你的用户名>/<仓库名>.git
   git branch -M main
   git push -u origin main
   ```
3. 仓库 Settings → Pages，Source 选 `main` 分支，目录选 `/docs`，保存。
4. 稍等片刻即可通过 `https://<你的用户名>.github.io/<仓库名>/` 访问。

## 目录结构

```
.
├── docs/                    ← GitHub Pages 发布目录（表面上的诊所官网）
│   ├── index.html / about.html / doctors.html / services.html
│   ├── gallery.html / adopt.html / contact.html
│   ├── announcements.html + ann-01~06.html   ← 公告栏
│   ├── notes/note-01~07.html                  ← 隐藏支线（需要自己找入口）
│   ├── ex-01.html / old-site-backup.html      ← 彩蛋页面
│   ├── 404.html / robots.txt
│   └── assets/corridor.png                    ← 藏有隐写信息的照片
├── tools/decode_lsb.py       ← 图片隐写解码工具（不在网站上被链接）
└── README.md
```

祝好运。别太快翻到3号观察室柜子最里面。
