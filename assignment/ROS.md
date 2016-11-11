### Lab4：ROS & Cartographer安装指南

1. ROS安装      
   1. 设置Ubuntu仓库使其允许restricted,"          "universe," and "multiverse这三个属性
   2. 安装sources.list
      >sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
   3. 设置密钥
      >sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
   4. 安装    
      安装指令如下：
      >sudo apt-get update（更新）

      >sudo apt-get install libgl1-mesa-dev-lts-utopic（解决依赖性问题）
      
      >sudo apt-get install ros-jade-desktop-full（安装模式为Desktop-Full Install）

      >apt-cache search ros-jade（寻找可用包）
      
      我们可以得到上述步骤成功的截图：    
      ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab4/result/1.jpg)
      
      >sudo rosdep init（初始化rosdep） 
      
      >rosdep update（进行更新） 
      
      安装结束截图如下：    
      ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab4/result/2.jpg)
   5. 环境配置
      >echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
source ~/.bashrc
   6. 安装rosinstall
      >sudo apt-get install python-rosinstall

      安装结束截图：
      ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab4/result/3.jpg)
2. Cartographer安装     
    1. 安装所有依赖项    
    sudo apt-get install -y google-mock libboost-all-dev  libeigen3-dev libgflags-dev libgoogle-glog-dev liblua5.2-dev libprotobuf-dev  libsuitesparse-dev libwebp-dev ninja-build protobuf-compiler python-sphinx  ros-indigo-tf2-eigen libatlas-base-dev libsuitesparse-dev liblapack-dev   
    1. 首先安装ceres solver，选择的版本是1.11 ,路径随意  
        1. git clone https://github.com/hitcm/ceres-solver-1.11.0.git
        安装结束截图：    
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab4/result/4.jpg)
        2. cd ceres-solver-1.11.0/build
        3. cmake ..
        4. make
        5. sudo make install 
        安装结束截图：    
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab4/result/5.jpg)
    2. 然后安装 cartographer,路径随意
        1. git clone https://github.com/hitcm /cartographer.git
        2. cd cartographer/build
        3. cmake .. -G Ninja
        4. ninja
        5. ninja test
        6. sudo ninja install
        安装结束截图：    
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/lab4/result/6.jpg)
    3. 安装cartographer_ros    
        下载文件到catkin_ws下面的src文件夹下面
        >git clone https://github.com/hitcm /cartographer_ros.git    

        然后到catkin_ws下面运行catkin_make即可
    4. 数据下载测试    
        2d数据，大概500M，用迅雷下载
        下载网址：https://storage.googleapis.com/cartographer-public-data/bags/backpack_2d/cartographer_paper_deutsches_museum.bag     
        运行指令：
        >roslaunch cartographer_ros demo_backpack_2d.launch bag_filename:=${HOME}/Downloads/cartographer_paper_deutsches_museum.bag
        在这一步的时候出现了博客上面的问题，但是尝试了博客显示的是三种解决方法，军不成功，所以不再展示最终结果
