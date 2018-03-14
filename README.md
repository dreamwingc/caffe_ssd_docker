# caffe_ssd_docker
Build CAFFE (include ssd) with nvidia-docker

Please install nvidia-docker from https://github.com/NVIDIA/nvidia-docker
```
cd path_to_caffe_ssd_docker
sudo nvidia-docker build -t caffe:gpu path_to_caffe_ssd_docker/caffe_ssd_docker
```
To test the built environment
```
sudo nvidia-docker run -ti caffe:gpu bash -c "cd /opt/caffe/build; make runtest"
```
All the run tests' status should be "OK" after the above command. It may take some time to run those tests.

To map the work directory from the docker image to the host computer
```
sudo nvidia-docker run -ti -v=$(pwd)/path_to_host_folder:/workspace caffe:gpu 
```
