# Colorado Contributions API for Accountable - GoCode Colorado 2020

## Installing and Running
At the moment this just starts the spring application and runs any new liquibase migrations.


### Prerequisites:
1. docker - [install here](https://hub.docker.com/editions/community/docker-ce-desktop-mac/)
1. homebrew -  `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`
1. postgres -  `brew install postgresql`

### Clone:
`git clone https://github.com/jdursema/colorado-contributions-api.git`

### DB Setup:

#### Install docker postgres
`docker pull postgres:alpine`

#### Start docker container:
`docker run --name accountable_db -e POSTGRES_PASSWORD=password -d -p 5432:5432 postgres:alpine`

#### Connect to docker container:
`docker exec -it accountable_db bash`

#### Connect to postgres user:
`psql -U postgres`

#### Create accountable database:
`CREATE DATABASE accountable;`

### Installing Application Dependencies and Running the Application

Install dependencies via gradle, hopefully your IDE helps you

Start application via your IDE (or via the command line)

**(Will make improvements to both of the above -- sorry)**


## Liquibase Migrations

From what I can tell liquibase migrations are being automatically applied when the application starts up.


### Adding a new migration

1. Add a new file to the migrations folder located at `/resources/db/changelog/migrations`
2. Files should be numbered since liquibase runs them in order. Something like `01-add-representative-table.xml`.
3. Add your newly created file to the include list in `db.changelog-master.xml` with another include tag like `<include file="classpath:db/changelog/migrations/01-add-representative-table.xml"/>`


## Helpful Commands 

#### Connect to psql from outside of docker:
`psql -h localhost -p 5432 -U postgres`

#### Check docker status
`docker ps` 
