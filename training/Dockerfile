FROM pytorch/pytorch

#update and install some non-pip installable dependancies
RUN apt update -y && apt upgrade -y && apt-get install gcc libsm6 libxext6 libgl1 libglib2.0-0 git -y

# Install sagemaker-training toolkit that contains the common functionality necessary to create a container compatible with SageMaker and the Python SDK.
RUN pip3 install sagemaker-training

# Copies the training code inside the container
ADD yolov7 /opt/ml/code/

RUN pip3 install -r /opt/ml/code/requirements.txt

# Defines train.py as script entrypoint
ENV SAGEMAKER_PROGRAM train.py