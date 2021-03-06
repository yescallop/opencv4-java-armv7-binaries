# opencv4-java-armv7-binaries
Pre-built OpenCV 4.0.0 Java wrapper on Raspberry Pi 3 Model B (armv7)

Tested on a RPI3B+ (armv8), worked fine.

Compiled on a Raspberry Pi 3 Model B on 2018-12-01

The compilation was
 - with NEON enabled (seemed ineffective)
 - with VFPV3 enabled
 - without FFmpeg due to a **Segmentation fault** (core dump) while calling libopenmpt

For issue information: [opencv/opencv#10080](https://github.com/opencv/opencv/issues/10080)

For binaries with TBB (2019 U2): [/withtbb](https://github.com/yescallop/opencv4-java-armv7-binaries/tree/master/withtbb)

## cmake params:
```
cmake -D ANT_EXECUTABLE=/usr/bin/ant \
-D CMAKE_BUILD_TYPE=Release \
-D BUILD_TESTS=OFF \
-D BUILD_PERF_TESTS=OFF \
-D BUILD_SHARED_LIBS=OFF \
-D BUILD_opencv_apps=OFF \
-D BUILD_opencv_python2=OFF \
-D BUILD_opencv_python3=OFF \
-D ENABLE_NEON=ON \
-D ENABLE_VFPV3=ON \
# -D WITH_TBB=ON \
-D WITH_FFMPEG=OFF \
-D OPENCV_ENABLE_NONFREE=ON \
-D JAVA_AWT_INCLUDE_PATH=/usr/lib/jvm/jdk-8-oracle-arm32-vfp-hflt/include \
-D JAVA_AWT_LIBRARY=/usr/lib/jvm/jdk-8-oracle-arm32-vfp-hflt/include/jawt.h \
-D JAVA_INCLUDE_PATH=/usr/lib/jvm/jdk-8-oracle-arm32-vfp-hflt/include \
-D JAVA_INCLUDE_PATH2=/usr/lib/jvm/jdk-8-oracle-arm32-vfp-hflt/include/linux \
-D JAVA_JVM_LIBRARY=/usr/lib/jvm/jdk-8-oracle-arm32-vfp-hflt/include/jni.h \
..
```
