

# CURL 
A tool for making http request, which can be used extensively.

## Basic request
	curl http://localhost:8000/
The above request will just make a get request to the url specified.

## Post Request method
	curl --request (-X) Post --header (-I) "Content-type: application/json" --data (-d) '{"username":"shaddy"}' http://localhost:8000/

### Get Request method
	curl --request (-X) Get http://localhost:8000/

##
