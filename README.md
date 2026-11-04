# Streamlit 실습

현재 앱은 **점심 메뉴 고르기** 실습입니다. 예산, 매운 음식 허용 여부, 음식 종류를 선택하면 조건에 맞는 메뉴를 보여 줍니다.
현재 단계에서는 API 키 없이 실행되며 Gemini 요청도 보내지 않습니다.

## Community Cloud 설정

- Repository: `kangseok0427/streamlib-lab`
- Branch: `main`
- Main file path: `app.py`
- Python: `3.12` 권장 (`3.11` 이상)

앱이 이미 배포되어 있으면 main의 파일 변경이 자동 반영됩니다.
의존성 설치가 끝난 뒤 브라우저에서 `Ctrl+Shift+R`(macOS: `Cmd+Shift+R`)로 새로고침하세요.

## 실행

```bash
python -m pip install -r requirements.txt
python -m streamlit run app.py
```

## AI 실습으로 넘어갈 때

`requirements.txt`에는 수업용 Streamlit과 Google GenAI SDK 버전을 고정했습니다.
AI 실습 코드를 app.py에 적용한 뒤 Streamlit 앱의 **Settings → Secrets**에서 다음 값을 설정합니다.

```toml
GEMINI_API_KEY = "발급받은_API_키"
```

실제 API 키는 소스나 GitHub에 넣지 마세요. 로컬용 `.streamlit/secrets.toml`은 `.gitignore`로 제외합니다.

## Metric 표시 오류 우회

`Failed to fetch dynamically imported module: .../Metric.*.js` 오류를 피하기 위해 숫자 두 곳을 `st.caption`과 `st.subheader`로 표시합니다.
메뉴 데이터와 필터 조건은 유지합니다. 이 변경은 Metric 부품 사용을 피하는 우회이며, 브라우저 캐시·네트워크 등 원인을 확정한 것은 아닙니다.
