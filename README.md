# Ubuntu Setup
1. Keep things updated.
    ```
    sudo apt update && sudo apt upgrade -y && sudo apt autoremove -y &&
    sudo apt install git zsh curl trash-cli neofetch -y
    ```
2. You need a better CLI.
    ```
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
3. Make it even better with zsh-plugins.
    ```
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting &&
    git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
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
4. [NVM](https://github.com/nvm-sh/nvm#installing-and-updating) makes life less hard.
    ```
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash &&
    source ~/.zshrc &&
    nvm install --lts &&
    node -v &&
    corepack enable &&
    yarn -v
    ```
5. SSH
    ```
    ssh-keygen -t ed25519
    ```
    ```
    cat ~/.ssh/id_ed25519.pub
    ```
6. Speedtest
    ```
    curl -s https://packagecloud.io/install/repositories/ookla/speedtest-cli/script.deb.sh | sudo bash &&
    sudo apt-get install speedtest
    ```
7. GitHub
    ```
    type -p curl >/dev/null || sudo apt install curl -y
    curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
    && sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
    && echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
    && sudo apt update \
    && sudo apt install gh -y \
    && gh --version
    ```
    ```
    gh auth login
    ```
    ```
    cd &&
    gh repo clone workspaces .workspaces &&
    mkdir Profession Hobby
    ```
