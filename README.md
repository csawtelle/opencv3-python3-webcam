# opencv3-python3-webcam

Download opencv and make


cmake -DBUILD_TIFF=ON -DBUILD_opencv_java=OFF -DWITH_CUDA=ON -DENABLE_AVX=ON -DWITH_OPENGL=ON -DWITH_OPENCL=ON -DWITH_IPP=ON -DWITH_TBB=ON -DWITH_EIGEN=ON -DWITH_V4L=ON -DWITH_VTK=OFF -DBUILD_TESTS=OFF -DBUILD_PERF_TESTS=OFF -DCMAKE_BUILD_TYPE=RELEASE -DBUILD_opencv_python2=OFF -DCMAKE_INSTALL_PREFIX=$(python3 -c "import sys; print(sys.prefix)") -DPYTHON3_EXECUTABLE=$(which python3) -DPYTHON3_INCLUDE_DIR=$(python3 -c "from distutils.sysconfig import get_python_inc; print(get_python_inc())") -DPYTHON3_PACKAGES_PATH=$(python3 -c "from distutils.sysconfig import get_python_lib; print(get_python_lib())") ..



import cv2
import sys
print(sys.version)

print(cv2.__file__, cv2.__version__)
print(cv2.getBuildInformation())
# Camera 0 is the integrated web cam on my netbook
camera_port = 1

#Number of frames to throw away while the camera adjusts to light levels
ramp_frames = 30

# Now we can initialize the camera capture object with the cv2.VideoCapture class.
# All it needs is the index to a camera port.
camera = cv2.VideoCapture(camera_port)
retval, im = camera.read()
print(retval,im)

whatever the "__file__" is, replace it with the newly built openvv
for me this meant 

cp opencv/release/lib/python3/cv2.cpython-35m-x86_64-linux-gnu.so /home/csawtelle/.local/lib/python3.5/site-packages/cv2/cv2.cpython-35m-x86_64-linux-gnu.so

Webcam works now!
