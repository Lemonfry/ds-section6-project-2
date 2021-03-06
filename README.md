# ds-section6-project-2

Yolov5를 이용한 coco dataset과 kitti(2d) dataset 간의 훈련 성능 비교

1. 데이터셋

* 다음의 dataset을 활용하였습니다.
  * coco(2017 dataset) : https://cocodataset.org/#home
  * kitti(2012 2d object) : http://www.cvlibs.net/datasets/kitti/eval_object.php?obj_benchmark=2d

* 다음의 github repository를 활용하였습니다.
  * Yolov5, version 6.1(2022.02.22) : https://github.com/ultralytics/yolov5#readme
  * convert2Yolo, 버전 없음(2019.07.28) : https://github.com/ssaru/convert2Yolo

train_result는 각 데이터셋의 훈련 결과이며, weight 파일 및 predictons.json 파일은 25mb 용량 초과로 빠져 있습니다. 

2. Workflow
    * dataset 다운
    * convert2Yolo를 이용하여 kitti 변환(kitti.names 활용)
    * convert2Yolo를 이용하여 coco dataset의 80개 category를 9개로 축소(person, bicycle, car, motorcycle, bus, train, truck, traffic light, stop sign)
    (coco.names 활용)
    * coco 원본, 축소본, kitti 데이터셋을 yolov5l의 weight로 훈련(coco 원본이 아닌 나머지에는 coco_reduced.yaml, kitti.yaml을 활용)

3. 결과

Object detector 정확도 지표로 사용되는 mAP는 coco 원본 데이터에선 0.6, kitti 데이터에선 0.9, 수정한 coco 데이터에선 0.7 정도의 정확도를 보입니다.

* 코드 실행 환경
ubuntu 18.04, python 3.6, requirements.txt안의 패키지
