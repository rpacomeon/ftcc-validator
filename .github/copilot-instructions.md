# GitHub Copilot Instructions for FT&CC Validator

> Copilot이 FT&CC 문서 분석 시 참조하는 컨텍스트

---

## 프로젝트 개요

이 프로젝트는 FT(Factory Test) & CC(Compliance Check) 문서 검증을 위한 **프롬프트 템플릿**을 제공합니다.

### 핵심 원칙

1. **AI는 분석만 수행**: Pass/Fail 판정을 하지 않음
2. **사용자가 최종 판단**: AI는 정보 제공 역할
3. **알람 형식 출력**: 문제 유형별로 정리된 형태

---

## 관련 파일

| 파일 | 용도 |
|------|------|
| `prompts/ftcc_analyzer_prompt.md` | 메인 분석 프롬프트 |
| `prompts/user_template.md` | 사용자 입력 템플릿 |
| `prompts/alert_format.md` | 출력 형식 가이드 |
| `prompts/examples.md` | 분석 예시 |

---

## 분석 유형

Copilot이 문서 분석 시 다음 6가지 관점에서 검토:

1. 🔴 **값 불일치** (Value Mismatch) - 심각도 높음
2. 🟠 **범위 이탈** (Out of Range) - 심각도 높음
3. 🟡 **누락 항목** (Missing Items) - 심각도 중간
4. 🟡 **미완료 항목** (Incomplete) - 심각도 중간
5. 🔵 **형식 오류** (Format Error) - 심각도 낮음
6. ⚪ **의심 항목** (Suspicious) - 확인 필요

---

## 프롬프트 사용 방법

### Copilot Chat에서 사용

```
@workspace /ftcc_analyzer_prompt.md 를 참조하여 다음 두 문서를 비교 분석해줘:

[기준 문서 데이터]

[샘플 문서 데이터]
```

### 자세한 사용법

1. `prompts/user_template.md` 양식 복사
2. 기준 문서와 샘플 문서 데이터 붙여넣기
3. Copilot Chat에 전달
4. 알람 형식으로 결과 확인

---

## 주의사항

- AI 분석 결과는 참고용이며 최종 판정은 담당자가 수행
- 의심 항목은 원본 문서와 대조 확인 필요
- 복잡한 조건부 규칙은 추가 프롬프트 설명 필요

---

## 커스터마이징

프로젝트별 FT/CC 양식에 맞게 다음을 수정:

1. **컬럼명 변경**: 실제 문서의 컬럼명으로 수정
2. **허용 범위 규칙**: 제품별 허용 오차 명시
3. **필수 항목 정의**: 반드시 있어야 하는 항목 목록
4. **형식 규칙**: 날짜, 숫자 등 데이터 형식 정의
