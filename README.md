# Toss NEXT ML Challenge - CTR Prediction

**Author:** woohyeokLi · **Date:** 2026-07-01

토스 NEXT ML CHALLENGE 광고 클릭 예측(CTR) 공모전 코드 정리 저장소입니다.

익명화된 광고 노출 로그 데이터를 기반으로 사용자의 광고 클릭 여부를 예측하는 이진 분류 문제를 다뤘습니다.
본 저장소에는 데이터 구조를 확인한 **EDA 노트북**과 최종 학습 및 제출 파일 생성을 위한 **모델링 노트북**을 포함했습니다.

원본 데이터는 대회 규정 및 데이터 공개 제한 가능성을 고려하여 포함하지 않았습니다.

## Result

* Participants: 2,891명
* Teams: 709팀
* Rank: 73 / 709 teams
* Percentile: Top 10.3%
* Role: 개인 참가

## Files

* `EDA.ipynb`
  데이터 구조 확인, 결측/상수 컬럼 점검, 주요 피처 분포 및 클릭률 분석

* `ensemble.ipynb`
  Feature Engineering, 3-Fold 학습, CatBoost/XGBoost 앙상블, 제출 파일 생성

## Approach

* 결측 패턴 및 상수 컬럼 확인
* 시간대/요일 기반 파생변수 생성
* `seq` 컬럼 기반 길이, 고유값 수, 다양성 비율 파생
* K-Fold Target Encoding
* CatBoost, XGBoost 기반 모델 학습
* OOF 기준 앙상블 가중치 선택

## Data

원본 데이터와 제출 파일은 저장소에 포함하지 않았습니다.
대회 데이터는 주최 측에서 제공한 파일을 사용해야 합니다.

## how to run (google colab)

이 저장소는 로컬 환경이 아닌 **Google Colab 기준**으로 작성되었습니다.

1. 대회 데이터를 Colab 또는 Google Drive에 업로드합니다.
2. `EDA.ipynb`로 데이터 구조를 확인합니다.
3. `ensemble.ipynb`에서 데이터 경로를 본인 환경에 맞게 수정합니다.
4. GPU 런타임에서 노트북을 순서대로 실행합니다.
5. 실행 완료 후 제출용 CSV 파일이 생성됩니다.

필요한 패키지 설치 명령은 노트북 상단에 포함되어 있습니다.
