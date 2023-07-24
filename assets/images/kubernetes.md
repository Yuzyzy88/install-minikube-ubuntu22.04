## Monolith & Microservice

- Monolith adalah membuat seluruh fitur aplikasi menjadi satu di dalam aplikasi.
- Microservices adalah seluruh fitur dipecah menjadi kecil-kecil, setiap fitur memiliki fungsionalitas aplikasi yang spesifik yang nanti akan saling berkomunikasi.

![monoith vs microservice](assets\images\1-monolith-vs-microservices.jpg)

## Virtual Machine (VM) & Container

Ketika mendeploy sebuah aplikasi maka diperlukan sistem operasi (OS). VM dapat membuat dan menjalankan beberapa sistem operasi. Namun untuk men setup sebuah OS didalam VM memerlukan banyak waktu dan saat menjalankan aplikasi maka harus menjalankan OS VM dan OS didalam VM terlebih dahulu.

Saat menggunakan container kita dapat menjalankan aplikasi didalam container. Container akan menggunakan OS bawaan. Aplikasi yang terisolated tidak dapat mengakses host os dengan mudah. Karena tidak butuh OS didalam container sehingga mempercepat ketika menjalankan aplikasi.

![container & vm](assets\images\2-container-vm.jpg)

## Docker Deployment

![docker deployment](assets\images\3-docker-deployment.jpg)

## Kubernetes

- Kubernetes "K8s" adalah aplikasi untuk automation deployment, scaling dan manajemen aplikasi berbasis container.
- Dibuat oleh Google dan maintained sekarang oleh Cloud Native Computing Foundation (CNCF)

![docker deployment](assets\images\4-kubenertes-work-flow.png)

Objek mendasar Kubernetes termasuk:

- Pod
- Service
- Volume
- Namespac


### Kubernetes Master

Kubernetes Master terdiri dari tiga buah process yang dijalankan pada sebuah node kluster. Node ini disebut sebagai _master_, yang terdiri dari kube-apiserver, kube-controller-manager, dan kube-scheduler.

- kube-apserver bertugas sebagai API yang digunakan untuk berinteraksi dengan Kubernetes Cluster.

- etcd bertugas sebagai databse untuk menyimpan data Kubernetes Cluster.
- kube-scheduler bertugas untuk memperhatikan aplikasi yang kita jalankan dan meminta Node untuk menjalankan aplikasi yang kita jalakan.

- kube-controller-manager bertugas melakukan kontrol terhadap Kubernetes Cluster.

- cloud-controller-manager bertugas untuk malakukan kontrol terhadap interaksi dengan cloud provider.

### Kubernetes Nodes

- Kubelet berjalan di setiap node dan bertugas untuk memastikan bahwa aplikasi kita berjalan di Node.

- kube-proxy berjalan di setiap Node dan bertugas sebagai proxy terhadap arus network yang masuk ke aplikasi kita dan sebagai load balancer (Load balancing adalah proses pendistribusian traffic jaringan ke beberapa server).

- container-manager berjalan di setiap Node dan bertugas sebagai container manager. Kubernetes mendukung beberapa container manager seperti Docker, container dan lainnya.

_Src: Programmer Zaman Now_
