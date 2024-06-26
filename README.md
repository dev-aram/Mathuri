# 🔮 추리추리 마추리
##### 추리 수수께끼 게임 챗봇
###### 인원: 5명
###### 기간: 2024-01-12 ~ 2024-02-20
###### [학습 데이터](https://github.com/dev-aram/Mathuri/tree/master/data)
###### [학습 코드](https://github.com/dev-aram/Mathuri/tree/master/learning)
-----------------
## 💡 프로젝트 기획
평소에 심심할때 할게없을때 쉽게 할 수 있는 어플을 만들고 싶다는 생각이 들어 인터넷을 찾아보다가 수수께끼 문제들을 찾았습니다. 그래서 마추리팀은 단순 대화만 할 수 있는 챗봇이 아닌 수수께끼 게임을 만들어 문제를 스테이지 형식으로 구성하고 질문하면 해당 질문에 맞는 답변을 사용자에게 전달하고, 힌트 및 정답등을 버튼형식으로 구현하여 사용자가 더욱 쉽고 편하게 게임을 즐길 수 있도록 챗봇을 제작하였습니다.

<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/5d3a7fb0-55e3-4dcc-a2bc-6a39ada0ae09">

<hr>

# **마추리란?**
사람과 챗봇이 수수께끼 문제를 같이 풀어가는 게임형식의 챗봇으로 유저(브리튼) 챗봇(마추리)로 구성되어있다.
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/b9041c53-3ddd-45b8-9e93-413379d7bb00">


## 👨‍💻 Process & Role
#### Overall Process
###### - 기획, 서버구현, 프론트구현, 모델학습, 서버배포, PPT제작, 발표, 데이터수집
**Overall Process**

- 기획, 서버구현, 프론트구현, 모델학습, 서버배포, PPT제작, 발표, 데이터수집

**😺 My Role**

- 기획
    - 어플리케이션 전체적인 기능 및 구현 기획
- 서버구현
    - Node.js를 이용하여 로그인, 회원가입, 스테이지, 챗봇페이지 구현
    - 챗봇에서는 대화 저장하기 초기화하기 힌트보기 등 다양한 기능을 구현
- 모델학습
    - 입력된 데이터를 정제하여 라벨링 후 모델 학습
    - 사용자에서 입력된 질문을 RoBERTa 모델을 이용하여 유사도 처리
    - 유사도 확률이 높을 시 GPT2 모델에 입력된 질문을 넣어 답변 출력
- 프론트구현
    - HTML, CSS, JavaScript를 이용하여 어플리케이션 전체 퍼블리싱 진행
- 서버배포
    - 클라우드타입을 이용하여 front, node.js 서버 배포
    - AWS를 이용하여 파이썬 서버 배포
- PPT제작
    - Canva를 이용하여 PPT 제작
- 데이터수집
    - 수수께끼 질문 답변 데이터 수집
- 디자인
    - 어플리케이션 전체 디자인

## 🌏 Dataset & Model
#### Dataset
- 문제별로 [질문과 답변 데이터](https://github.com/moon-123/Matchuri-NLP-project/files/14344362/QADataset.xlsx)를 직접 작성함
- 모델 학습에 사용한 문제는 총 6개로 2289개의 질문-답 데이터셋 사용

#### Model
- 문장 학습 모델 [skt/kogpt2-base-v2](https://github.com/SKT-AI/KoGPT2)
- 유사도 측정 모델 [ddobokki/klue-roberta-base-nli-sts](https://huggingface.co/ddobokki/klue-roberta-base-nli-sts)
-----------------
## 🚀 Result

### **발표ppt**
[추리추리 마추리 ppt](https://github.com/dev-aram/Mathuri/blob/master/%EB%A7%88%EC%B6%94%EB%A6%AC_%EB%B0%9C%ED%91%9C.pdf)


### **프론트**
- 제작 화면1
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/102acf10-a28f-4910-9cf4-fcbbe411205e">

- 제작 화면2
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/dc70ce0e-efc0-4c11-ba5a-46af259e8fb7">

### **서버**
확장성을 위해 node, python 두가지 서버를 같이 사용 채팅부분을 제외한 나머지 부분은 전무 node.js로 서버를 작업하였고 모델과 소통해야하는 채팅 부분은 python 서버로 작업하였습니다.

<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/1abe245c-1cab-4294-9e44-64e31c57926f">
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/ca2ee070-ea4b-46e9-85be-62f0dad75699">

### **모델**
유저가 질문을 입력하면 RoBerta로 유사성을 검사하고 문제와 유저가 입력한 질문이 유사하다고 판단되면 GPT2 모델에 넣어 학습한 질문과 대조하여 학습된 답변을 그래도 출력하거나 GPT2가 생성한 답변을 출력되게 모델을 학습시켰습니다.

<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/7be28c64-0c2a-4e17-ab4d-9c0295ba1180">
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/dff17a9b-6752-4187-a0f4-8e799135f226">
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/28ab16b7-c197-4998-8993-d5dfd0ad3c33">
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/49ffe5e3-0676-4e6a-97b9-8b504c6e3f2a">

- **전처리 과정**
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/f08979cc-647c-4085-b13e-6e097dfe9e71">

- **GPT2**
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/4ac6fced-5981-4921-ba5c-487182f1af63">
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/8ad2ec6f-2fb0-49e4-adaa-20f6299589de">
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/4bbd766f-4db5-4ebd-9524-9dcf0ea4250d">

- **최종모델**
<img width="100%" alt="image" src="https://github.com/dev-aram/Mathuri/assets/135501045/4dc61506-bd8a-45b1-bcfd-2a6b23431b69">



-----------------
### ⚙️ Skills & Tools

<p>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/JavaScript-gray?style=flat&logo=JavaScript&logoColor=F7DF1E"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=4479A1"/>&nbsp;&nbsp;
</p>

<p>
  <img src="https://img.shields.io/badge/Colab-F37626?style=flat&logo=googlecolab&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/VScode-007ACC?style=flat&logo=visualstudiocode&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/Discord-5865F2?style=flat&logo=Discord&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/AWSEC2-FF9900?style=flat&logo=amazonec2&logoColor=white"/>&nbsp;&nbsp;
  <img src="https://img.shields.io/badge/AWSS3-569A31?style=flat&logo=amazons3&logoColor=white"/>&nbsp;&nbsp;

  
</p>
