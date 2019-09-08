> 本项目自`LoliLin/CloudMan`魔改而成

## 魔改思路

原本CloudMan项目下载的音乐都是以音乐ID命名的。其音乐名称写入了文件Metadata里面。但是有一些MP3或者车载中控无法识别并显示Matadata的歌名，或只能以文件名的形式来显示歌名，导致无法正常选歌。
其次，原项目的下载逻辑是将当前用户所有的（包括收藏）播放列表莽下来。这并不符合我的使用需求。

## 功能

- [x] 中文歌曲/词名
- [x] 下载单一播放列表
- [ ] 歌曲/词以歌手命名 

## 使用方法

1. 在 WalkMan 根目录输入 `git clone https://github.com/GiriNeko/Cloudwoman.git`
2. 进入 `CloudMan` 目录, 输入 `pip3 install -r requirements.txt`
3. 将 `config.example.ini` 重命名为 `config.ini` 并修改其中的 歌单ID和API 服务器地址
4. 输入 `python3 run.py` 即可


若有网易云会员推荐登录, 登录后可下载那些标了版权问题的歌曲和无损歌曲

下载线程数建议设置为 4 及 4 以下, 若超过 4 疑似会被强制断

## 已知BUG

<del>若歌名带有“/”则会下载失败</del> Fixed:替换"/"为空格

## 原理

播放列表：废除Config.ini中的UID条目，将“浙江共青团”的UID写死在run.py中（播放列表少，易排除。注释有写），然后再在config.ini中排除“浙江共青团”的个人歌单。
