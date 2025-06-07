ID: 20924305
Name: Gia Muhammad Agusta

### 1. Mind Map and Concept Map
### Judul: Implementasi Estimasi Debit Air Sungai berbasis *AI* pada sistem *Edge-Computing*
### Title: Implementation of River Water Debt Estimation AI based on Edge-Computing system
## Mindmap

```mermaid
mindmap
  root((Water Debt<br />Estimation))
    Problem
      Production Cost
      Automation.<br />Data and Operator Intervention
      Production Mass Complexity
      Damage Probability
      Computational Cost
    GAP
      Not all previous<br />study measure Water Debt
      Not implemented on Edge-Computing
      Lack of Accuracy<br />due to illuminance or<br />others condition 
    Measurement
      Water Flow Velocity
        AI-Based
          Recurrent All Pairs Field Transformer
          RivVideoFlow
        Non-AI
          Propeler or Hardware Based
          Optical Flow<br />Algorithm
      Water Depth
        Sonar Based
        Depth Sensor
          Stereo Vision
          Structured Light
      Cross Sectional Area
        Normal Distribution<br />Assumption
        Manual Measurement
      Water Debt
        Integrating<br />all measurement
    Existing Method
      Intrusive
        Vertical Stilling Wells
        Acoustic Doppler Velocimeters
      Non-Intrusive
        Remote Sensing
        High Frequence Doppler
        Edge-Computing
```

### ConceptMap
```mermaid
flowchart TD
    XXX[Hydrology Water Management] ==> A
    A[Water Debt<br />Estimation] --> | Calculate | B(Measurement)
    B --> | Water Flow/Speed | C(Meter<br />per<br />second) --> | Integration | D(Debt<br />m^3/s)
    B --> | Water Depth | E(Meter) --> | Integration | D(Debt<br />m^3/s)
    B --> | Cross Sectional Area | G(Meter) --> | Integration | D(Debt<br />m^3/s)

    A[Water Debt<br />Estimation] --> | Design | I[System]
    I --> | Architecture | J[System<br />and<br />Instrument]
    J --> | use edge-computing | K(Raspberry Pi-4)
    K --> | to run existing model of | L(RAFT)
    L --> | to get prediction of | P(Water Flow)
    K --> | use | M(RGB Sensor)
    M --> | to get | O(Real Time<br />Image)
    K --> | to run | N(Perspective<br />Projection)
    N --> | to get | R(Normalized Image)
    J --> | use sensor | Q(ASUS Xtion<br />Camera Sensor)
    Q --> | use method | S(Structured Light)
    S --> | to get | T(Depth)
    I --> | Integration | U[Custom Integration<br />Formula]
    U --> | to get | V(Water Debt)
    A[Water Debt<br />Estimation] --> | Evaluate | W(System<br />and<br />Measurement)
    W --> | comparing | X(Accuracy)
    W --> | calculate cost of | Y(Computation)
    W --> | calculate cost of | Z(Infrastructure)
```

### 2. Data Science and Python Env
### a. Explain in brief about data science
Answer
Data Science adalah bidang interdisipliner yang menggunakan metode ilmiah, proses, algoritma, dan sistem untuk mengekstrak pengetahuan serta wawasan dari data terstruktur maupun tidak terstruktur. Bidang ini menggabungkan teknik dari statistika, ilmu komputer, pembelajaran mesin (machine learning), dan keahlian domain untuk menganalisis, menginterpretasi, dan memvisualisasikan data kompleks guna mendukung pengambilan keputusan. 
Dhar, V. (2013). "Data Science and Prediction." Communications of the ACM, 56(12), 64-73.

### b. What are the differences between data, data science, and data scientist?
Answer
Data:
Data adalah fakta mentah, angka, teks, gambar, atau sinyal yang belum diolah. Data merupakan elemen fundamental dalam seluruh proses analisis. Data berupa fakta mentah, angka, teks, gambar, atau bahkan rekaman suara yang belum memiliki makna spesifik. Contohnya transaksi harian toko, hasil kuesioner, log aktivitas pengguna aplikasi, atau data sensor dari perangkat IoT. Data bisa terstruktur (seperti tabel database) atau tidak terstruktur (seperti postingan media sosial). Tanpa data, tidak dapat dianalisis, analoginya data seperti bahan baku yang harus diolah lebih lanjut untuk menghasilkan nilai atau insight.

Data Science:
Data science adalah disiplin ilmu yang menggabungkan metode statistika, pemrograman komputer, dan pengetahuan domain untuk mengekstrak pola, prediksi, atau insight dari data. Prosesnya meliputi pengumpulan data, pembersihan (cleaning), eksplorasi (EDA), pemodelan (machine learning), visualisasi hasil hingga intepretasi menjadi pengetahuan baru. Contoh penerapannya sangat luas, mulai dari sistem rekomendasi (seperti pada algoritma aplikasi TV, e-Commerce, musik dan lainnya), deteksi fraud kartu kredit, hingga prediksi tren pasar saham. Data science tidak hanya berfokus pada teknis analisis, tetapi juga pada cara menyampaikan temuan secara efektif kepada stake-holder.

Data Scientist:
Data scientist adalah individu yang memiliki keahlian untuk menjalankan seluruh rangkaian proses data science. Tugasnya mencakup merancang algoritma, membangun model prediktif, hingga menerjemahkan hasil analisis menjadi rekomendasi bisnis yang actionable. Seorang data scientist harus menguasai keterampilan teknis (seperti Python/R, SQL, dan machine learning) sekaligus kemampuan komunikasi untuk menjelaskan temuan kompleks dengan bahasa sederhana. Misalnya, mereka mungkin mengembangkan model untuk memprediksi churn pelanggan atau mengoptimalkan rantai pasok berdasarkan data historis. Peran ini sering disebut sebagai "pekerjaan terseksi abad ke-21" karena permintaannya yang tinggi di berbagai industri khususnya pada industri yang sudah berjalan hingga sudah menghasilkan data.

### c. Explain about the four foundational aspects of data science?
Answer
4 Fondasi dari aspek Data Science diantaranya adalah Matematika, Teknologi, Pengetahuan Domain dan Komunikasi Visual Data
- Matematika:
  Fondasi matematika yang terdiri dari kalkulus, aljabar linier, statistika dan probabilitas. Kalkulus dan aljabar linier memberikan pemahaman dari mekanisme atau metode-metode Machine Learning (dahulu lebih dikenal statistik inferensial untuk jenis parametrik), Kalkulus dan Aljabar linier di Machine Learning umumnya digunakan untuk mencari garis pemisah (khususnya pada kategori klasifikasi) konvergensi dari masalah pengenalan pola, digunakan untuk mencari global optimum dan tidak terjebak dalam lokal optimum. Sedangkan Statistik dan probabilitas membentuk tulang punggung analitis yang memberikan kerangka kerja untuk memahami pola dan ketidakpastian dalam data. Pada beberapa metode machine learning tertentu menggunakan statistika dan probabilitas (contoh: Naive Bayes). Tanpa pemahaman mendalam tentang distribusi data, uji hipotesis, dan regresi, seluruh proses analisis akan kehilangan dasar ilmiahnya. Para praktisi data science harus mampu membedakan antara korelasi dan kausalitas, serta memahami prinsip sampling yang tepat.

- Teknologi:
  Ilmu komputer dan pemrograman berperan sebagai alat utama untuk mengimplementasikan teori statistika menjadi solusi nyata. Kemampuan mengolah dataset besar membutuhkan penguasaan bahasa pemrograman seperti Python atau R, serta framework seperti Pandas dan NumPy. Aspek ini juga mencakup pemahaman tentang struktur data, algoritma, dan optimasi kode untuk menangani big data secara efisien. Tantangan komputasi seperti parallel processing dan manajemen memori menjadi bagian krusial dalam fondasi ini khususnya pada metode Machine Learning yang mutakhir seperti Deep Learning atau pada jumlah Data yang sangat besar.

- Pengetahuan Domain:
  Pengetahuan domain atau bisnis berfungsi sebagai kompas yang mengarahkan analisis ke masalah yang benar-benar relevan. Seorang data scientist di bidang kesehatan harus memahami terminologi medis, sementara yang bekerja di fintech perlu mengerti regulasi keuangan. Tanpa pemahaman domain yang mendalam, analisis yang canggih sekalipun bisa menghasilkan insight yang tidak aplikatif atau bahkan menyesatkan.

- Komunikasi Visual Data:
  Komunikasi dan visualisasi data menjadi jembatan antara hasil analisis teknis dengan pengambilan keputusan. Fondasi ini meliputi seni menyajikan temuan kompleks dalam bentuk dashboard, grafik interaktif, atau laporan eksekutif yang mudah dipahami. Kemampuan bercerita dengan data (data storytelling) menjadi pembeda antara analis biasa dengan praktisi kelas dunia, karena nilai sebenarnya dari data science terletak pada kemampuannya memengaruhi keputusan bisnis.

### d. List link on PyPI for installing JupyterNotebook, Matplotlib, NumPy.
- Link untuk matplotlib: https://pypi.org/project/matplotlib/
- Link untuk jupyter notebook: https://pypi.org/project/notebook/
- Link untuk Numpy: https://pypi.org/project/numpy/

### e. Create a virtual environment, install some packages, and save information to requirements.txt, create other virtual environment and use requirement.txt. Show the screenshots for all processes.

- Create a virtual environment

<img width="576" alt="Screenshot 2025-05-09 at 17 06 58" src="https://github.com/user-attachments/assets/840a06fb-27b9-4e39-8428-c63491525596" />

- Install some packages:

<img width="587" alt="Screenshot 2025-05-09 at 17 06 20" src="https://github.com/user-attachments/assets/e4cdeb44-7f5e-4ace-be78-5f8203d0a9a1" />

<img width="591" alt="Screenshot 2025-05-09 at 17 06 37" src="https://github.com/user-attachments/assets/cf3ed48c-3431-4b22-9e6d-b316637a4d1b" />

<img width="572" alt="Screenshot 2025-05-09 at 17 05 49" src="https://github.com/user-attachments/assets/6302049d-dec0-450f-aa6c-4d4938a2b835" />

- Save information to requirements.txt

<img width="646" alt="Screenshot 2025-05-09 at 17 05 03" src="https://github.com/user-attachments/assets/a5364727-27ee-488d-b863-95f6fe64b57e" />

- create other virtual environment
 
<img width="584" alt="Screenshot 2025-05-09 at 17 04 50" src="https://github.com/user-attachments/assets/09097df3-fe0d-4ba4-94d8-9bb2f21eb58a" />

- use requirement.txt to install list of packages

<img width="685" alt="Screenshot 2025-05-09 at 17 04 35" src="https://github.com/user-attachments/assets/8782a3a8-7251-4742-bf24-5a0e7f33bde9" />

### 3. Practicing Python for ML

