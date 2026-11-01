# Streamlit 화면 이미지 — 백엔드 주소는 실행할 때 BACKEND_URL 환경변수로 넣는다
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8501

CMD ["streamlit", "run", "app.py", "--server.address=0.0.0.0", "--server.port=8501"]
