

git clone -b 3.3.0 --depth=1 https://github.com/opencv/opencv.git
cd opencv
mkdir build
cd build

docker-compose up -d
# docker-compose exec main /bin/bash
cd opencv/build
cmake -D CMAKE_BUILD_TYPE=RELEASE -DWITH_FFMPEG=ON -DBUILD_SHARED_LIBS=OFF -D WITH_1394=OFF ..
time make -j8
