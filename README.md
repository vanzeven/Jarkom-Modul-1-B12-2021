# Jarkom-Modul-1-B12-2021

Anggota: Faisal Reza M 05111940000009

1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!
  - buka file pcap 1-5
  - masukkan (display) filter http.host == "ichimarumaru.tech"
  - klik kanan > follow tcp stream frame yang mana saja
  ![image](https://user-images.githubusercontent.com/11045113/134754618-f6af7e3f-dc84-4b17-93f5-67d15b7b11d2.png)
  - webserver yang digunakan adalah nginx
2. Temukan paket dari web-web yang menggunakan basic authentication method!
3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!
4. Temukan paket mysql yang mengandung perintah query select!
5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!
6. Cari username dan password ketika melakukan login ke FTP Server!
7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!
9. Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
10 .Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 
12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!
15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
