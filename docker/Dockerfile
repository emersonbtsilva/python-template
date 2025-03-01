FROM python:3.12 as builder

WORKDIR /app
COPY src/requirements.txt .
RUN pip install --user --no-cache-dir -r requirements.txt

FROM python:3.12

WORKDIR /app
COPY --from=builder /root/.local /root/.local
COPY src/ /app/

ENV PATH=/root/.local/bin:$PATH
CMD ["python", "app/main.py"]