FROM ruby:latest

RUN apt-get update && \
		apt-get install -y nodejs sqlite3 && \
		gem install rails -v 5.0.2

# Expose le port 3000 pour accéder à l'app.
EXPOSE 3000

# Copie tout le contenu du dossier courant dans le container
ONBUILD COPY . /opt/app

# Definie le dossier d'ouverture au lancement du container
ONBUILD WORKDIR /opt/app

# Installe les dépendances à partir du Gemfile de l'app
ONBUILD RUN bundle install

# Met la structure de la bdd à jour à partir d'un fichier de app/db/migrate/
ONBUILD RUN rails db:migrate

# Remplit la bdd à partir du fichier app/db/seeds.rb
ONBUILD RUN rails db:seed

ONBUILD RUN rails db:setup

# Création de l'image 'ft-rails:on-build'
#docker build -t ft_rails:on-build .

# Il faut créer une 'app' pour tester le Dockerfile
#docker run --rm -v $PWD:/app -w /app -it ruby bash -c 'apt-get update && apt-get install -y nodejs sqlite3 && gem install rails && rails new app'

# Création du Dockerfile dans 'app' pour tester l'image créée
#echo 'FROM ft-rails:on-build
#EXPOSE 3000
#CMD ["rails", "s", "-b", "0.0.0.0", "-p" ,"3000"]' > app/Dockerfile

# Pour construire une image avec l'app
#docker build -t ruby_1 ./app/

# Pour lancer un container de cette image et tester l'app dans chrome
#docker run --rm --name=rails-app -p 3000:3000 -it ruby_1

