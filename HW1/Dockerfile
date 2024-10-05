FROM python:3.8-slim AS builder
RUN apt-get update && apt-get install -y binutils
RUN pip install pyinstaller
WORKDIR /app
RUN echo "print('This is Task 8 of the DevOps course.')" > sample_script.py
RUN pyinstaller --onefile sample_script.py

FROM ubuntu:22.04
RUN apt-get update && apt-get install -y libstdc++6
COPY --from=builder /app/dist/sample_script /sample_script
CMD ["/sample_script"]