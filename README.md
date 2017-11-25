# Instructions

1. Install pip, flask and virtualenv

```
sudo easy_install pip
sudo pip install flask
sudo pip install virtualenv
virtualenv flask
flask/bin/pip install flask
```

2. Run the application


```
./app.py
```

3. Run the the POST commands in R

```r
library(httr)
library(jsonlite)

# curl -i -H "Content-Type: application/json" -X POST -d '{"title":"Read a book"}' http://localhost:5000/todo/api/v1.0/tasks

a <- POST(
	url="http://localhost:5000/todo/api/v1.0/tasks",
	body = list(title="From R"),
	encode="json"
)

a <- POST(
	url="http://localhost:5000/todo/api/v1.0/tasks/get_tasks",
	body = list(id=1:10),
	encode="json"
)

fromJSON(content(a, "text"))
```
