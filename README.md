# 개요
* 일정기간 동안 측정된 주식 데이터셋이 주어집니다.
* Train set과 test set이 주어집니다.
* Train set에 대해서 학습을 진행하고, test set을 통한 prediction을 만드는 것이 목표입니다.

# 데이터 설명
*Input data*  
* 데이터셋의 각 column은 날짜 정보와 종목정보, 그리고 feature set으로 이루어져 있습니다. Feature set은 blur 처리되어 있습니다. 
* Feature는 각 종목들의 유의미하다고 판단되는 데이터 값으로 이루어져 있습니다.

*Target data*
* Train set에 대해서는 정답 데이터 2개가 주어지고, Test set에 대해서는 정답이 주어지지 않습니다. 정답 데이터들은 각 샘플 시간 기준으로 다음 단위 시간(T) 수익률로 만들어집니다.
  * 정답 데이터 1: 단위 시간(T) 수익률 (train_target.csv) → Regression
  * 정답 데이터 2: 특정 한 시점에서 종목들의 단위 시간 수익률(정답 데이터 1)을 5 분위로 나누어 분류한 target (train_target2.csv) → Classification

# 세부사항
* 어떤 정답을 학습시키느냐에 따라 regression 접근, 혹은 5 분위 중 어떤 위치에 있을지 예측하는 classification 접근법이 있습니다. 
* 이를 포함해서 수험자 재량에 따라 데이터에 변형을 가하는 등의 접근 방식을 써도 좋습니다.
  * 예를 들어 classification 문제로 예시를 들면 수익률을 5 분위 대신 2 분위로 나누어서 binary classification으로 변형해도 좋습니다. 다만 변형할 경우 해당 부분에 대한 설명의 기재를 부탁드립니다.
  * 어떠한 접근 방법이든 하나만 선택해도 됩니다.
* 모든 데이터를 학습에 사용할 필요는 없습니다.
  * 예를 들어 특정 feature는 필요 없다고 판단하면 버리셔도 무방하고, 새로운 Feature를 만들어서 사용하셔도 됩니다.
* 실제 모델 결과보다 모델을 만들기까지의 과정이 중요합니다.
* 어떠한 논리로 분석을 진행하였는지 설명을 세부적으로 적어주시길 바랍니다. (코멘트/주석 방식 or 보고서)
  * Score보다는 적어주신 주석/코멘트나 보고서 내용이 평가 비중이 높습니다.
* 딥러닝 프레임워크(TensorFlow, PyTorch, Keras, Theano 등)를 사용한 모델링 과정을 하나 이상 넣어주시길 바랍니다. 
* Deep learning 모델 외에도 추가적으로 모델을 사용하는 것은 제한이 없습니다.

# 제출 양식
* Test set에 대한 모델의 예측값를 csv 형태로 저장하여 소스코드와 같이 제출해야 합니다. 
* 소스코드 형식은 .ipynb(jupyter notebook) 형식이 선호되고 .py 파일도 제출 가능합니다. 
* 결과물들이 모두 포함된 압축파일(.zip)로 제출해주십시오.
