## PENJELASAN HOMEWORK DOCKER DTS TA ACADEMY 2021

- Merupakan sebuah aplikasi to-do-list yang berasal dari sumber [https://github.com/schadokar/go-to-do-app](https://github.com/schadokar/go-to-do-app)
- Pembuatan *contenarization* aplikasi terdiri dari 3 image yaitu :
  - Aplikasi Client(yang menggunakan ReactJS)
  - Aplikasi Backend(menggunakan Golang)
  - MongoDB Database

### 1. *Contenarization* Aplikasi Client

​	Pada folder client dibuat sebuah dockerfile untuk membuat image aplikasi client dari to-do-list dan ditambahkan sebuah config untuk *nginx*

- Image dari aplikasi client dapat diakses ke dalam dockerhub 

  [Docker Hub Aplikasi Client](https://hub.docker.com/repository/docker/ahmadirfaan/gotodoapp-client)

- Untuk menjalankan sebuah aplikasi client ini dibutuhkan environment :
  **REACT_APP_API**  : environment ini mendefinisikan sebuah endpoint dari server

### 2. *Contenarization* Server

​	Pada tahap ke-2 dibuat sebuah dockerfile untuk membuat sebuah aplikasi server dari to-do-list yang nantinya akan mengakses mongodb database

- Image dari aplikasi server dapat diakses 

  [Docker Hub Aplikasi Server](https://hub.docker.com/repository/docker/ahmadirfaan/gotodoapp-server)

- Dibutuhkan beberapa *environment* agar aplikasi dapat berjalan dengan normal :
  **DB_URI** : environment ini mendefinisikan sebuah uri dari database mongo****
  **DB_NAME**: environment ini merupakan definisi dari database di mongodb
  **DB_COLLECTION_NAME**: environment ini mendefinisikan sebuah collection di mongodb

### 3. Docker Compose

​	Pada tahap ke-3 dilakukan sebuah docker compose untuk ke-3 image yaitu client, server, dan database yaitu mongodb. 

dengan melakukan pengaturan environment yang dibutuhkan, lalu mengexpose port yang ada pada aplikasi 

dan mendefinisikan image yang akan digunakan. Image yang digunakan pada docker compose telah di *push* di dockerhub sehingga pada pembuatan docker compose langsung saja pull dari dockerhub yang telah dibuat.