FROM python:3.6

ENV APP_FOLDER='/application'
ENV LOCAL_FOLDER_APP=.

RUN mkdir $APP_FOLDER
COPY $LOCAL_FOLDER_APP $APP_FOLDER
RUN pip install -r $APP_FOLDER/requirements.txt
WORKDIR $APP_FOLDER
CMD ["python","-u","app.py"]