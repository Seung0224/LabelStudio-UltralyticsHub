# DeepLearning Yolo v11

Windows 환경에서 **Ultralytics YOLOv11** 프레임워크를 활용하여  
객체 탐지(Object Detection) 모델을 학습·추론하고, **C# .NET Framework (4.8.1)** 기반 프로그램에 적용할 수 있도록 구현한 프로젝트입니다.  
Google Colab 환경에서 무료로 학습을 수행하고, 최종 변환된 TensorRT 엔진을 통해 고속 추론이 가능합니다.

---
<img width="1445" height="789" alt="image" src="https://github.com/user-attachments/assets/235441ce-038d-432f-b5d8-2eb17082eb32" />

## 📦 프로젝트 개요

- **플랫폼:** Visual Studio Code · Google Colab (Python 3.11)  
- **프레임워크:** Ultralytics YOLOv11  
- **목적:** Custom Dataset 기반 객체 탐지 모델 학습 및 추론  
- **데이터셋:** 사용자 정의 라벨링 (COCO 형식 Export)  
- **결과물:** PyTorch `.pt`, ONNX `.onnx`, TensorRT `.engine` 모델 파일 및 추론 결과 이미지  

---

## ✅ 주요 기능

### 1. ✏️ Annotation
- Vision Task 설정 후 라벨 이름(Label names) 및 라벨링 옵션(configure settings) 지정  
- 작업 완료 후 **Export 버튼**을 통해 모델에서 요구하는 형식(config 기반)으로 변환된 Annotation 파일 생성  

### 2. 🧠 모델 선택 & 학습 (Model Selection & Training)
- **Ultralytics** 기반 모델 선정 및 학습 진행  
- 기존 `classes.txt`, `notes.json` 파일을 활용하여 **yaml 구성 파일** 생성  
- 데이터셋 변환(`images`, `labels`, `yaml`) 후 압축하여 업로드  
- 학습 모델로는 **YOLOv11x** 권장 (Accuracy 최상)  
- 무료 환경에서의 학습을 위해 **Google Colab** 활용 (`pip` 명령어 실행 → Train Code 복사 실행)  

### 3. 🔮 추론 (Predict)
- 학습 완료 후 **best.pt** 모델 생성 → 성공 여부 검증  
- 추론을 위해 `.pt → .onnx → .engine` 변환 과정 수행  
- **평균 추론 속도**:  
  - Object Detection (이미지 100장 기준): **7ms** (Neruocle 환경: 11ms)  
- 변환된 `.onnx` 파일은 **C# .NET Framework 4.8.1** 환경에서 동작 검증 완료 → Vision Program 적용 가능  

---

## 🧰 사용 방법

1. 데이터셋 라벨링 후 Export 진행 (COCO 형식 변환)  
2. Google Colab에서 YOLOv11 모델 학습 진행 (`best.pt` 생성)  
3. 생성된 `.pt` 모델을 `.onnx` → `.engine` 형식으로 변환  
4. 변환된 모델을 로컬 환경(C# .NET 4.8.1) 프로그램에서 추론 적용  

---

## 🔧 개발 환경 및 라이브러리

| 구성 요소 | 내용 |
|------------|------|
| 언어 | Python 3.11 |
| 프레임워크 | Ultralytics YOLOv11 |
| 환경 | Google Colab, Visual Studio Code, Windows 10 |
| 배포 대상 | C# .NET Framework 4.8.1 |
| 최적화 | TensorRT Engine 변환 |
