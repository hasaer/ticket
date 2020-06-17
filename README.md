AWS

AWS IAM User Access Key 생성

IAM > 액세스 관리 > 사용자 > 보안 자격 증명

액세스 키 만들기 > Access Key, Private Key 별도 보관


AWS ECR 생성

ECR > 리포지토리 생성

서비스 별 리포지토리 생성


클러스터 생성

eksctl create cluster --name (Cluster-Name) --version 1.15 --nodegroup-name standard-workers --node-type t3.medium --nodes 3 --nodes-min 1 --nodes-max 3

Access Key, Private Key 입력

Default Region: ap-northeast-2


클러스터 토큰 가져오기

aws eks --region ap-northeast-2 update-kubeconfig --name (Cluster-Name)


도커라이징

docker build -t 271153858532.dkr.ecr.ap-northeast-2.amazonaws.com/(IMAGE_NAME):v1 .


ECR 로그인

aws ecr get-login-password --region ap-northeast-2 | docker login --username AWS --password-stdin 271153858532.dkr.ecr.ap-northeast-2.amazonaws.com


ECR 도커 이미지 푸시

docker push 271153858532.dkr.ecr.ap-northeast-2.amazonaws.com/(IMAGE_NAME):latest


컨테이너라이징

디플로이 생성

kubectl create deploy (NAME) --image=271153858532.dkr.ecr.ap-northeast-2.amazonaws.com/(IMAGE_NAME):v1

서비스 생성

kubectl expose deploy (NAME) --type=ClusterIP --port=8080


