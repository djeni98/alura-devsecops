FROM python:3.13
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
CMD ["uvicorn", "--host", "0.0.0.0", "run:app", "--port", "3000"]