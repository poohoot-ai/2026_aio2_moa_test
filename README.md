# Moa 테스트

## 로컬 확인 (푸시전)
```powershell
uv venv -p 3.11                         # 처음 한 번 — 작업 폴더 안에 .venv를 만든다
uv pip install -r requirements.txt      # 처음 한 번 — CI 러너와 같은 목록으로 설치
uv run pytest -q                        # 테스트 통과 확인 — 기대 결과: 5 passed
uv run uvicorn app.main:app --reload    # http://127.0.0.1:8000/docs 에서 API 확인

```

## 커버리지 기준 (5단계)
```powershell
uv run pytest -q --cov=app --cov-fail-under=85   # 기대 결과: 5 passed, Total coverage 85.71% → 통과
uv run pytest -q tests/test_api.py --cov=app --cov-fail-under=85   # 검사기 테스트를 빼면 80.95% → 실패 (종료 코드 1)
```