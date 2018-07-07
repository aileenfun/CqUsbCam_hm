# CqUsbCam_Linux
1. 采起电子的USB相机应用程序依赖的共享库工程源码。兼容USB2.0和USB3.0，目前支持的sensor型号包括MT9V034，AR0134和AR0135。 

2. 工程采用cmake进行管理，要求最低版本位cmake2.8。
examples目录下是应用示例：其中cmd目录下保存了示例的命令行版本。在各示例工程下的build文件夹中，已经存在编译好的可执行程序（编译环境为x86, ubuntu14.04， gcc4.8.6, opencv2.4.9, libusb1.0.21），x86机器的Ubuntu14.04用户可在该路径下直接使用sudo ./usbCamConsole.sh 执行。 其他用户建议重新编译共享库和应用。重新编译步骤如下：

      1)：进入CqUsbCam/build目录，删掉该路径下所有文件
      
      2)：cmake ..

      3): make
      
      4): 进入examples/cmd下示例工程的build目录，例如examples/cmd/AR013x/build
      
      5)：sudo ./clean.sh
      
      6): cmake ..
      
      7): make
      
即可重新生成可执行程序。同样， sudo ./usbCamConsole.sh 执行。


3. 注：编译CqUsbCam共享库工程需要安装libusb，建议以下安装方式：

     sudo apt-get install libusb-1.0-0-dev
     

    编译示例工程需要安装opencv，建议以下安装方式：

     sudo apt-get install libopencv-dev
