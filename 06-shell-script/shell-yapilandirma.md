# Shell Yapılandırması ve Alias Kullanımı

Shell yapılandırma dosyaları ve alias'lar, terminal deneyiminizi kişiselleştirmenize ve daha verimli çalışmanıza olanak sağlar.

## 📚 İçerik

1. [Shell Yapılandırma Dosyaları](#shell-yapılandırma-dosyaları)
2. [Alias Kullanımı](#alias-kullanımı)
3. [Ortam Değişkenleri](#ortam-değişkenleri)
4. [Path Yapılandırması](#path-yapılandırması)
5. [Örnekler ve İyi Uygulamalar](#örnekler-ve-i̇yi-uygulamalar)

## Shell Yapılandırma Dosyaları

### .bashrc

```bash
# ~/.bashrc dosyası
# Bash shell için kişisel yapılandırmalar

# Renkli terminal çıktısı
export CLICOLOR=1
export LSCOLORS=GxFxCxDxBxegedabagaced

# Terminal görünümünü özelleştirme
PS1='\u@\h:\w\$ '

# Geçmiş ayarları
HISTSIZE=1000
HISTFILESIZE=2000
HISTCONTROL=ignoredups:ignorespace
```

### .zshrc

```bash
# ~/.zshrc dosyası
# Zsh shell için kişiselleştirmeler

# Oh-My-Zsh kullanımı
export ZSH="$HOME/.oh-my-zsh"
ZSH_THEME="robbyrussell"

# Eklentiler
plugins=(
    git
    docker
    zsh-autosuggestions
    zsh-syntax-highlighting
)

source $ZSH/oh-my-zsh.sh

# Özel yapılandırmalar
COMPLETION_WAITING_DOTS="true"
```

### .bash_profile / .zprofile

```bash
# ~/.bash_profile veya ~/.zprofile
# Login shell için yapılandırmalar

# Sistem geneli PATH ayarları
export PATH=$HOME/bin:/usr/local/bin:$PATH

# Dil ayarları
export LANG=tr_TR.UTF-8
export LC_ALL=tr_TR.UTF-8
```

## Alias Kullanımı

### Temel Alias Tanımlamaları

```bash
# Genel kullanım
alias ll='ls -la'
alias la='ls -A'
alias l='ls -CF'

# Gezinme kısayolları
alias ..='cd ..'
alias ...='cd ../..'
alias desktop='cd ~/Desktop'
alias downloads='cd ~/Downloads'

# Sistem kısayolları
alias update='sudo apt update && sudo apt upgrade'
alias ports='netstat -tulanp'
alias mem='free -h'
alias cpu='top -o cpu'
```

### Git Alias'ları

```bash
# Git kısayolları
alias gs='git status'
alias ga='git add'
alias gc='git commit -m'
alias gp='git push'
alias gl='git log --oneline'
alias gd='git diff'
alias gb='git branch'
alias gco='git checkout'
```

### Docker Alias'ları

```bash
# Docker kısayolları
alias d='docker'
alias dc='docker-compose'
alias dps='docker ps'
alias di='docker images'
alias dex='docker exec -it'
alias dlog='docker logs'
```

## Ortam Değişkenleri

```bash
# Genel ortam değişkenleri
export EDITOR='vim'
export VISUAL='code'
export BROWSER='firefox'

# Geliştirici ortam değişkenleri
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk
export ANDROID_HOME=$HOME/Android/Sdk
export NODE_ENV=development
```

## Path Yapılandırması

```bash
# PATH eklemeleri
export PATH=$PATH:$HOME/.local/bin
export PATH=$PATH:$JAVA_HOME/bin
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/platform-tools

# Özel script dizini
export PATH=$PATH:$HOME/scripts
```

## Örnekler ve İyi Uygulamalar

### Fonksiyon Tanımlama

```bash
# Dizin oluştur ve içine git
mkcd() {
    mkdir -p "$1" && cd "$1"
}

# Git add, commit ve push tek komutta
gitt() {
    git add .
    git commit -m "$1"
    git push
}

# Dosya ara ve içinde kelime ara
ftext() {
    find . -name "$1" -exec grep -l "$2" {} \;
}
```

### Koşullu Alias'lar

```bash
# İşletim sistemine göre alias'lar
if [[ "$OSTYPE" == "darwin"* ]]; then
    # macOS için alias'lar
    alias showfiles='defaults write com.apple.finder AppleShowAllFiles YES'
    alias hidefiles='defaults write com.apple.finder AppleShowAllFiles NO'
elif [[ "$OSTYPE" == "linux-gnu"* ]]; then
    # Linux için alias'lar
    alias open='xdg-open'
    alias pbcopy='xclip -selection clipboard'
    alias pbpaste='xclip -selection clipboard -o'
fi
```

### Güvenlik Önlemleri

```bash
# Tehlikeli komutlar için güvenlik
alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'

# Sudo kullanımı için alias
alias sudo='sudo '  # Alias'ların sudo ile çalışmasını sağlar
```

### Verimlilik Artırıcı Alias'lar

```bash
# Hızlı düzenleme
alias eb='$EDITOR ~/.bashrc'
alias ez='$EDITOR ~/.zshrc'
alias sz='source ~/.zshrc'
alias sb='source ~/.bashrc'

# Sistem bilgisi
alias sysinfo='echo "$(uname -a) | $(lsb_release -a)"'
alias diskspace='df -h'
alias foldersize='du -sh'
alias ports='netstat -tulanp'
```

------   
<br>
<br>
<br>
<div align="center">

[🏠AnaSayfa](../README.md) • [📑Bölüm](README.md) 

</div>