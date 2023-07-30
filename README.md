MY-PROJECT
---------------------
Using Tools: AWS EC2, ECR, S3, Terraform, Jenkins, Helm, Docker, Dockerhub, Minikube k8s, Velero, Vault, Github

Terraform ile AWS üzerinde EC2 intance oluşturma ve üzerinde otomatik olarak " Jenkins " kurulumunu tamamladım. Burada EC2 makinesi oluştururken bu makineye özel bir Jenkins-sg terraform ile oluşturuldu. 

<img width="1124" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/7c1c7bbc-3009-45c1-ba63-31798a158773">

EC2 üzerine jenkins kurulumunu tamamladıktan sonra UI erisimi için " http://ec2-18-184-14-22.eu-central-1.compute.amazonaws.com:8080/" adresine gidilir. Burada CI / CD süreci için ilk kurulumda ilgili jenkins plugin'lerini kurulumu ile tamamladım.

Server bağlantısı için EC2-connect ile server'a bağlandım.

<img width="895" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/b2032a3d-ed25-4501-be6f-b08dbd4ef723">

İlgili jenkins-sg'a 8080 (jenkins), 8200 (vault), 6443 ( minikube) port'larına sadece izin verildi.

<img width="1512" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/297439ec-45a4-4616-a12f-9440cbae4b0e">

Daha sonra , EC2 server'a clı olarak docker , helm , velero , vault, aws-cli , terraform ve docker component'lerinin kurulumunu tamamladım.

AWS IAM:

AWS console yönetimi için admin ve developer user'ları yetkileri ile oluşturuldu.

<img width="1512" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/ad21d4b9-0eb6-4ea2-939f-f82340939e5e">


ECR Registry:

Uygulama dockerize işlemi sonrası 2 farklı Registry için image'larımızı pushladık.
İlk olarak ECR Reposunda charts reposu altına image'larımızı backuplıyoruz.

<img width="1510" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/4d30a26d-aff9-49af-a238-a3740da76481">

Daha sonra kendi dockerhub repo altına uguduran/myrepo altına pushluyoruz.
<img width="1508" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/5cdd8747-2619-4da6-80a1-aa65a939e99d">

Vault:

url: https://ec2-18-184-14-22.eu-central-1.compute.amazonaws.com:8200
<img width="1512" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/2c5a2190-1547-4428-b93e-52a8e1fb5963">


S3 helm backup:

Helm paketlerini backup almak için aws-cli ile s3'e backup olusturuldu.
<img width="1512" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/686b8231-2b2c-4f1b-96ca-4efd45b50c23">

Jenkins:
url : http://ec2-18-184-14-22.eu-central-1.compute.amazonaws.com:8080/

username ve password bilgileri terraform README.md içerisinde iletilecektir.
<img width="1512" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/17eb85c7-59a7-4952-b6b6-7a071691a258">
<img width="1511" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/e0cf7668-857d-4a19-827c-37597fb9a2aa">

Minikube k8s:

EC2 server üzerine uygulamalarızı k8s altyapısı ile deploy edildi.
<img width="1512" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/ad70ef62-1ecf-460a-bf7d-8316f41915e4">












