## github相关运行库
sudo yum install git -y
sudo apt-get install git -y
git clone https://github.com/chenmingbiao/stone-age.git

## 编译相关运行库
yum install gcc-c++
apt-get install build-essential

### 测试
mkdir test && cd test
vim hello.cpp

    #include <iostream>
    main(){
        std::cout << "Hello World" << std::endl;
    }

g++ -o hello hello.cpp && ./hello

## 