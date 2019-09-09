# tensorflow-docker-guide
Get multiple versions of tensorflow running on your computer

## start docker (In case it's not running)
sudo systemctl start docker

## start and stop a running container (tf2container is the name of the running container)
docker start -a tf2container  (-a will make the jupyter output in your terminal :D)
docker stop tf2container

## list running containers
docker ps -a

## run a container (do it once, then use the commands above to start it)

### this is version 2 
-v means your computer folder called notebooks will be accessible inside the container copy whatever files to it
--runtime  the secret to allow gpu inside the docker (except for driver program itself not need for any other installs docker will learn it on itsown)

docker run -it --runtime=nvidia  --name tf2container -v $(realpath ~/notebooks):/tf/notebooks -p 8888:8888 tensorflow/tensorflow:2.0.0rc0-gpu-py3-jupyter


### version 1 (gpu)
docker run -it --runtime=nvidia  --name tf1again -v $(realpath ~/notebooks):/tf/notebooks -p 8080:8888 tensorflow/tensorflow:nightly-gpu-py3-jupyter



Fork to add more explaination for users to use docker with their tensorflow


