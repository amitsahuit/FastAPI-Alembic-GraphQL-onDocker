

# FastAPI-Alembic-GraphQL-onDocker

## intial setup command
```
py -m venv venv
.\venv\Scripts\activate
pip install -r requirements.txt
```

## migrate the DB
```
alembic init alembic
```

## Start the application
```
docker-compose run app alembic revision --autogenerate -m "New Migration" 
docker-compose run app alembic upgrade head
```
## GraphQL Mutation
```
mutation CreateNewPost{
  createNewPost(title:"new title1", content:"new content") {
    ok
  }
}

query{
  allPosts{
    title
  }
}

query{
  postById(postId:2){
    id
  	title
    content
  }
}
```