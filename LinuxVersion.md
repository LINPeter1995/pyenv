pyenv 安裝與設定教學（Linux）

Step 1：卸載舊的 pyenv-win（如果之前安裝過 Windows 版）

rm -rf ~/.pyenv

Step 2：安裝必要的系統相依套件（Ubuntu / Debian）

sudo apt update

sudo apt install -y make build-essential libssl-dev zlib1g-dev \

libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \

libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev \

liblzma-dev python3-openssl git

Step 3：安裝 pyenv 本體

curl https://pyenv.run | bash

Step 4：設定 Shell 配置檔（根據你用的 Shell）

echo 'export PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.bashrc

echo 'eval "$(pyenv init --path)"' >> ~/.bashrc

echo 'eval "$(pyenv init -)"' >> ~/.bashrc

若你使用的是 zsh：

echo 'export PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.zshrc

echo 'eval "$(pyenv init --path)"' >> ~/.zshrc

echo 'eval "$(pyenv init -)"' >> ~/.zshrc

Step 5：讓設定生效

source ~/.bashrc      # 或 source ~/.zshrc，依你的 shell 而定

Step 6：確認 pyenv 是否安裝成功

pyenv --version

Step 7：安裝並啟用指定版本的 Python（例如 3.11.0）

pyenv install 3.11.0

pyenv global 3.11.0

