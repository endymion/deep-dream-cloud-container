# Deep Dream Cloud Container

Originally forked from [CloudDream](https://github.com/VISIONAI/clouddream).

That project creates a neat Docker-based service for computing Deep Dream images and videos, with a slick HTTP preview.

This project has a simpler purpose: To provide a Python programming platform for computing [Deep Dream](https://en.wikipedia.org/wiki/DeepDream) images using [Caffe](http://caffe.berkeleyvision.org/) with the [Bat Country](https://github.com/jrosebr1/bat-country) Python library.

The target host is [AWS EC2 instances](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using_cluster_computing.html) with GPU processing, using [nvidia-docker](https://github.com/NVIDIA/nvidia-docker) to access [CUDA](http://www.nvidia.com/object/cuda_home_new.html).

# Running on EC2

## To create an nvidia-docker GPU-enabled container image from scratch

1. Get an EC2 g2.2xlarge with Amazon Linux
2. Install Docker with yum: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html
3. Install Docker Compose: https://docs.docker.com/compose/install/
4. Install CUDA: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using_cluster_computing.html  Driver download: http://us.download.nvidia.com/XFree86/Linux-x86_64/367.57/NVIDIA-Linux-x86_64-367.57.run
5. Install nvidia-docker using instructions for “other distributions”: https://github.com/NVIDIA/nvidia-docker
6. Snap an AMI.

## To run a compute container

1. Boot g2.2xlarge from the AMI from above.
2. start the plugin: ```nvidia-docker-plugin```
3. test nvidia-docker: ```nvidia-docker run --rm nvidia/cuda nvidia-smi```
4. Clone this project to the EC2 instance.
5. ```cd``` to this project folder and ```docker-compose up```
