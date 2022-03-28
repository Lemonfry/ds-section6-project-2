# project2

Yolov5를 이용한 coco dataset과 kitti(2d) dataset 간의 훈련 성능 비교

다음의 dataset을 활용하였습니다.
1) coco(2017 dataset) : https://cocodataset.org/#home
2) kitti(2012 2d object) : http://www.cvlibs.net/datasets/kitti/eval_object.php?obj_benchmark=2d

다음의 github repository를 활용하였습니다.
1) Yolov5, version 6.1(2022.02.22) : https://github.com/ultralytics/yolov5#readme
2) convert2Yolo, 버전 없음(2019.07.28) : https://github.com/ssaru/convert2Yolo


전체적인 흐름
1. dataset 다운
2. convert2Yolo를 이용하여 kitti 변환(kitti.names 활용)
3. convert2Yolo를 이용하여 coco dataset의 80개 category를 9개로 축소(person, bicycle, car, motorcycle, bus, train, truck, traffic light, stop sign)
(coco.names 활용)
4. coco 원본, 축소본, kitti 데이터셋을 yolov5l의 weight로 훈련(coco 원본이 아닌 나머지에는 coco_reduced.yaml, kitti.yaml을 활용)

코드 실행 환경
ubuntu 18.04, python 3.6 및 각 repository 안의 requirements.txt
