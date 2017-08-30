# TensorFlow-and-Keras-on-Jetson-TX2
create a swap file 
plugin usb stick 
cd /media/nvidia/JetsonSSD/
create swap file around 8-10 GB

From installation to examples 
Jetpack 3.1 
Tensorflow 1.3.0
Error message during install tensorflow: follow this instruction https://github.com/samjabrahams/tensorflow-on-raspberry-pi/issues/101 
Solution:
Edit the workspace.bzl at /home/pi/tensorflow/tensorflow (eigen archive link)

(at line 169)
from :

native.new_http_archive(
name = "eigen_archive",
urls = [
"http://mirror.bazel.build/bitbucket.org/eigen/eigen/get/f3a22f35b044.tar.gz",
"https://bitbucket.org/eigen/eigen/get/f3a22f35b044.tar.gz",
],
sha256 = "ca7beac153d4059c02c8fc59816c82d54ea47fe58365e8aded4082ded0b820c4",
strip_prefix = "eigen-eigen-f3a22f35b044",
build_file = str(Label("//third_party:eigen.BUILD")),
)

to:----
native.new_http_archive(
name = "eigen_archive",
urls = [
"http://mirror.bazel.build/bitbucket.org/eigen/eigen/get/d781c1de9834.tar.gz",
"https://bitbucket.org/eigen/eigen/get/d781c1de9834.tar.gz",
],
sha256="a34b208da6ec18fa8da963369e166e4a368612c14d956dd2f9d7072904675d9b",
strip_prefix = "eigen-eigen-d781c1de9834",
build_file = str(Label("//third_party:eigen.BUILD")),
)

