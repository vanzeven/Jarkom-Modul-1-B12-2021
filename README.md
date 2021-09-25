# Jarkom-Modul-1-B12-2021

Anggota: Faisal Reza M 05111940000009

## 1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"! #
  - buka file pcap 1-5
  - masukkan (display) filter http.host == "ichimarumaru.tech"
  - klik kanan > follow tcp stream frame yang mana saja
  - ![image](https://user-images.githubusercontent.com/11045113/134757566-0385b7d7-2b09-4635-964c-8aca016d6060.png)
  
  - webserver yang digunakan adalah nginx
## 2. Temukan paket dari web-web yang menggunakan basic authentication method! #
  - masukkan filter http.authbasic
  - ![image](https://user-images.githubusercontent.com/11045113/134757835-804b5989-19d3-4e82-b804-6d0f74bbcb39.png)

## 3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng! #
  - buka web tersebut
  - ![image](https://user-images.githubusercontent.com/11045113/134758193-1f346293-4637-488d-b60d-55e38d8bab4d.png)
  - basic auth akan diminta
  - untuk mendapatkan basic auth, masukkan filter di no2, pilih salah satu frame, lalu lihat di kolom tengah, akan terlihat kredensialnya
  - ![image](https://user-images.githubusercontent.com/11045113/134758572-462c6c83-735b-403f-9b9b-1d190b21f67f.png)
  - masukkan basicauth
  - kerjakan soal di website
  - ![image](https://user-images.githubusercontent.com/11045113/134758591-678b9b51-f7c2-4c1f-80d5-2f2504240c1e.png)

### 4. Temukan paket mysql yang mengandung perintah query select! #
  - masukkan filter mysql.query matches "SELECT"
  - ![image](https://user-images.githubusercontent.com/11045113/134758770-df4af5b9-fc5e-484e-a145-05f7569ea38a.png)

## 5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap! #
  - masukkan filter mysql.query ~ "insert" (~ artinya sama dengan matches)
  - ![image](https://user-images.githubusercontent.com/11045113/134758814-6c6cf959-bfd0-4c38-98f3-e3486b155b7b.png)
  - buka website portal dst
  - masukkan kredensial ke website
  - kerjakan soal di website
  - ![image](https://user-images.githubusercontent.com/11045113/134758877-d93c456a-776a-4357-be15-bc56fb49946f.png)

## 6. Cari username dan password ketika melakukan login ke FTP Server! #
  - buka file pcap 6-7
  - masukkan df (display filter) ftp.request.command matches user
  - ![image](https://user-images.githubusercontent.com/11045113/134759135-3766f603-3a41-444e-bf8a-3d07d30e28f5.png)
  - masukkan df ftp.request.command matches pass
  - ![image](https://user-images.githubusercontent.com/11045113/134759154-d899d051-4920-4a72-a049-5a72fbead8a3.png)

## 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf") #
  - masukkan df frame contains "Real.pdf"
  - klik kanan salah satu paket > follow tcp stream
  - ![image](https://user-images.githubusercontent.com/11045113/134759181-05731974-51d4-4e19-935a-efd7f22832fc.png)
  - ![image](https://user-images.githubusercontent.com/11045113/134759186-bc6c3ffb-efb5-4696-ad09-ab28669538bc.png)
  - ![image](https://user-images.githubusercontent.com/11045113/134759190-a17852a5-e4be-4c9d-a493-0cb1f4761315.png)

## 8. Cari paket yang menunjukan pengambilan file dari FTP tersebut! #
  - buka file pcap 9-10
  - masukkan df ftp.request.command == RETR
  - ![image](https://user-images.githubusercontent.com/11045113/134759298-6592570a-f01c-4fa7-b91c-09361a835e1c.png)

## 9. Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut! #
  - (maaf saya tidak tahu cara menggunakan display filter, jadi saya menggunakan cara khas CTF) gunakan ctrl + F dengan mode hex untuk mencari “50 4B 03 04” yang merupakan hex signature dari file zip, lalu akan ditemukan bahwa packet yang mengadung zip adalah frame 170
  - frame yang ditunjuk adalah frame 170
  - ![image](https://user-images.githubusercontent.com/11045113/134759356-ae6c33bb-3960-407a-ad15-1befd1c7e0f7.png)
  - ![image](https://user-images.githubusercontent.com/11045113/134759364-9e56ab45-6c52-44e1-86fb-020987f10f29.png)
  - hasil file zip
  - ![image](https://user-images.githubusercontent.com/11045113/134759378-82bfbe1a-26e0-4051-8d8e-905c635d5812.png)

## 10 .Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"! #
  - masukkan df frame contains "history.txt"
  - ![image](https://user-images.githubusercontent.com/11045113/134759435-c616f811-142f-4ef6-9353-6a5aeffc163a.png)
  - ![image](https://user-images.githubusercontent.com/11045113/134759392-1e5c6e79-58da-42de-bc2d-f9d8373b2b7c.png)
  - ![image](https://user-images.githubusercontent.com/11045113/134759399-dde1e5bf-0527-419d-b23d-e7bc35d0f893.png)
  - ![image](https://user-images.githubusercontent.com/11045113/134759405-baaf385a-8f0f-42d6-8abd-f48570d52beb.png)

## 11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!  #
  - mcf (masukkan capture filter) src port 80
  - ![image](https://user-images.githubusercontent.com/11045113/134759465-8c231bcc-4a31-4992-aa41-8d0af9192d91.png)

## 12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21! #
  - mcf port 21
  - ![image](https://user-images.githubusercontent.com/11045113/134759478-e391c643-7e6d-46dd-b63b-8e666476d539.png)

## 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443! #
  - mcf dst port 443
  - ![image](https://user-images.githubusercontent.com/11045113/134759522-b9159bdc-e10e-4508-8c7b-085317aa3ad6.png)

## 14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id! #
  - dst host kemenag.go.id
  - ![image](https://user-images.githubusercontent.com/11045113/134759536-0418b9cb-a374-4d97-8572-bd6d22692321.png)

## 15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian! #
  - cari ip menggunakan ipconfig
  - ![image](https://user-images.githubusercontent.com/11045113/134759559-67366280-d851-4de8-a015-91054d93d2b3.png)
  - mcf src net 192.168.43.158
  - ![image](https://user-images.githubusercontent.com/11045113/134759595-044d185b-edfc-4b81-af90-0a37a71edf4b.png)

## Kendala #
  - Tidak ada teman untuk diskusi (karena praktikum saya sendirian)
