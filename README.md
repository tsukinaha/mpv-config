# Linux MPV Config 自用   
操作系统 Archlinux    
MPV-Vapoursynth  
包含 mvtools Anime4K 一个lua  
## 预览 
![image.png](https://s2.loli.net/2023/10/17/eiQVHFqyukJv2mj.png)    
## 快速部署（包含 mpv-vapoursynth 安装）
```
sudo pacman -R mpv 
paru -S mpv-vapoursynth
sudo pacman -S vapoursynth-plugin-mvtools
mkdir ~/.config/mpv
cd ~/.config/mpv
git clone https://github.com/tsukinaha/mpv-config.git
cp -r mpv-config mpv
rm mpv-config
```
## 自行设置部分   

motioninterpolation.vpy 中 dst_fps = <补帧目标帧数，例如 60>   
mpv.conf 中 启动时应用补帧 加入这行 vf=format=yuv420p,vapoursynth=~~/motioninterpolation.vpy:4:4   
./script-opts/osc.conf 中修改 lua 缩放
```
scalewindowed=1.5 #修改为你想要的缩放倍数
scalefullscreen=1.5
scaleforcedwindow=1.5
``` 
