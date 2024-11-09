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
<b> nvgstcapture 영상 출력 확인

- USB Camera 실행 및 이미지 저장
  ```
$ nvgstcapture-1.0 --camsrc=0 --cap-dev-node=0
```
<b>
‘j’ + enter : 싱글이미지 저장
‘q’ + enter : 프로그램 종료

```
$ eog <file_name.jpg>
<b>  // 저장 이미지 확인 (Imager Viewer)
※ Jetson 카메라 기본 튜토리얼
Taking Your First Picture with CSI or USB Camera :
https://developer.nvidia.com/embedded/learn/tutorials/first
-picture-csi-usb-camera#CameraGuide-Usefulresources
- USB Camera 동영상 저장
  ```
nvgstcapture-1.0 --mode=2 --camsrc=0 --cap-dev-node=0
```
<b>
‘1’ + enter : 동영상 녹화 시작
‘0’ + enter : 동영상 녹화 종료

```
totem <file_name.mp4>
```
<b>
// 동영상 실행 확인 (Videos)
