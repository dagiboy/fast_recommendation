FROM python:3.10

RUN pip3 install kaggle tqdm
COPY kaggle.json /root/.kaggle/
COPY src/download_dataset.py src/
RUN python src/download_dataset.py

COPY src/process_data.py src/
RUN python src/process_data.py

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY src src

ENTRYPOINT ["python", "src/model.py"]
