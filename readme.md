# yolov8_cspdarknet-pvdetection 人车检测

## 运行demo
```shell
cd prototype; python demo.py --weight /Users/sh/Downloads/yolov8n_peddet_v1.pt --h264 /Volumes/ASM236X/stream/test_erqiyuanqu.h264 --device mps
```

## 训练模型
COCO预训练模型下载：(N/A)[24bb0ae848.pt]()
fake_osd增强字体库下载：(N/A)[hzk-pixel-16px.ttf]()
```shell
cd prototype; python trainer.py --device_id 0 --pretrained_pt_path /Users/sh/Downloads/24bb0ae848.pt --batch_size 16 --max_epochs 150 --ema_enabled --wandb_enabled --early_stop
```

## 导出模型
```shell
cd prototype; python export.py --weight /Users/sh/Downloads/yolov8n_peddet_v1.pt --input_shape 1 3 352 640 --input_names image --output_names output --opset_version 13 --enable_onnxsim
```
