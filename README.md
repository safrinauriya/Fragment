# Fragment
Fragment adalah komponen yang memiliki fungsi untuk menampilkan antarmuka ke
pengguna melalui activity dengan memiliki layout xml sendiri, Fragment digunakan agar
komponen tampillan aplikasi menjadi fleksibel dan dapat digunakan kembali ( reusable). Fragment memiliki  fungsi yang hampir sama seperti activity tetapi memiliki “lifecycle” yang berbeda. Fragment merupakan bagian dari sebuah activity yang mana sebuah fragment tidak akan ada bila tidak ada sebuah activity karena fragment membutuhkan akses dari activity untuk dapat dijalankan.
Fragment juga bisa disebut sub nya activity, satu activity bisa memiliki lebih dari satu fragment.

Kelebihan yang didapatkan bila menggunakan fragment adalah sebagai berikut:
1. Tidak perlu memasukkan nama file fragment ke dalam “AndroidManifest” yang diperlukan oleh activity.
2. 	Fungsi yang berada pada activity dapat langsung digunakan dalam fragment tersebut tanpa harus membuat ulang. Contoh: pada saat back, fragment hanya perlu memanggil fungsi “getactivity

Fragment memiliki banyak method yang dapat di override seperti halnya Activity:
-	onAttach() dipanggil saat sebuah fragment terhubung ke activity.
-	onCreate() diapnggil saat sebuah fragment dibuat (objeknya di memori).
-	onCreateView() dipanggil saat fragment sudah siap membaca sebuah layout.
-	onViewCreated() dipanggil setelah onCreateView() dan memastikan layout yang dibaca fragment adalah non-null. Semua pengaturan view seperti pembacaan findViewById, menambah onClickListener dapat dilakukan di sini.
-	onActivityCreated() dipanggil setelah activity pembaca sudah menyelesaikan onCreate()-nya.
-	onStart() dipanggil setelah fragment siap untuk ditampilkan di layar.
-	onResume() - Dipakai untuk melakukan pembacaan data yang lebih “rumit” seperti lokasi, sensor, dll.
-	onPause() - Tempat melepas data “rumit”. Lakukan commit di sini.
-	onDestroyView() dipanggil saat layout sebuah fragment akan dihapus dari memori, namun fragmentnya masih ada di memori.
-	onDestroy() dipanggil jika fragment sudah tidak dipakai.
-	onDetach() dipanggil saat fragment tidak lagi terhubung ke sebuah activity.

Kebanyakan aplikasi harus mengimplementasikan setidaknya tiga metode ini untuk setiap fragment diantaranya yaitu:
1.	onCreate(): Sistem akan memanggilnya saat membuat fragment. Dalam implementasi, kita harus melakukan inisialisasi komponen penting dari fragment yang ingin dipertahankan saat fragmen dihentikan sementara atau dihentikan, kemudian dilanjutkan.
2.	onCreateView() : Sistem akan memanggilnya saat fragmen menggambar antarmuka penggunanya untuk yang pertama kali. Untuk menggambar UI fragmen, kita harus mengembalikan View dari metode ini yang menjadi root layout fragmen. Hasil yang dikembalikan bisa berupa null jika fragmen tidak menyediakan UI. 
3.	onPause() : Sistem akan memanggil metode ini sebagai indikasi pertama bahwa pengguna sedang meninggalkan fragmen kita (walau itu tidak selalu berarti fragmen sedang dimusnahkan). Di sinilah biasanya kita harus mengikat perubahan yang harus dipertahankan di luar sesi pengguna saat ini (karena pengguna mungkin tidak akan kembali).

Urutan lifecycle seperti pada gambar dibawah ini.
![fragment2](https://user-images.githubusercontent.com/60589670/109185383-88f43a80-77c2-11eb-840c-4bf502f19ef3.png)

# Contoh penerapan fragment

Jika memilih button "menu makanan" maka akan diaihkan pada halaman fragment menu makanan.

![Screenshot_20210225-215913_Fragment](https://user-images.githubusercontent.com/60589670/109184322-75949f80-77c1-11eb-982d-fd2582de28a7.jpg)

Jika memilih button "menu minuman" maka akan diaihkan pada halaman fragment menu minuman.

![Screenshot_20210225-215925_Fragment](https://user-images.githubusercontent.com/60589670/109184338-788f9000-77c1-11eb-8c7f-7d9998a28f7c.jpg)
