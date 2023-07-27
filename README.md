# Ubuntu Setup
* Keep things updated.
    ```
    sudo apt update && sudo apt upgrade -y && sudo apt autoremove -y &&
    sudo apt install git zsh -y
    ```
* You need a better CLI.
    ```
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
* Make it even better with zsh-plugins.
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
* [NVM](https://github.com/nvm-sh/nvm#installing-and-updating) makes life less hard.
    ```
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash &&
    source ~/.zshrc &&
    nvm install --lts &&
    node -v &&
    corepack enable &&
    pnpm -v
    ```
* VS Code Server
    ```
    curl -Lk 'https://code.visualstudio.com/sha/download?build=stable&os=cli-alpine-arm64' --output vscode_cli.tar.gz &&
    tar -xf vscode_cli.tar.gz &&
    rm vscode_cli.tar.gz &&
    sudo mv code /bin &&
    source ~/.zshrc &&
    code tunnel
    ```
* SSH
    ```
    ssh-keygen -t ed25519 -N "" -f ~/.ssh/id_ed25519 <<< y &&
    cat ~/.ssh/id_ed25519.pub
    ssh-keygen -t rsa -N "" -f ~/.ssh/id_rsa <<< y &&
    cat ~/.ssh/id_rsa.pub
    ```
* Speedtest
    ```
    curl -s https://packagecloud.io/install/repositories/ookla/speedtest-cli/script.deb.sh | sudo bash &&
    sudo apt-get install speedtest &&
    speedtest
    ```
7. GitHub
    ```
    git config --global init.defaultBranch main;
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
