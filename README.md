# deepstream

<b>- 인식된 카메라 장치 확인
```
 ls -al /dev/video*
```
<b>- v4l2 유틸 설치
```
sudo apt-get install qv4l2 v4l-utils
```
<b> - 카메라 정보 확인
```
v4l2-ctl --list-devices
v4l2-ctl -d /dev/video0 --list-formats
v4l2-ctl --all -d 0
```
<b> - CSI 카메라 debug
```
v4l2-ctl --stream-mmap --stream-count=100 --set-ctrl bypass_mode=0 -d /dev/video0
v4l2-ctl --stream-mmap --stream-count=1 --set-ctrl bypass_mode=0 -d /dev/video0 --verbose
```
<b>   USB 카메라 연결버전(대역폭) 확인
```
lsusb -t
```
