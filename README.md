# Prerequisites
- docker
- git-lfs

AWS EC2 AMI with at least 32gb disk can be used to create the image and the upload to replicate.com
```
sudo yum install docker
sudo yum install git
sudo yum install git-lfs
```

## 1. Create the model in replicate.com

Create a new model in [https://replicate.com/models](https://replicate.com/create)


## 2. Install COG
```
mkdir segany
cd segany
git lfs clone https://github.com/Leandroamaral/segany.git
sudo curl -o /usr/local/bin/cog -L https://github.com/replicate/cog/releases/latest/download/cog_`uname -s`_`uname -m`
sudo chmod +x /usr/local/bin/cog
cog login
```
[^1]
## 3. Create a model image and push to replicate
```
cog push r8.im/<model name>
```
\<model name> = model name created on item 1 of this manual 

# Opt: Test model before push to replicate
```
cog predict -i image=segany/exemple/dogs.jpg
```

[^1]: This is only have little changes of [https://replicate.com/casia-iva-lab/fastsam](https://replicate.com/casia-iva-lab/fastsam)  


