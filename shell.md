# shell的类型
bash
zsh
sh

# 查看当前shell类型
echo $SHELL

# 切换shell类型
chsh -s <shell_path>
chsh -s /bin/bash
chsh -s /bin/zsh
chsh -s /bin/sh

# 各种shell对应的配置文件
bash --> ~/.bash_profile
zsh --> ~/.zshrc
sh --> ~/.profile