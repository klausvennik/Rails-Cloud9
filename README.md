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

Creando la app: 

rails new app -j=importmap -c=bootstrap -d=postgresql


# Heroku CLI

heroku login -i

( usar correo y API key)

# Apuntes Generales 

1. En Cloud9 AWS crear un environment Ubuntu server. 
2. gem install rails -v 6.0.2.1
3. source <(curl -sL https://cdn.learnenough.com/yarn_install)
4. rails _6.0.2.1_ new hello_app
5. bundle install
6. Ir al sitio y copiar gemas en gemfile dentro de hello_app:  https://github.com/mhartl/rails_tutorial_6th_edition_gemfiles
7. cd hello_app
8. Bundle install
9. En el directorio hello_app>config>enviroments>development.rb pegar antes del end:

config.hosts.clear

10. En app/controllers/application_controller.rb agregar:

def hello
render html: "hello, world!"
end
end

11. En config/routes.rb agregar antes del end: root 'application#hello'
12. rails s
13. Revisar si se renderizó hello world. 
14. Crear un repositorio privado en GitHub. 
15. Copiar el comando en el repositorio donde dice ...or push an existing repository y pegarlo en la consola estando en el directorio del proyecto. 
16. En GitHub ir a settings>developer settings>personal access token y generar uno que se usará como clave cuando lo pregunte la consola. 
17. Desde el control de version de cloud9 hacer git push. 
18. Agregar al gemfile del proyecto la gema de postgresql para usarla con heroku:
group :production do gem 'pg', '1.1.4'
end
19. bundle install --without production
20. git commit -a -m "Update Gemfile for Heroku"
21. source <(curl -sL https://cdn.learnenough.com/heroku_install)
22. heroku --version
23. heroku login --interactive
24. info@deklaus.com/F...5
25. heroku create
26. En este paso ocurre un error: git push heroku HEAD:master
