# 📱 SenTic Native

> AI 영어 소통 학습 파트너 **SenTic**의 모바일 앱 (React Native · Expo)
> 팀 **SenTic** · 2026

![React Native](https://img.shields.io/badge/-React%20Native-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Expo](https://img.shields.io/badge/-Expo%2054-000020?style=flat-square&logo=expo&logoColor=ffffff)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=ffffff)
![React](https://img.shields.io/badge/-React%2019-61DAFB?style=flat-square&logo=react&logoColor=000000)

## 소개

SenTic은 AI 파트너와 **실제 상황을 연습하듯 영어로 대화**하고, 내가 한 말에 대해 **더 자연스러운 표현 피드백**을 받는 영어 학습 앱이에요.
카페 주문, 공항 체크인, 팀 미팅처럼 구체적인 상황을 고르고, 음성 통화나 채팅으로 대화를 이어 가요.

이 저장소는 웹(Vite + React)으로 먼저 만든 SenTic 프로토타입을 **Expo React Native 앱으로 옮긴 버전**이에요.
하나의 코드로 Android · iOS · 웹 미리보기에서 모두 실행돼요.

> 지금은 UI와 화면 흐름 중심의 프로토타입이라, 대화 내용과 학습 통계는 예시 데이터로 채워져 있어요.

## 주요 화면

| 화면 | 설명 |
|---|---|
| 🔐 **로그인 · 회원가입 · 계정 찾기** | 아이디/비밀번호 로그인(비밀번호 보기 토글), 카카오 · Google 소셜 로그인 버튼, 이메일 기반 가입과 계정 찾기 |
| 🏠 **홈 (학습 모드 선택)** | 연속 학습 일수(🔥 streak), 음성 대화 / 채팅 대화 모드 카드, 요일별 학습 시간 막대 그래프, 총 대화 수 · 학습 시간 · 저장 표현 통계 |
| 🗂 **상황 선택** | 음성: 카페에서 주문하기(초급) · 공항 체크인(중급) · 팀 미팅 참여(고급)<br>채팅: 친구와 스몰톡 · 여행 계획 세우기 · 업무 메시지 |
| 🎯 **상황 설정** | 선택한 상황의 오늘의 목표 체크리스트와 난이도 · 피드백 · 자막 설정 확인 후 연습 시작 |
| 🎙 **음성 대화** | AI 파트너와 통화 시작/종료, 마이크 · 스피커 토글, 실시간 자막, `통화 / 대화내역 / 피드백` 탭, 피드백 ON/OFF |
| 💬 **채팅 대화** | 말풍선 채팅, 메시지 전송 시 AI 답장과 함께 **추천 표현 피드백** 표시 |
| 👤 **마이페이지 외** | 마이페이지, 설정, 프리미엄, 저장한 표현, 공지사항, FAQ |

## 화면 흐름

```
로그인 ─┬─ 회원가입
        ├─ 계정 찾기
        └─▶ 홈(학습 모드)
              ├─ 🎙 음성 대화 ─▶ 상황 선택 ─▶ 상황 설정 ─▶ 음성 통화 (통화 · 대화내역 · 피드백)
              ├─ 💬 채팅 대화 ─▶ 상황 선택 ─▶ 상황 설정 ─▶ 텍스트 채팅 (+ 추천 표현)
              └─ 마이페이지 · 설정 · 프리미엄 · 저장한 표현 · 공지사항 · FAQ
```

## 기술 스택

| 구분 | 사용 기술 |
|---|---|
| 앱 | React Native 0.81, Expo SDK 54, React 19, TypeScript 5.9 |
| UI | React Native 기본 컴포넌트 + `StyleSheet` (메인 컬러 `#4F46E5`) |
| 화면 전환 | 상태 기반 화면 스위칭 (`useState<Screen>`) |
| 기타 | `expo-status-bar`, `react-native-safe-area-context` |

## 폴더 구성

```
sentic-native/
├─ App.tsx          # ✅ Expo 앱 본체 (모든 화면 · 컴포넌트 · 스타일)
├─ app.json         # Expo 설정 (앱 이름 SenTic, 세로 고정, 태블릿 지원)
├─ package.json
└─ src/             # 📎 원본 웹 프로토타입 (Vite + React Router + Tailwind + shadcn/ui)
   └─ app/components/   # 화면별 컴포넌트 (login, mode-select, voice-chat, text-chat, payment ...)
```

`src/` 폴더는 React Native로 옮기기 전의 웹 버전 코드를 참고용으로 남겨 둔 거예요. 앱 실행에는 루트의 `App.tsx`만 사용해요.

## 실행 방법

```bash
npm install
npm start          # Expo 개발 서버 실행
```

실행 후 터미널 메뉴에서 선택해요.

- 📱 휴대폰: **Expo Go** 앱으로 QR 코드 스캔
- 🤖 `a` Android 에뮬레이터 / 🍎 `i` iOS 시뮬레이터 / 🌐 `w` 웹 미리보기

## 관련 저장소

- [SenTic-DMU/Frontend](https://github.com/SenTic-DMU/Frontend) · SenTic 팀 프론트엔드
- [SenTic-DMU/Backend](https://github.com/SenTic-DMU/Backend) · SenTic 팀 백엔드

---

<sub>UI 일부는 [shadcn/ui](https://ui.shadcn.com/)(MIT)와 [Unsplash](https://unsplash.com) 이미지를 사용했어요. 자세한 내용은 [ATTRIBUTIONS.md](ATTRIBUTIONS.md)를 참고하세요.</sub>
