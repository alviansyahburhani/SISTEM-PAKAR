1. TAHAPAN PENGUMPULAN DATA
Proses pengumpulan data merupakan langkah awal yang penting dalam mengembangkan penelitian dengan tujuan memperoleh informasi yang relevan dalam membangun sistem pakar. Pada penelitian kami, data yang dipilih terkait dengan penyakit pernapasan manusia. Adapun beberapa alasan kami memilihnya sebagai berikut :
a)	Cakupan data luas dan kaya akan informasi, data berisi atribut penyakit pernapasan seperti asma, bronkitis, bronkiektasis dan lain-lain.
b)	Data yang diperoleh bersumber dari situs yang resmi dan sudah melalui proses validasi oleh komunitas Kaggel sehingga kualitas data dapat dipercaya.
Tahapan proses dalam pengambilan sampel data dilakukan melalui langkah-langkah berikut:
a)	Identifikasi data
Tahap ini merupakan proses analisis data dimana dalam dataset berjumlah 6 atribut yaitu “Gejala”, “Usia”, “Jenis_Kelamin”, “Penyakit”, “Obat” dan “Level” dan jumlah baris data mencapai 500. Pada atribut kolom Gejala merupakan daftar gejala yang diderita oleh pasien. Rata-rata usia pasien berkisar antara 5 - 60 tahun atau bahkan lebih. Adapun atribut penyakit yang sedang diderita oleh pasien berdasarkan pada atribut gejala serta atribut obat untuk merekomendasikan obat pada pasien sesuai dengan penyakit dan gejala yang diderita dan atribut Level dimana menunjukkan tingkat komplikasi penyakit yang diderita pasien.
b)	Pre-processing data
Tahap berikutnya merupakan langkah pembersihan data, dimana langkah awalnya adalah menghapus kolom yang tidak diperlukan karena fokus utamanya untuk mendiagnosis penyakit. Kolom yang dihapus mencakup "Usia", "Jenis_Kelamin", dan "Level" dengan menggunakan df.drop sebagai berikut.
Proses berikutnya setelah melakukan pembersihan kolom maka selanjutnya menghapus baris yang mengandung NaN atau nilai kosong.
 
		Gambar 2. Baris Kolom
Pada gambar diatas diketahui bahwa baris yang berhasil dihapus sebanyak 63, artinya baris yang terindikasi kosong berjumlah 63 baris yang dikosongkan.
Hasil secara keseluruhan data yang diperoleh setelah melakukan proses cleaning dari yang sebelumnya atribut berjumlah 6 dan baris 500 menjadi 118 baris data dan 3 atribut yaitu “Gejala”, “Penyakit” serta “Obat”.

2. SUMBER DATA
Data bersumber dari situs web resmi bernama Kaggle, situs tersebut merupakan sebuah platform digital untuk berbagi dataset yang banyak digunakan sebagai keperluan penelitian, terutama penelitian yang mencakup machine learning.
Data penyakit pernapasan ini dipublikasikan oleh akun @abbotpatcher (American-health-info) dimana dikumpulkan melalui Departemen Kesehatan Masyarakat yang bertujuan untuk mengidentifikasi penyakit pernapasan kronis di seluruh negara bagian New Mexico, Amerika Serikat.

B. FLOWCHART METODE FORWARD CHAINING
Tahapan metode Forward chaining dimulai dengan memproses fakta awal kemudian berakhir mengambil keputusan, Langkah awal dimulai dengan pasien menginput gejala yang disediakan oleh sistem, selanjutnya sistem akan melakukan pengecekan gejala dan memeriksa apakah gejala yang dimasukkan tersedia dalam aturan yang sudah dibuat. Jika tersedia maka aturan akan dieksekusi dan sistem akan mengembalikan hasil penyakit yang ditemukan. Sebaliknya, jka sistem tidak menemukan penyakit berdasarkan gejala yang dimasukkan maka sistem akan menampilkan pesan bahwa penyakit tidak ditemukan dan proses berakhir.
Pada metode Forward chaining akan menggunakan aturan berbasis logika jika IF/THEN dimana jika gejala cocok dengan aturan yang dibuat maka akan dieksekusi (THEN) dan jika tidak maka hasilnya penyakit tidak ditemukan. 

C. FLOWCHART METODE BACKWARD CHAINING

Metode ini adalah kebalikan dari Forward chaining , dimana akan memproses dengan membuat hipotesis awal berupa dugaan penyakit, kemudian dilakukan proses validasi untuk memastikan apakah hipotesis tersebut benar. Langkah pertama dimulai dengan pengguna (pasien) menginput hipotesis penyakit tertentu. Selanjutnya, sistem akan melakukan pengecekan terhadap penyakit yang diinput dan memeriksa apakah gejala yang tersedia mendukung hipotesis tersebut.

Jika gejala mendukung hipotesis, maka sistem akan melakukan validasi lebih lanjut dan menyimpulkan bahwa penyakit tersebut ditemukan. Sebaliknya, jika gejala tidak mendukung hipotesis, maka hipotesis penyakit akan ditolak, dan pengguna dapat memasukkan hipotesis baru. Proses ini terus berulang hingga ditemukan penyakit yang valid atau hingga semua hipotesis ditolak. Setelah hasil akhir diperoleh, sistem akan menampilkan penyakit yang ditemukan atau memberikan informasi bahwa hipotesis tidak dapat divalidasi.

Pada metode Backward chaining, sistem menggunakan pendekatan berbasis aturan dengan logika IF/THEN. Dalam hal ini, sistem bekerja secara terbalik, dimulai dari hipotesis (kesimpulan) menuju fakta (gejala). Jika fakta mendukung kesimpulan, maka aturan akan dieksekusi (THEN), dan jika tidak, hipotesis akan ditolak.
 

A. HASIL DAN PEMBAHASAN DATA
Dalam penelitian ini, kami menganalisis data terkait gejala penyakit pernapasan yang umum terjadi, khususnya asma. Berikut beberapa data yang ditampilkan mencakup gejala, penyakit dan obat.
Tabel 1. Data
No	Gejala	Penyakit	Obat
1	batuk	asma	omalizumab.
2	perasaan sesak di dada	asma	mepolizumab
3	mengi	asma	mepolizumab
4	sesak napas	asma	mepolizumab
5	demam	asma	penghirup
6	dingin	asma	penghirup
7	alergi	asma	penghirup
8	batuk berdahak kuning atau hijau setiap hari	bronkiektasis	antibiotik
9	sesak napas yang semakin parah saat kambuh	bronkiektasis	antibiotik
10	demam	bronkiektasis	antibiotik
11	nyeri dada	bronkiektasis	garam hipertonik
12	suara siulan saat bernafas	bronkiektasis	garam hipertonik
13	mengi	bronkiektasis	garam hipertonik
14	batuk berdarah	bronkiektasis	ventilasi perkusi intrapulmonal
15	batuk	bronkiektasis	ventilasi perkusi intrapulmonal

Dari tabel diatas, gejala yang paling umum pada penyakit asma adalah batuk,mengi sesak napas dan lainnya. Obat yang direkomendasikan bervariasi tergantung pada gejala yang dialami pasien. Misalnya, Omalizumab direkomendasikan untuk pasien yang mengalami batuk, sementara Mepolizumab lebih sering direkomendasikan untuk gejala sesak napas dan mengi.

Analisis ini menunjukkan bahwa pengobatan asma dapat disesuaikan dengan gejala spesifik yang dialami pasien. Hal ini penting untuk meningkatkan efektivitas pengobatan dan mengurangi risiko komplikasi

1.	Daftar Gejala dan Penyakit
Berdasarkan dataset yang telah diolah, hasil yang ditemukan beberapa gejala dan penyakit sebagai berikut:
Tabel 2. Daftar Gejala
Kode	Gejala	Kode	Gejala
G1	sesak napas yang semakin parah
 saat kambuh	G35	nyeri punggung bawah
G2	keruh	G36	mengi
G3	batuk kering terus-menerus	G37	napas
G4	muntah	G38	energi rendah
G5	pusing	G39	pilek
G6	sakit tenggorokan	G40	sesak napas
G7	keringat malam	G41	nyeri dada
G8	detak jantung lebih cepat	G42	merasa lelah atau letih
G9	nyeri dada tajam	G43	dingin
G10	sakit kepala di pagi hari	G44	batuk berdarah
G11	batuk kehijauan	G45	batuk
G12	kehilangan nafsu makan dan
 penurunan berat badan yang tidak disengaja	G46	penurunan berat badan karena
 kehilangan nafsu makan
G13	kesulitan dengan memori dan konsentrasi	G47	batuk kuning
G14	menyedihkan	G48	perasaan sesak di dada
G15	suara siulan saat bernafas	G49	demam
G16	kehilangan selera makan	G50	alergi
G17	pernapasan cepat	G51	lendir
G18	mual	G52	panas dingin
G19	nyeri	G53	goncangan
G20	diare	G54	suasana hati yang tidak biasa
G21	batuk mengi	G55	batuk kering
G22	pingsan	G56	jeda dalam bernapas
G23	batuk berdahak kuning atau hijau setiap hari	G57	lebih lebar dan bulat dari ujung jari
 tangan dan kaki normal
G24	batuk yang berlangsung lebih dari tiga minggu	G58	kantuk di siang hari
G25	kelelahan	G59	mulut kering
G26	nyeri sendi	G60	berkeringat
G27	busung	G61	jantung berdebar-debar
G28	sakit kepala	G62	nyeri otot
G29	demam tinggi	G63	kongesti dada
G30	sering terbangun	G64	hidung tersumbat
G31	pernapasan dangkal	G65	demam ringan
G32	penurunan berat badan	G66	sifat lekas marah
G33	kulit kebiruan	 	 
G34	batuk kronis	 	 

Data yang dikumpulkan mencakup 66 gejala yang dapat muncul pada pasien dengan kondisi pernapasan. Setiap gejala memiliki kode unik untuk memudahkan identifikasi dan analisis lebih lanjut.



Tabel 3. Daftar Penyakit
Kode	Penyakit
P1	apnea tidur
P2	asbes
P3	asma
P4	bronkiektasis
P5	bronkiolitis
P6	bronkitis
P7	bronkitis kronis
P8	hipertensi paru
P9	influensa
P10	penyakit aspergilosis
P11	penyakit mesothelioma
P12	penyakit paru obstruktif kronis
P13	pneumotoraks
P14	radang paru-paru
P15	sindrom kesulitan pernapasan akut
P16	tuberkulosis
P17	virus sinsitium saluran pernapasan

Dalam tabel diatas, kami mengidentifikasi berbagai penyakit yang berhubungan dengan sistem pernapasan. Data yang dikumpulkan mencakup 17 jenis penyakit, masing-masing dengan kode unik untuk memudahkan analisis dan referensi. Diantaranya ada penyakit apnea [P1] tidur yaitu penyakit gangguan tidur, adapun penyakit asma [P3] yang ditandai dengan peradangan saluran pernapasan dan penyakit lainnya.

2.	Tabel Keputusan
Tabel 4. Tabel Keputusan
Gejala/Penyakit	P1	P2	P3	P4	P5	P6	P7	P8	P9	P10	P11	P12	P13	P14	P15	P16	P17
G1	0	0	0	1	0	0	0	0	0	0	0	0	0	0	0	0	0
G2	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G3	0	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G4	0	0	0	0	0	0	0	0	1	0	0	0	0	1	0	0	0
G5	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0	0
G6	0	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0
G7	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	1	0
G8	0	0	0	0	0	0	0	0	0	0	0	0	0	0	1	0	0
G9	0	0	0	0	0	0	0	0	0	0	0	0	1	0	0	0	0
G10	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G11	0	0	0	0	0	0	0	0	0	0	0	0	0	1	0	0	0
G12	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	1	0
G13	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G14	0	0	0	0	0	0	0	0	0	0	0	0	0	0	1	0	0
G15	0	0	0	1	0	1	0	0	0	0	0	0	0	0	0	0	0
G16	0	0	0	0	1	0	0	0	0	0	0	0	0	1	0	0	0
G17	0	0	0	0	0	0	0	0	0	0	0	0	1	1	0	0	0
G18	0	0	0	0	0	0	0	0	1	0	0	0	0	1	0	0	0
G19	0	0	0	0	0	0	0	0	0	0	0	0	0	0	1	0	0
G20	0	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0
G21	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	1
G22	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0	0
G23	0	0	0	1	0	0	0	0	0	0	0	0	0	0	0	0	0
G24	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	1	0
G25	0	0	0	0	0	0	0	1	1	1	0	1	1	1	0	0	0
G26	0	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0
G27	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0	0
G28	0	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0
G29	0	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0
G30	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G31	0	0	0	0	0	0	0	0	0	0	0	0	0	1	0	0	0
G32	0	0	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0
G33	0	0	0	0	0	0	0	0	0	0	0	0	1	0	0	0	0
G34	0	0	0	0	0	0	0	0	0	0	0	1	0	0	0	0	0
G35	0	0	0	0	0	0	0	0	0	0	1	0	0	0	0	0	0
G36	0	0	1	1	0	1	1	0	0	1	0	1	0	0	0	0	0
G37	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0	0
G38	0	0	0	0	0	0	0	0	0	0	0	0	1	1	0	0	0
G39	0	0	0	0	1	1	0	0	1	0	0	0	0	0	0	0	0
G40	0	1	1	0	0	0	1	0	0	1	1	1	1	1	1	0	0
G41	0	0	0	1	0	0	1	1	0	0	1	0	0	1	0	0	0
G42	0	0	0	0	0	1	0	0	0	0	0	0	0	0	0	0	0
G43	0	0	1	0	1	0	0	0	0	0	0	1	1	1	0	0	1
G44	0	0	0	1	0	0	0	0	0	0	0	0	0	1	0	0	0
G45	0	0	1	1	1	0	0	0	1	0	0	0	0	0	1	0	0
G46	0	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G47	0	0	0	0	0	1	0	0	0	0	0	0	0	1	0	0	0
G48	0	0	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G49	0	0	1	1	1	0	0	0	0	0	0	0	1	1	0	1	0
G50	0	0	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G51	0	0	0	0	0	0	1	0	0	0	0	1	0	0	0	0	0
G52	0	0	0	0	0	0	0	0	1	0	0	0	0	0	0	1	0
G53	0	0	0	0	0	0	0	0	0	0	0	0	0	1	0	0	0
G54	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G55	0	0	0	0	0	0	0	0	0	0	1	0	1	0	0	0	0
G56	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G57	0	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G58	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G59	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
G60	0	0	0	0	0	0	0	0	0	0	0	0	0	1	0	0	0
G61	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0	0
G62	0	0	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0
G63	0	0	0	0	0	1	0	0	0	0	0	0	0	0	0	0	0
G64	0	0	0	0	1	1	0	0	1	0	0	0	0	0	0	0	0
G65	0	0	0	0	0	1	0	0	0	0	0	0	0	0	0	0	0
G66	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0

Tabel keputusan diatas dibuat untuk menganalisis hubungan antara gejala yang dialami pasien dengan berbagai penyakit pernapasan serta aturan  (rule) yang akan diterapkan pada sistem pakar, Setiap sel dalam baris dan kolom menunjukkan apakah gejala tertentu terkait dengan penyakit tertentu, dengan blok kode berwarna biru  menunjukkan adanya hubungan dan sebaliknya  menunjukkan tidak ada hubungan.

3.	Aturan Sistem (rule)
Tabel 5. Aturan
Rule	IF	THEN
1	keruh, kantuk di siang hari, jeda dalam bernapas,
 kesulitan dengan memori dan konsentrasi,
 suasana hati yang tidak biasa, sifat lekas marah,
 sering terbangun, sakit kepala di pagi hari, mulut kering	apnea tidur
2	sesak napas, batuk kering terus-menerus, penurunan berat
 badan karena kehilangan nafsu makan, lebih lebar dan
 bulat dari ujung jari tangan dan kaki normal	asbes
3	batuk, perasaan sesak di dada, mengi, sesak napas, demam, dingin, alergi	asma
4	batuk berdahak kuning atau hijau setiap hari, sesak napas yang semakin
 parah saat kambuh, demam, nyeri dada, suara siulan saat bernafas, mengi,
 batuk berdarah, batuk	bronkiektasis
5	dingin, pilek, demam, hidung tersumbat, kehilangan selera makan, batuk	bronkiolitis
6	pilek, hidung tersumbat, demam ringan, kongesti dada, mengi,
 suara siulan saat bernafas, batuk kuning, merasa lelah atau letih	bronkitis
7	lendir, mengi, nyeri dada, sesak napas	bronkitis kronis
8	napas, kelelahan, nyeri dada, pusing, pingsan, jantung berdebar-debar, busung	hipertensi paru
9	demam tinggi, sakit kepala, nyeri otot, nyeri sendi, batuk, panas dingin,
 sakit tenggorokan, hidung tersumbat, pilek, kelelahan, mual, muntah, diare	influensa
10	mengi, sesak napas, kelelahan, penurunan berat badan	penyakit aspergilosis
11	sesak napas, nyeri dada, nyeri punggung bawah, batuk kering	penyakit mesothelioma
12	batuk kronis, sesak napas, kelelahan, lendir, mengi, dingin	penyakit paru obstruktif kronis
13	nyeri dada tajam, sesak napas, kulit kebiruan, kelelahan, pernapasan cepat,
  batuk kering, demam, dingin, energi rendah	pneumotoraks
14	batuk kehijauan, batuk kuning, batuk berdarah, demam, berkeringat, goncangan,
 sesak napas, pernapasan cepat, pernapasan dangkal, nyeri dada, energi rendah,
 kehilangan selera makan, kelelahan, mual, muntah, dingin	radang paru-paru
15	sesak napas, menyedihkan, detak jantung lebih cepat, nyeri, batuk	sindrom kesulitan pernapasan akut
16	batuk yang berlangsung lebih dari tiga minggu, kehilangan nafsu makan
 dan penurunan berat badan yang tidak disengaja, demam, panas dingin, keringat malam	tuberkulosis
17	batuk mengi, dingin	virus sinsitium saluran pernapasan


Berdasarkan tabel keputusan sebelumnya, maka dibentuk serangkaian aturan (rule) berbasis gejala yang dapat digunakan untuk mengidentifikasi berbagai kondisi pernapasan. Setiap aturan terdiri dari kondisi gejala yang harus ada (IF) dan diagnosis penyakit yang dihasilkan (THEN). Dalam pengimplementasian metode forward chaining dan backward chaining, maka aturan diatas yang akan digunakan untuk memperoleh hasil diagnosa. Dimana gejala yang dimasukkan pengguna harus cocok dari salah satu rule diatas untuk mendapatkan hasil diagnosis yang memadai.

B. HASIL IMPLEMENTASI METODE FORWARD CHAINING
Metode forward chaining bekerja dengan mencocokkan semua gejala yang diberikan oleh pengguna dengan aturan-aturan yang telah ditentukan sebelumnya dalam basis aturan (rule base). Langkah pertama yang dilakukan adalah memuat dataset berikut.
 
Gambar 5. Load Dataset
Dataset yang dimuat berasal dari file berformat excel dimana variabel rule_file merupakan tempat untuk membaca file excel yang berisi aturan-aturan yang telah didefinisikan sebelumnya. Kemudian variabel inisialisasi pattern_file adalah dataset mentah untuk mencocokkan data pada gejala pengguna  untuk tujuan dimana kasus forward chaining can backward tidak dapat diselesaikan.

 
Gambar 6. Mengambil daftar gejala
Hal selanjutnya adalah mengambil daftar unik penyakit dan gejala dari dataset yang disimpan dalam variabel `rule_data`. Dengan menggunakan fungsi .unique() untuk mendapatkan daftar penyakit yang unik dari kolom 'Penyakit' pada rule_data. Ini berguna untuk mencegah duplikasi dan memungkinkan analisis yang lebih baik. Berikutnya menggabungkan semua gejala yang ada dalam kolom 'Gejala', menghapus nilai yang hilang dengan .dropna(), dan kemudian memisahkan gejala berdasarkan koma. Setelah itu, kami  menggunakan set() untuk memastikan semua gejala yang diambil adalah unik. 
 
Gambar 7. Memilih Metode
Sebelum memilih gejala, pengguna diarahkan untuk memilih metode yang akan digunakan. Angka 1 berarti metode forward chaining yang akan dieksekusi, sebaliknya jika memilih opsi 2 maka backward chaining yang akan dieksekusi.
 
Gambar 8. Input Gejala
Gambar diatas bertujuan untuk mengambil inputan pengguna dan menampilkan daftar gejala terlebih dahulu, kemudian akan dimasukkan kedalam sistem untuk dianalisis. Inputan pengguna berupa angka yang dimulai dari 1 sampai gejala terakhir dan dipisahkan dengan tanda koma.
 
Gambar 9. Proses Forward Chaining
Proses selanjutnya merupakan implementasi forward chaining yang menarik kesimpulan berdasarkan gejala yang dimasukkan pengguna. Proses ini dimulai dengan mengacu pada aturan-aturan yang telah ditetapkan dalam dataset, yang berisi informasi mengenai penyakit, gejala, dan rekomendasi obat. Langkah pertama dalam proses ini adalah pemecahan gejala, di mana setiap aturan memiliki daftar gejala yang dipisahkan oleh tanda koma. Gejala-gejala tersebut dipecah menjadi elemen-elemen individu menggunakan fungsi tertentu, sehingga dapat dibandingkan dengan gejala yang telah dipilih oleh pengguna. Selanjutnya, pencocokan gejala dilakukan dengan menggunakan fungsi yang memverifikasi apakah semua gejala dalam aturan tertentu tercakup dalam gejala yang dipilih. Jika semua gejala terpenuhi, aturan tersebut dianggap valid, dan proses diagnosa dapat dilanjutkan.
 
Gambar 10. Hasil Diagnosa Forward Chaining
Hasil yang diperoleh oleh sistem mendiagnosa bahwa Pengguna menderita penyaki virus sinsitium pada saluran pernapasan dan secara otomatis sistem merekomendasikan obat Cairan Intravena. Hal ini relevan karena pengguna memasukkan gejala Batuk mengi dan Dingin dimana gejala tersebut berkaitan dengan aturan yang telah ditetapkan. Jika kasus dimana gejala tidak ditemukan dalam aturan maka akan beralih ke langkah alternatif yaitu pattern matching. Dengan demikian, implementasi forward chaining ini menjadi metode yang sederhana namun efektif dalam menentukan diagnosa berdasarkan kecocokan gejala, terutama pada dataset yang memiliki aturan deterministik, di mana semua gejala yang relevan harus terpenuhi untuk menghasilkan diagnosa yang akurat.

C. HASIL IMPLEMENTASI METODE BACKWARD CHAINING
Tahap berikutnya adalah mengimplementasikan backward chaining dimulai dari pemilihan hipotesis (penyakit), penelusuran data pendukung (gejala), hingga verifikasi kesesuaian gejala dengan aturan.
 
Gambar 11. Menampilkan dan memilih Penyakit
Pengguna diminta untuk memilih penyakit yang ingin diperiksa dengan memasukkan nomor gejala yang sesuai. Input ini kemudian digunakan untuk menentukan penyakit yang dipilih (selected_disease) berdasarkan indeks yang diberikan.
 
Gambar 12. Tampilan Gejala pada penyakit yang relevan
Setelah pengguna memilih penyakit, sistem akan melakukan pencarian terhadap data gejala yang berkaitan dengan penyakit tersebut dalam dataset aturan. Apabila penyakit yang terdapat dalam dataset sesuai dengan pilihan pengguna, maka daftar gejala (rule_symptoms) yang terkait dengan penyakit tersebut akan ditampilkan kepada pengguna. Pengguna akan memilih gejala yang mereka alami dari daftar gejala yang ditampilkan. Input ini berupa nomor gejala yang dipisahkan oleh koma. Nomor-nomor tersebut dikonversi menjadi indeks, lalu digunakan untuk mengambil gejala terkait dari daftar rule_symptoms.
 
Gambar 13. Verifikasi Gejala
Proses verifikasi gejala dan penentuan diagnosa merupakan langkah terakhir dalam backward chaining. Proses pemeriksaan untuk memastikan apakah seluruh gejala yang tercantum dalam aturan untuk penyakit yang dipilih (rule_symptoms) telah terpenuhi oleh gejala yang dimasukkan oleh pengguna (selected_symptoms). Jika semua gejala tersebut sesuai, maka diagnosa penyakit akan dianggap terkonfirmasi, dan sistem akan menampilkan rekomendasi obat yang relevan untuk pengobatan.
 
Gambar 14. Hasil Diagnosa
Hasil terakhir yang diperoleh menunjukkan bahwa gejala yang diderita pengguna terkonfirmasi dan direkomendasikan ke dokter untuk konsultasi lebih lanjut. Sebaliknya, jika tidak semua gejala terpenuhi, maka sistem akan memberikan informasi bahwa gejala yang dilaporkan tidak cocok dengan penyakit yang dimaksud, sehingga proses verifikasi dihentikan. 

Pada implementasi metode forward chaining dan backward chaining, terdapat perbedaan utama dalam proses analisis gejala dan pendekatan terhadap aturan diagnosis. Forward chaining bekerja dengan memeriksa seluruh aturan dalam dataset berdasarkan gejala yang diberikan oleh pengguna, sementara backward chaining memulai dengan hipotesis penyakit yang dipilih pengguna, lalu memverifikasi gejala yang relevan. Proses forward chaining cenderung lebih luas karena mencakup semua kemungkinan aturan, sedangkan backward chaining lebih terarah pada penyakit tertentu. Meskipun keduanya memiliki cara kerja yang berbeda, hasil diagnosis tetap bergantung pada keakuratan data gejala yang diinputkan.

D. SOLUSI ALTERNATIF PATTERN MATCHING DENGAN COSINE SIMILARITY
Metode pencocokan pola dengan pendekatan Cosine Similarity digunakan sebagai alternatif ketika metode forward chaining dan backward chaining tidak menghasilkan diagnosis yang memuaskan. Proses ini dilakukan dengan membandingkan gejala yang dimasukkan oleh pengguna dengan dataset berdasarkan tingkat kesamaan teks.
 
Gambar 15. Pattern Matching
Pada tahap awal, sistem memeriksa apakah metode utama (forward chaining atau backward chaining) telah berhasil memberikan hasil diagnosa. Jika tidak ditemukan diagnosa, sistem akan memberi pemberitahuan kepada pengguna bahwa proses akan dilanjutkan menggunakan pattern matching. Kemudian menggabungkan gejala yang diinput menjadi string tunggal dipisahkan oleh koma. 
 
Gambar 16. Cosine Similarity
Tahap berikutnya, CountVectorizer digunakan untuk mengubah gejala yang dimasukkan oleh pengguna dan dataset menjadi representasi vektor. Setelah itu, cosine similarity dihitung untuk menilai tingkat kesamaan antara gejala pengguna dan data yang terdapat dalam dataset. Nilai kesamaan ini mencerminkan seberapa relevan gejala pengguna dengan setiap penyakit yang ada dalam dataset.

 
Gambar 17. Penentuan Penyakit
Tahap terakhir, sistem akan mengidentifikasi penyakit berdasarkan nilai kesamaan tertinggi. Apabila nilai kesamaan melebihi ambang batas (threshold) sebesar 0,5, maka penyakit yang paling relevan dengan gejala yang diinputkan oleh pengguna akan ditampilkan, beserta rekomendasi obat yang sesuai. Namun, jika nilai kesamaan tersebut terlalu rendah, sistem akan memberikan pernyataan bahwa gejala yang dialami pengguna terlalu umum atau tidak dapat didiagnosis dengan data yang ada.
 
Gambar 18. Hasil Pattern Matching
Hasil akhir menunjukkan bahwa berdasarkan analisis kesamaan, pengguna kemungkinan menderita tuberkulosis, dan obat yang direkomendasikan adalah rifampin. Pengguna juga disarankan untuk melakukan konsultasi lebih lanjut dengan tenaga medis untuk mendapatkan penanganan yang tepat.

Dengan memanfaatkan cosine similarity, metode pencocokan pola ini dapat memberikan diagnosis meskipun gejala yang dimasukkan tidak sepenuhnya sesuai dengan aturan yang telah ditetapkan sebelumnya. Pendekatan ini memberikan tingkat fleksibilitas yang lebih tinggi dalam sistem pakar, terutama dalam menangani kasus di mana gejala pengguna sulit untuk dicocokkan menggunakan metode berbasis aturan.
