# SDS011-driver

all code is written by CHATGPT so far 

```
git clone https://github.com/Kraftbar/SDS011-driver
cd SDS011-driver
code . 
sudo apt-get install cmake
mkdir CMakeBuild
cd CMakeBuild
cmake .. && make && sudo ./sds011_driver
```

```
# plug the usb 
tmp1=$(ls /dev/) 
# unplug the usb 
tmp2=$(ls /dev/)
# find what tty the usb is attached to:
tmp3=$(diff <( echo "$tmp1" ) <( echo "$tmp2" ) )
# edit the correct stream into the driver file 
tmp4=$( echo $tmp3 | grep -o -E "([^[:space:]]*tty[^[:space:]]*)" )
sed -i "s/ttyUSB0/$tmp4/g" sds011_driver.c
``` 
