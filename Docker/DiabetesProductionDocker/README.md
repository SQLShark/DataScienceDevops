# Commands requied to get this all working. 
This is here both as an instruction and also a means for me to remember how to process a model. 

So to run a model inside a container you need to first navigate to the location of the Dockerfile. 

```
cd "G:\GitHubProjects\session-DataScienceDevops\Docker\DiabetesProductionDocker"
```

Then we need to build the model 
```
docker build -t diabetes .
``` 

Lets check that the image has been created as intended. 

```
docker images
```

Lets run the model using our local version of Docker
```
docker run -d -p 5071:5071 diabetes
```

The important part of that last call is the -p parameter. That is forwarding the port from the docker image to my machine. Now all of these steps have been completed, we can open our web browser and train then score our model.

1. http://localhost:5071/train?var1=0
2. http://localhost:5071/score?var1=10