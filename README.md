# 🤖 비츠봇 (BeatsBot) - 악성코드 정보 & 코딩 도우미

악성코드 보안 정보와 프로그래밍 질문에 답변합니다

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red.svg)
![NLP](https://img.shields.io/badge/NLP-Intent_Classification-green.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## 📋 목차
- [특징](#-특징)
- [데모](#-데모)
- [설치](#-설치)
- [사용법](#-사용법)
- [지원 기능](#-지원-기능)
- [작동 원리](#-작동-원리)
- [프로젝트 구조](#-프로젝트-구조)

## ✨ 특징

- 🛡️ **보안 정보**: 랜섬웨어, 트로이목마, 바이러스 등 악성코드 정보 제공
- 💻 **코딩 도우미**: Python, Java, 웹 개발, 알고리즘 질문 답변
- 🧠 **AI 기반**: PyTorch 신경망으로 의도 분류
- 🇰🇷 **한글 지원**: 한글과 영어 모두 지원
- 🎯 **높은 정확도**: 학습 후 90%+ 정확도
- 🔧 **쉬운 확장**: JSON 파일 수정으로 새로운 의도 추가 가능

## 🎬 데모

```
You: 안녕
비츠봇: 안녕하세요! 악성코드 정보 & 코딩 도우미 챗봇입니다. 🛡️💻

You: 랜섬웨어란?
비츠봇: 랜섬웨어는 파일을 암호화하고 복구 대가로 금전을 요구하는 악성코드입니다...

You: 파이썬 배우기
비츠봇: Python은 배우기 쉽고 강력한 프로그래밍 언어입니다!
     기본 문법:
     - 변수: x = 10
     - 출력: print('Hello')...

You: WannaCry 알려줘
비츠봇: WannaCry는 2017년 전 세계를 강타한 랜섬웨어입니다...
```

## 🔧 설치

### 1. 저장소 클론
```bash
git clone https://github.com/yourusername/beatsbot.git
cd beatsbot
```

### 2. 필요한 패키지 설치
```bash
pip install -r chatbot_requirements.txt
```

**chatbot_requirements.txt:**
```
torch
numpy
```

## 🚀 사용법

### 1단계: 챗봇 학습
```bash
python malware_chatbot_train.py
```

출력 예시:
```
단어 수: 245
의도 수: 23
패턴 수: 187
학습 시작...
Epoch [200/2000], Loss: 0.3421
Epoch [400/2000], Loss: 0.1234
...
학습 완료!
모델 저장 완료: malware_chatbot_data.pth
```

### 2단계: 챗봇 실행
```bash
python malware_chatbot_chat.py
```

### 종료
- `quit` 입력 또는 `Ctrl + C`

## 🎯 지원 기능

### 🛡️ 보안 정보
| 카테고리 | 내용 |
|---------|------|
| **랜섬웨어** | WannaCry, Locky, Ryuk 등 |
| **트로이목마** | Zeus, Emotet 등 |
| **바이러스** | 자가 복제, 파일 감염 |
| **웜** | 네트워크 확산 |
| **스파이웨어** | 정보 탈취 |
| **예방법** | 백업, 업데이트, 백신 |
| **증상** | 감염 징후 확인 |
| **복구** | 대응 방법 |

### 💻 코딩 도우미
| 카테고리 | 내용 |
|---------|------|
| **Python** | 기초, 반복문, 함수, 리스트 |
| **Java** | 기초, 클래스, 객체지향 |
| **웹 개발** | HTML, CSS, JavaScript |
| **알고리즘** | 정렬, 검색, 자료구조 |
| **Git** | 버전 관리, GitHub |
| **디버깅** | 오류 해결 방법 |
| **코딩 팁** | 학습 방법, 실력 향상 |

## 🧠 작동 원리

### 1. 의도 분류 (Intent Classification)
```
사용자 입력 → 토큰화 → Bag of Words → 신경망 → 의도 예측 → 응답 생성
```

### 2. 신경망 구조
```python
Input Layer (단어 수) 
    ↓
Hidden Layer 1 (64 neurons) + ReLU + Dropout
    ↓
Hidden Layer 2 (64 neurons) + ReLU + Dropout
    ↓
Output Layer (의도 수)
```

### 3. 학습 과정
1. **데이터 준비**: JSON 파일에서 패턴과 응답 로드
2. **전처리**: 토큰화 및 Bag of Words 변환
3. **학습**: 2000 에포크 동안 신경망 훈련
4. **저장**: 학습된 모델을 `.pth` 파일로 저장

### 4. 예측 과정
1. 사용자 입력을 Bag of Words로 변환
2. 신경망으로 의도 예측
3. 확률이 70% 이상이면 해당 의도의 응답 반환
4. 확률이 낮으면 "이해하지 못했습니다" 메시지

## 📁 프로젝트 구조

```
ai-chatbot/
│
├── malware_chatbot_intents.json    # 학습 데이터 (의도, 패턴, 응답)
├── chatbot_model.py                # PyTorch 신경망 모델
├── malware_chatbot_train.py        # 학습 스크립트
├── malware_chatbot_chat.py         # 챗봇 실행 스크립트
├── chatbot_requirements.txt        # 필요한 패키지
│
└── malware_chatbot_data.pth        # 학습된 모델 (자동 생성)
```

## ⚙️ 커스터마이징

### 새로운 의도 추가

`malware_chatbot_intents.json` 파일을 수정하세요:

```json
{
  "tag": "new_intent",
  "patterns": [
    "질문 패턴 1",
    "질문 패턴 2",
    "질문 패턴 3"
  ],
  "responses": [
    "응답 1",
    "응답 2",
    "응답 3"
  ]
}
```

### 하이퍼파라미터 조정

`malware_chatbot_train.py`:
```python
batch_size = 8          # 배치 크기
hidden_size = 64        # 은닉층 크기
learning_rate = 0.001   # 학습률
num_epochs = 2000       # 에포크 수
```

### 신뢰도 임계값 조정

`malware_chatbot_chat.py`:
```python
if prob.item() > 0.70:  # 70% → 원하는 값으로 변경
```

## 📊 성능

### 학습 결과
- **학습 시간**: 약 1-2분 (CPU 기준)
- **정확도**: 90%+ (학습 데이터 기준)
- **응답 속도**: < 0.1초

### 지원 의도 수
- **보안**: 13개 의도
- **코딩**: 10개 의도
- **총**: 23개 의도

## 🎓 학습 예제

### 예제 1: 보안 질문
```
You: 랜섬웨어 예방법
비츠봇: 악성코드 예방법:
     1. 정기적인 백업
     2. 운영체제 및 소프트웨어 업데이트
     3. 백신 프로그램 사용...
```

### 예제 2: 코딩 질문
```
You: 파이썬 반복문
비츠봇: Python 반복문:
     
     for문:
     for i in range(5):
         print(i)
     
     while문:
     while x < 10:
         x += 1...
```

### 예제 3: 복합 질문
```
You: 트로이목마란?
비츠봇: 트로이목마는 정상 프로그램으로 위장하여 시스템에 침투하는 악성코드입니다...

You: 자바 클래스
비츠봇: Java 클래스:
     
     public class Person {
         private String name;...
```

## 🐛 문제 해결

### 학습 데이터 오류
```bash
FileNotFoundError: malware_chatbot_intents.json
```
→ JSON 파일이 같은 폴더에 있는지 확인

### 모델 로드 오류
```bash
FileNotFoundError: malware_chatbot_data.pth
```
→ 먼저 `malware_chatbot_train.py` 실행 필요

### 낮은 정확도
- 더 많은 패턴 추가
- 에포크 수 증가
- 은닉층 크기 증가

## 📚 참고 자료

- [PyTorch 공식 문서](https://pytorch.org/docs/)
- [자연어 처리 기초](https://www.nltk.org/)
- 클로드 AI

## 🤝 기여

버그 리포트, 새로운 의도 제안, Pull Request 환영합니다!

## 📄 라이선스

MIT License 

## 👨‍💻 개발자

**Dangel**
