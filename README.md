### This app wrote in python 2.7 ###


preparation environment:

    virtualenv -p python venv
    source venv/bin/activate
    pip install -r requirements
    
setup credentials:

    export TODOUSER='admin'
    export TODOPASS='todopass'

run app

    chmod +x ./app.py
    ./app

get all tasks

    curl -i -u admin:todopass http://localhost:5000/todo/api/v1.0/tasks

get task 2
  
    curl -i -u admin:todopass http://localhost:5000/todo/api/v1.0/tasks/2

update task 2
    
    curl -u admin:todopass -i -H "Content-Type: application/json" -X PUT -d '{"done":true}' http://localhost:5000/todo/api/v1.0/tasks/2

add new task
    
    curl -u admin:todopass -i -H "Content-Type: application/json" -X POST -d '{"title":"Read a book"}' http://localhost:5000/todo/api/v1.0/tasks

remove task 2

    curl -u admin:todopass -i -X DELETE http://localhost:5000/todo/api/v1.0/tasks/2
    
