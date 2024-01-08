FROM matenduel/cloudwave:practice.v1
#RUN apt-get update && apt-get upgrade && apt-get install -y curl
#
#RUN mkdir -p /scripts
#COPY ./install-k8s.sh /scripts
#
##kubectl install
#WORKDIR /scripts
#RUN chmod +x install-k8s.sh
#RUN ./install-k8s.sh
# Kubectl
RUN apt-get update
# apt-transport-https may be a dummy package; if so, you can skip that package
RUN apt-get install -y apt-transport-https ca-certificates curl

RUN curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.29/deb/Release.key | gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg

RUN echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.29/deb/ /' | tee /etc/apt/sources.list.d/kubernetes.list

RUN apt-get update
RUN apt-get install -y kubectl

#AWS CLI 설치

RUN apt install -y unzip
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN chmod +x ./aws/install
RUN ./aws/install

# Kubectx & Kubens
#RUN apt install kubectx

# Or
RUN git clone https://github.com/ahmetb/kubectx /opt/kubectx && ln -s /opt/kubectx/kubectx /usr/local/bin/kubectx && ln -s /opt/kubectx/kubens /usr/local/bin/kubens