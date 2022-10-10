# Instalando-Ruby 3 y Rails 7 en Ubuntu


rvm list
rvm get head
rvm install ruby-3.1.0
rvm --default use 3.1.0

gem install rails -v 7.0.1

gem update bundler
gem update rails
gem update --system
sudo apt update

sudo apt install postgresql libpq-dev redis-server redis-tools

ruby -v
rails -v
bundler -v
pg_config --version
