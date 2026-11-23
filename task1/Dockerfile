FROM python:3.11-slim AS builder

WORKDIR /src

ENV PORT=5000 \
    INSTANCE_NAME="task1" \
    INSTANCE_HASH="task1" \
    PYTHONUNBUFFERED=1


COPY main.py .
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

WORKDIR /app
COPY public public
COPY templates templates 
COPY --from=builder /src/app .
COPY . .

EXPOSE ${PORT}

CMD ["sh", "./run.sh"]
