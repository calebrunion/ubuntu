# Ubuntu Setup
1. Keep things updated. 
    ```
    sudo apt update && sudo apt upgrade -y && sudo apt autoremove -y
    ```
2. Install APT packages.
    ```
    sudo apt install git zsh curl trash-cli neofetch -y
    ```
3. You need a better CLI.
    ```
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
4. Make it even better with zsh-plugins.
    ```
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting \
    && git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    ```
    ```
    vi ~/.zshrc
    ```
    ```
    plugins=(git zsh-syntax-highlighting zsh-autosuggestions)
    ```
    ```
    source ~/.zshrc
    ```
5. [NVM](https://github.com/nvm-sh/nvm#installing-and-updating) makes life less hard.
    ```
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash \
    && source ~/.zshrc \
    && nvm install --lts \
    && node -v
    ```
6. You'll probably want SSH keys too.
    ```
    ssh-keygen -t ed25519
    ```
