<img width="1124" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/187c1c99-ef69-4e12-a772-1cfc4c31ba68">MY-PROJECT
---------------------
Using Tools: AWS EC2, ECR, S3, Terraform, Jenkins, Helm, Docker, Dockerhub, Minikube k8s, Velero, Vault, Github

Terraform ile AWS üzerinde EC2 intance oluşturma ve üzerinde otomatik olarak " Jenkins " kurulumunu tamamladım. Burada EC2 makinesi oluştururken bu makineye özel bir Jenkins-sg terraform ile oluşturuldu. İlgili jenkins-sg'a 8080 (jenkins), 8200 (vault), 6443 ( minikube) port'larına sadece izin verildi.

<img width="1124" alt="image" src="https://github.com/duranugur/kubernetes-helm-hello-world/assets/57773256/7c1c7bbc-3009-45c1-ba63-31798a158773">


EC2 üzerine jenkins kurulumunu tamamladıktan sonra UI erisimi için " http://ec2-18-184-14-22.eu-central-1.compute.amazonaws.com:8080/" adresine gidilir. Burada CI / CD süreci için ilk kurulumda ilgili jenkins plugin'lerini kurulumu ile tamamladım.

Daha sonra , EC2 server'a clı olarak docker , helm , velero , vault, aws-cli , terraform ve docker component'lerinin kurulumunu tamamladım.

Jenkins:
url : http://ec2-18-184-14-22.eu-central-1.compute.amazonaws.com:8080/

username ve password bilgileri iletilecektir.



