# edgex-install-step

## 1. device-sdk-c
cd /root  

git clone https://github.com/edgexfoundry/device-sdk-c.git  

cd device-sdk-c  

git branch -a (檢查目前branch)  

git checkout v2.0.0  

docker build -t edgex-csdk-base:2.0.0 -f scripts/Dockerfile.alpine-base .  

docker image ls (檢查有沒有build成功)

## 2. device-sdk-c_KS-M01
cd /root  

git clone https://github.com/bighb69738/device-sdk-c_KS-M01.git  

帳號 bighb69738  

密碼 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  

cd device-sdk-c_ks-M01  

docker build -t edgex-csdk-test -f scripts/Dockerfile.alpine-test .  

docker image ls (檢查[edgex-csdk-test]有沒有build出來

## 3. device-mqtt-go
cd /root  

git clone https://github.com/bighb69738/device-mqtt-go.git  

帳號 bighb69738  

密碼 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  

cd device-mqtt-go  

make docker  

cp ./docker-compose.yml /etc/EdgeX  

cp -r ./custom-config /etc/EdgeX  

cp -r ./res /etc/EdgeX  

vim ./EdgeX.sh  (最後一行docker-compose指令後面的檔名改成docker-compose.yml  

vim ./EdgeXdown.sh  (最後一行docker-compose指令後面的檔名改成docker-compose.yml   

cd /etc/EdgeX  

docker-compose -p edgex -f docker-compose.yml  up -d

## 4. check
Normally, 13 containers are running
