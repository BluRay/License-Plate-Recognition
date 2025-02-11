# License-Plate-Recognition
License Plate Recognition For Car With Python And OpenCV

#### 用python3+opencv3做的中国车牌识别，包括算法和客户端界面，只有2个文件，surface.py是界面代码，predict.py是算法代码，界面不是重点所以用tkinter写得很简单。

### 使用方法：
版本：python3.4.4，opencv3.4和numpy1.14和PIL5<br>
下载源码，并安装python、numpy、opencv的python版、PIL，运行surface.py即可

### 算法实现：
算法思想来自于网上资源，先使用图像边缘和车牌颜色定位车牌，再识别字符。车牌定位在predict方法中，为说明清楚，完成代码和测试后，加了很多注释，请参看源码。车牌字符识别也在predict方法中，请参看源码中的注释，需要说明的是，车牌字符识别使用的算法是opencv的SVM， opencv的SVM使用代码来自于opencv附带的sample，StatModel类和SVM类都是sample中的代码。SVM训练使用的训练样本来自于github上的EasyPR的c++版本。由于训练样本有限，你测试时会发现，车牌字符识别，可能存在误差，尤其是第一个中文字符出现的误差概率较大。源码中，我上传了EasyPR中的训练样本，在train\目录下，如果要重新训练请解压在当前目录下，并删除原始训练数据文件svm.dat和svmchinese.dat。

##### 额外说明：算法代码只有500行，测试中发现，车牌定位算法的参数受图像分辨率、色偏、车距影响，有的车型识别效果有待提高。
##### 有任何疑问请邮件至 wzh191920@sina.com

##### 界面效果：
![](https://github.com/wzh191920/License-Plate-Recognition/blob/master/Screenshots/3.png)
![](https://github.com/wzh191920/License-Plate-Recognition/blob/master/Screenshots/5.png)


##### QQQ
环境配置—Ubuntu 16.04 安装Opencv 3.4.3
https://www.jianshu.com/p/f646448da265

No CMAKE_CXX_COMPILER could be found.

Tell CMake where to find the compiler by setting either the environment 
variable “CXX” or the CMake cache entry CMAKE_CXX_COMPILER to the full path 
to the compiler, or to the compiler name if it is in the PATH.

解决方法：

sudo apt-get update

sudo apt-get install -y build-essential

##
from PIL import Image, ImageTK 
ImportError: cannot import name 'ImageTK' 

For Debian/Ubuntu:

Python 2

sudo apt-get install python-imaging python-pil.imagetk

Python 3

sudo apt-get install python3-pil python3-pil.imagetk

For Archlinux:

sudo pacman -S python-pillow  
