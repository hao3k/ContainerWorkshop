FROM python:3.11-slim

WORKDIR /app

ENV PORT=5000 \
    INSTANCE_NAME="task1" \
    INSTANCE_HASH="task1" \
    PYTHONUNBUFFERED=1

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["sh", "./run.sh"]