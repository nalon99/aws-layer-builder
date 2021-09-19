# aws-layer-builder
Repository useful to create lambda layers as zip files to be uploaded as layers to AWS lambda functions.  

This might be very usfeul when a Lambda function needs to use external packages not available. In such case, a layer can be used to provide additional packages to the Lambda function being used.  
Layers can be created in the AWS Lambda console where a zip file must be uploaded in order to provide the package/packages necessary to the Lambda function.  

## Get the amazonlinux docker image
In order to build a Layer, docker must be installed in the local machine, and from the Docker Hub downloads the **amazonlinux** image.  
Clone this repository with your local machine on a working folder, then type the following commands:  
- cd \<your working directory\>
- docker run -it --rm -v \<your working directory\>/aws-layer-builder/python:/app amazonlinux bash
- yum install python3
- yum install zip
- cd package
- pip3 install --ignore-installed --target=python <the name of the python package you are going to install>
- zip -r ../package.zip .  
  
Finally you'll find your AWS Layer as a zip file inside your working directory, and this can be later uploaded to the AWS Lambda management consol as a new Layer.  

  

