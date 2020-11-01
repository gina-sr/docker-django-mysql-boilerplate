# Docker + Django + MySQL boilerplate
## Set up
- Make sure that docker and docker-compose are installed on your system
- Copy .envs/mysql-example.env to .envs/mysql.env and update the environment variables values
## Commands
### Create a django project
`docker-compose -f docker-compose.yml run --rm web python manage.py startproject {project_name} .`

**Note:** the final *"."* is required to create the project in the repo's root path
### Create a django app
`docker-compose -f docker-compose.yml run --rm web python manage.py startapp {app_name}`
### Build web container (first time)
`docker-compose -f docker-compose.yml build`
### Make and apply migrations
`docker-compose -f docker-compose.yml run --rm web python manage.py makemigrations`
`docker-compose -f docker-compose.yml run --rm web python manage.py migrate`
### Create super user
`docker-compose -f docker-compose.yml run --rm web python manage.py createsuperuser`
### Run the app
`docker-compose up`
### Run linter
`bash lint.sh` (from the project root)