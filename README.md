# Deploying zappa on aws for deploying serverless app (flask)

## Install aws cmdline on ec2

```
$ conda install -c conda-forge awscli
```

## Configure aws credential on ec2 (must needed step)
```
$ aws configure
```
> ***add your aws access key and secret access keys***
> ***can view the keys deatail, cd ~/.aws ***



## Create a virtual env. & activate the environment
```
$ conda create --name environment_name
$ source activate myenv
$ source deactivate myenv
```

## Install flask and zappa inside the VE
```
$ conda install -c anaconda flask
$ conda install -c mathieu zappa
```


## Make a directory for flask App create an helloWorld flask project
```
$ mkdir flaskPro
$ cd flaskPro
$ wget https://github.com/ishaq4466/aws/tree/master/basicFlskApp
```


## Initialize zappa inside the flaskApp dir and configure the zappa project
```
$ zappa init
```


## Make changes in the zappa_seeting.json
## it should look like below after modifying it 
``` 
{
       dev: {
            app_function: app.app,
            s3_bucket: zappa-xxxxx,
            slim_handler: true,
            runtime: python3.6
        }
} 
```


## Deploy the project using deploy 
```
$ zappa deploy dev
$ zappa -h 
> You will get an api after successfull deployment
```


## Additional resources on zappa
### [Resource 1](https://hackernoon.com/deploy-a-serverless-flask-application-on-aws-lambda-d8ca58af42a4)
### [Resource 2](https://medium.com/@patrickmichelberger/how-to-deploy-a-serverless-machine-learning-microservice-with-aws-lambda-aws-api-gateway-and-d5b8cbead846)
### [Resource 3* ](https://github.com/Miserlou/Zappa/issues/1471#issuecomment-381437537)n








