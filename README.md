# project_chatbot
This repository documents my journey of studying AI/ML after being discharged from the Korean army

# 🧠 Daily Chatbot using Mini Transformer

이 프로젝트는 카카오톡에서 제공하는 일상 대화 데이터를 정제해, 자연어 질문에 대답할 수 있는 챗봇을 만드는 것을 목표로 합니다.  
Mini Transformer 모델을 사용하여 간단하면서도 의미 있는 질의응답 학습을 진행하였습니다.

---

## 🚀 프로젝트 개요

- **목적**: 일상 대화를 바탕으로 사용자의 자연어 질문에 응답할 수 있는 Transformer 기반 챗봇 구축
- **모델**: Mini Transformer (2~3 레이어 기반, Self Attention 구조)
- **데이터**: 카카오톡에서 제공하는 일상대화 csv 파일을 정제하여 약 40,000개의 Q&A 쌍 구성
- **토크나이저**: Subword 기반 (후반엔 다른 토크나이저로 교체 고려)
- **학습 환경**: Google Colab, TensorFlow 

---

## 📁 파일 구성

| 파일명 | 설명 |
|--------|------|
| `MiniTransformer_base.ipynb` | 초기 실험 모델 |
| `최종본4.ipynb` | 최종 튜닝 완료된 모델 |
| `ChatBotData_split.csv` | 정제된 Q&A 데이터셋 (카카오톡 일상 대화 기반)

---
모델 구조

- `num_layers`: 3
- `d_model`: 128
- `num_heads`: 4
- `dff`: 1024
- `dropout_rate`: 0.2
- `learning_rate`: CustomSchedule (warmup_steps = 4000, multiplier = 1.5)

---

성능 요약

- **최종 정확도** : 약 20%
- 다양한 하이퍼파라미터 조정 시도 (레이어 수, dff 크기, learning rate 등등)
- 낮은 정확도에도 불구하고 Transformer 구조 학습 및 전처리, 스케줄러 경험에 의의

---

한계 및 개선 방향

- 정확도 정체(20% 수준) 문제
- 토크나이저 교체, 불용어 제거, 데이터 품질 향상 필요성
- 향후 공부를 지속 한다면 GPT나 KoAlpaca 등 LLM 기반 미세조정 모델로 발전 계획
