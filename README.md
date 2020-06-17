<b>AWS</b>

<b>AWS IAM User Access Key 생성</b>

IAM > 액세스 관리 > 사용자 > 보안 자격 증명

액세스 키 만들기 > Access Key, Private Key 별도 보관

----

<b>AWS ECR 생성</b>

ECR > 리포지토리 생성

서비스 별 리포지토리 생성

----

<b>클러스터 생성</b>

eksctl create cluster --name (Cluster-Name) --version 1.15 --nodegroup-name standard-workers --node-type t3.medium --nodes 3 --nodes-min 1 --nodes-max 3

Access Key, Private Key 입력

Default Region: ap-northeast-2

----

<b>클러스터 토큰 가져오기</b>

aws eks --region ap-northeast-2 update-kubeconfig --name (Cluster-Name)

----

<b>Maven 빌드</b>

mvn package -Dmaven.test.skip=true

또는 IntelliJ > Maven > Lifecycle > clean & package

----

<b>도커라이징</b>

docker build -t 271153858532.dkr.ecr.ap-northeast-2.amazonaws.com/(IMAGE_NAME):v1 .

----

<b>ECR 로그인</b>

aws ecr get-login-password --region ap-northeast-2 | docker login --username AWS --password-stdin 271153858532.dkr.ecr.ap-northeast-2.amazonaws.com

----

<b>ECR 도커 이미지 푸시</b>

docker push 271153858532.dkr.ecr.ap-northeast-2.amazonaws.com/(IMAGE_NAME):v1

----

<b>컨테이너라이징</b>

디플로이 생성

kubectl create deploy (NAME) --image=271153858532.dkr.ecr.ap-northeast-2.amazonaws.com/(IMAGE_NAME):v1

서비스 생성

kubectl expose deploy (NAME) --type=ClusterIP --port=8080

kubectl deploy -f deployment.yaml

----

<b>Pod 테스트</b>

----

https://workflowy.com/s/msa/27a0ioMCzlpV04Ib#/5c459b8ad974

----

<b>Cluster에 Kafka 설치</b>

https://workflowy.com/s/msa/27a0ioMCzlpV04Ib#/d3169f4b644e

----

<b>운영 :  서비스 매시 - Istio ~ Circuit Breaking, Retry</b>

https://workflowy.com/s/msa/27a0ioMCzlpV04Ib#/377f767d80a6


----
<b>Todo</b>

Autoscale

부하테스트

liveness/readiness probe

ci/cd pipeline



