FROM python:3.6.9-stretch as build-stage
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
RUN python -m spacy download en_core_web_md
RUN python -m spacy download fr_core_news_md
RUN python -m spacy link en_core_web_md en
RUN python -m spacy link fr_core_news_md fr
RUN rasa train -c config.yml -d domain.yml
RUN rasa run actions &
RUN rasa run --enable-api --endpoints endpoints.yml --cors "*"
EXPOSE 5005