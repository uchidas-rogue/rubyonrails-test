# rubyonrails-test

## 環境構築 mac

* VSCode拡張
  * Ruby
  * HTML Snippets

* Rubyのインストール

```zsh
# update
brew update

# rbenv 
brew install rbenv ruby-build
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
source ~/.bash_profile

# readline
brew install readline
brew link readline --force

# ruby
RUBY_CONFIGURE_OPTS="--with-readline-dir=$(brew --prefix readline)"
# install ruby
rbenv install 2.6.3
# use ruby
rbenv global 2.6.3
rbenv rehash
# check ruby version
ruby -v



```


## 環境構築 q4os

```bash

sudo apt update

sudo apt install -y gcc make bzip2 git

sudo apt update

git clone https://github.com/rbenv/rbenv.git ~/.rbenv

echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc

mkdir -p "$(rbenv root)/plugins"
# rbenv プラグインをインストール
git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)/plugins/ruby-build"
# rbenv install 後に ~/.rbenv/default-gems に記載の gem をインストールしてくれる
git clone https://github.com/rbenv/rbenv-default-gems.git "$(rbenv root)/plugins/rbenv-default-gems"
echo bundler > "$(rbenv root)/default-gems"
# $ rbenv update すると、~/.rbenv/plugins 以下を全部 git pull してくれる ruby-build も対象となる
git clone https://github.com/rkh/rbenv-update.git "$(rbenv root)/plugins/rbenv-update"

sudo apt update

rbenv install 2.6.3
rbenv global 2.6.3
rbenv rehash
# check version
ruby -v

```