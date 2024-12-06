# HyperLearning_EssayEvaluation
# 에세이 분석 및 예측 프로젝트

이 프로젝트는 학생들의 에세이 데이터를 분석하여 에세이 점수를 예측하는 모델을 개발하는 것입니다. 데이터는 학생들의 에세이와 평가 정보를 포함하고 있으며, 이를 바탕으로 에세이의 다양한 특성(글자수, 문장 수, 고유 단어 수 등)과 점수 간의 관계를 분석합니다. 최종적으로 여러 회귀 모델을 사용하여 에세이 점수 예측 모델을 구축합니다.

## 설치 및 실행 방법
**1. 필수 라이브러리 설치**  
requirements.txt 파일을 사용하여 필요한 라이브러리를 한 번에 설치합니다.  
`pip install -r requirements.txt`  

**2. 데이터 준비**  
[다운로드 링크
](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&dataSetSn=545)  
AI-Hub의 "에세이 글 평가 데이터"에서 데이터셋을 다운로드합니다.  
다운로드한 데이터의 경로를 코드 내에서 환경에 맞게 수정합니다.

**3. 데이터 전처리**  
JSON 파일에서 데이터를 읽어 pandas DataFrame으로 변환 후, essay.csv로 저장합니다.  
student_grade가 "고등_2학년"인 데이터만 추출됩니다.  

**4. 텍스트 정규화 및 분석**  
konlpy의 Okt 형태소 분석기를 사용하여 에세이 문단을 분석합니다.  
불용어를 제거하고, 각 문단의 형태소 수, 문장 수 등을 계산합니다.  

**5. 상관관계 분석**  
변수 간 상관관계를 산점도로 시각적으로 분석합니다.  

**6. 특성 선택 및 전처리**  
categorical_features와 numeric_features를 정의하고, MinMaxScaler와 OneHotEncoder로 데이터를 변환합니다.  

**7. 모델 학습**  
Linear Regression, Random Forest, Support Vector Regressor, ElasticNet 모델을 학습합니다.  
교차 검증을 통해 성능을 평가합니다.

## 파일 구조 설명
- **/src**: 프로젝트의 핵심 코드가 포함된 폴더입니다. 데이터 처리, 모델 학습 및 평가와 관련된 코드가 이 폴더에 저장됩니다.
  - `HyperLearning_EssayEvaluation.ipynb`: 프로젝트 전체 코드가 작성된 Jupyter Notebook 파일입니다. 데이터 전처리, 분석, 모델 학습 및 평가 등의 모든 과정이 이 파일 내에서 이루어집니다.

- **/data**: 데이터 처리 및 분석에 필요한 스크립트만 포함됩니다.
  - `data_processing.ipynb`: 데이터를 읽고, 처리하며 분석하는 스크립트가 포함된 Jupyter Notebook 파일입니다.
 
- **/docs**: 프로젝트와 관련된 문서가 포함된 폴더입니다.
  - `결과 보고서.pdf`: 데이터 분석 결과, 모델 선택 이유, 성능 평가 결과 및 개선 방안을 포함한 최종 보고서입니다.

- **requirements.txt**: 프로젝트 실행에 필요한 Python 패키지 목록을 나열한 파일입니다. `pip install -r requirements.txt` 명령어로 필요한 패키지를 설치할 수 있습니다.

## 사용된 기술 및 라이브러리
**1. 데이터 처리 및 분석**  
pandas: 데이터 프레임을 사용한 데이터 처리 및 전처리.  
json: JSON 파일 읽기 및 파싱.  
konlpy: 한국어 형태소 분석을 위한 Okt 형태소 분석기.  
re: 텍스트 정규화 및 특수 문자 제거.  
matplotlib / seaborn: 산점도.  

**2. 모델링**  
scikit-learn  
cross_val_score: 교차 검증을 통한 모델 성능 평가.  
train_test_split: 데이터셋 분할.  

**3. 데이터 전처리**  
MinMaxScaler: 수치형 데이터 정규화.  
OneHotEncoder: 범주형 데이터 인코딩.  

**4. 평가 지표**  
MSE: 모델 성능 평가 지표.  

**5. 모델**  
Linear Regression  
Random Forest Regressor  
Support Vector Regressor  
ElasticNet  

**6. 주요 기능**  
에세이 데이터 전처리 및 텍스트 정규화.  
문단별 형태소 분석 및 불용어 제거.  
변수 간 상관관계 시각화.  
머신러닝 모델을 통한 에세이 점수 예측.
