# FastAPI-TDD-Docker

## docker-compose Commands
```
# Start
$ docker-compose up -d --build

# tear down
$ docker-compose down -v
```


## pytest Commands
```
# normal run
$ docker-compose exec web python -m pytest

# disable warnings
$ docker-compose exec web python -m pytest -p no:warnings

# run only the last failed tests
$ docker-compose exec web python -m pytest --lf

# run only the tests with names that match the string expression
$ docker-compose exec web python -m pytest -k "summary and not test_read_summary"

# stop the test session after the first failure
$ docker-compose exec web python -m pytest -x

# enter PDB after first failure then end the test session
$ docker-compose exec web python -m pytest -x --pdb

# stop the test run after two failures
$ docker-compose exec web python -m pytest --maxfail=2

# show local variables in tracebacks
$ docker-compose exec web python -m pytest -l

# list the 2 slowest tests
$ docker-compose exec web python -m pytest --durations=2
```

## heroku commands
```
# Create a new app
$ heroku create

# Login in to the Heroku container registry
$ heroku container:login

# Provision a new Postgres database with the hobby-dev plan
$ heroku addons:create heroku-postgresql:hobby-dev --app <app-name>

# Release the image
$ heroku container:release web --app <app-name>

# Apply the migrations
$ heroku run aerich upgrade --app <app-name>

```