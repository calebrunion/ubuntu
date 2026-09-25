# Ubuntu Setup
Keep things updated.
```
sudo apt update && sudo apt upgrade -y && sudo apt autoremove -y
```
You need a better CLI.
```
sudo apt install zsh -y &&
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
Make it even better with zsh-plugins.
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
[NVM](https://github.com/nvm-sh/nvm#installing-and-updating) makes life less hard.
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash &&
source ~/.zshrc &&
nvm install --lts &&
node -v &&
npm i -g pnpm vercel bun &&
pnpm -v &&
pnpm setup &&
source ~/.zshrc
```

