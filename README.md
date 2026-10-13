1. Eksekusi seluruh profile yang ada :
a. Edit file profile /etc/profile dan tampilkan pesan sebagai berikut :
echo “Profile dari /etc/profile”
<img width="1280" height="800" alt="1a" src="https://github.com/user-attachments/assets/04d1c46e-1f10-4384-b697-f1bc5cee2f6b" />

b. Asumsi nama anda stD02001, maka edit semua profile yang ada yaitu :
/home/stD02001/.bash_profile
/home/. stD02001/.bash_login
/home/mahasiswa/.profile 
/home/mahasiswa/.bashrc
Ganti nama /home/mahasiswa dengan nama anda sendiri. Pada setiap 
file tersebut, cantumkan instruksi echo, misalnya pada /home/ 
mahasiswa/.bash_profile :
echo “Profile dari .bash_profile”
Lakukan hal yang sama untuk file lainnya, sesuaikan tampilan dengan nama file
yang bersangkutan.
<img width="1280" height="800" alt="1b" src="https://github.com/user-attachments/assets/390cfe8f-9620-4242-9dec-162e6d6727bc" />

c. Jalankan instruksi subtitute user, kemudian keluar dengan perintah exit sebagai 
berikut:
$ su mahasiswa
$ exit
kemudian gunakan opsi – sebagai berikut :
$ su – mahasiswa
$ exit
Jelaskan perbedaan kedua utilitas tersebut.
<img width="1280" height="800" alt="1c" src="https://github.com/user-attachments/assets/0dc9ab7c-ad2a-4a3d-ada7-893dd5674f53" />

2. Prompt String (PS)
a. Edit file .bash_profile, ganti prompt PS1 dengan ‘>’. Instruksi export diperlukan 
dengan parameter nama variable tersebut, agar perubahan variable PS1 dikenal 
oleh semua shell
PS1=’> ‘ 
export PS1
<img width="1280" height="800" alt="2a" src="https://github.com/user-attachments/assets/40911d72-c38f-41c4-9702-88cb364523ad" />

b. Eksperimen hasil PS1 :
$ PS1=“\! > “ 
69 > PS1=”\d > “ 
Mon Sep 23 > PS1=”\t > “ 
10:10:20 > PS1=”Saya=\u > “ 
Saya=mahasiswa > PS1=”\w >” 
~ > PS1=\h >”
<img width="1280" height="800" alt="2b" src="https://github.com/user-attachments/assets/42fa5b79-72a4-4e8a-a47b-fb40ca518001" />

3. Logout
Edit file .bash_logout, tampilkan pesan dan tahan selama 5 detik, sebelum eksekusi 
logout
Echo “Terima kasih atas sesi yang diberikan” 
Sleep 5 
clear
<img width="1280" height="800" alt="3" src="https://github.com/user-attachments/assets/0a10c369-6314-4aff-b9d4-8397d4359646" />
Bash script

4. a. Buat 3 buah script p1.sh, p2.sh, p3.sh dengan isi masing-masing :
p1.sh 
#! /bin/bash 
echo “Program p1” ls –l
p2.sh 
#! /bin/bash 
echo “Program p2” who
p3.sh 
#! /bin/bash 
echo “Program p3” ps x

b. Jalankan script tersebut sebagai berikut :
$ ./p1.sh ; ./p3.sh ; ./p2.sh
$ ./p1.sh &
$ ./p1.sh $ ./p2.sh & ./p3.sh &
$ ./p1.sh ; ./p3.sh ) &
<img width="1280" height="800" alt="4a b" src="https://github.com/user-attachments/assets/e5999b99-0344-4d52-a66a-586f1a104d5d" />

5. Jobs
a. Buat shell-script yang melakukan loop dengan nama pwaktu.sh, setiap 10 detik, 
kemudian menyimpan tanggal dan jam pada file hasil.
#!/bin/bash 
while [ true ] 
do 
date >> hasil 
sleep 10
done
<img width="1280" height="800" alt="5a" src="https://github.com/user-attachments/assets/af952419-a081-41bc-985b-44ea899d2513" />

b. Jalankan sebagai background; kemudian jalankan satu program (utilitas find) di 
background sebagai berikut :
$ jobs
$ find / -print > files 2>/dev/null &
$ jobs
<img width="1280" height="800" alt="5b" src="https://github.com/user-attachments/assets/23cf525a-6824-4aa0-b548-fc8a73366e86" />

c.Jadikan program ke 1 sebagai foreground, tekan ^Z dan kembalikan program 
tersebut ke background
$ fg %1
$ bg
<img width="1280" height="800" alt="5c" src="https://github.com/user-attachments/assets/da31f61f-790c-43ff-b903-6b88774b31e9" />

d. Stop program background dengan utilitas kill
$ ps x
$ kill [Nomor PID]
<img width="1280" height="800" alt="5d" src="https://github.com/user-attachments/assets/5791eb33-1d05-4f87-9b18-f928c01b6e01" />

6. History
a. Ganti nilai HISTSIZE dari 1000 menjadi 20
$ HISTSIZE=20
$ h
<img width="1280" height="800" alt="6a" src="https://github.com/user-attachments/assets/2a192417-75e6-4c46-aade-4340d983de49" />

b. Gunakan fasilitas history dengan mengedit instruksi baris ke 5 dari instruksi yang 
terakhir dilakukan
$ !-5
<img width="1280" height="800" alt="6b" src="https://github.com/user-attachments/assets/2ff529f7-380d-4f10-b9bc-202e96696fcd" />

c. Ulangi instruksi yang terakhir. Gunakan juga ^P dan ^N untuk bernavigasi pada 
history bufer
$ !!
<img width="1280" height="800" alt="6" src="https://github.com/user-attachments/assets/ef072c3c-2738-4ef9-bf87-1db1a2d5a6f1" />

d. Ulangi instruksi pada history bufer nomor 150
$ !150
<img width="1280" height="800" alt="6d" src="https://github.com/user-attachments/assets/5710d75e-ef50-407a-bc84-667c33a8e41b" />

e. Ulangi instruksi dengan prefix “ls”
$ !ls
<img width="1280" height="800" alt="6e" src="https://github.com/user-attachments/assets/68485bd0-394e-47f2-b8e5-14d55f0472cd" />
