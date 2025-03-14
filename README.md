# Modul 5: Java Profiling
## JMeter Report and Test Results
### **Endpoint** `/all-student`
JMeter
Before Optimization Test Result JMeter
<img src="src/images/testresults1.jpg" alt="all-student">
After Optimization Test Result JMeter
<img src="src/images/testresults1optimize.jpg" alt="all-student">
Before Optimization JMeter:
<img src="src/images/jmeter_allstudent.jpg" alt="all-student"/>
After Optimization JMeter:
<img src="src/images/jmeter_allstudent_after.jpg" alt="all-student"/>

Execution Time `getAllStudentWithCourses()` from Intellij Profiler:

| Before | After  | Diff Percentage |
| -- |--------|-----------------|
| 4526 ms | 680 ms | 85%             |

### **Endpoint** `/all-student-name`
JMeter
Before Optimization Test Result JMeter
<img src="src/images/testresults2.jpg" alt="all-student-name">
After Optimization Test Result JMeter
<img src="src/images/testresults2optimize.jpg" alt="all-student-name">
Before Optimization JMeter:
<img src="src/images/jmeter_allstudentname.jpg" alt="all-student-name"/>
After Optimization JMeter:
<img src="src/images/jmeter_allstudentsname_after.jpg" alt="all-student-name"/>

Execution Time `joinStudentNames()` from Intellij Profiler:

| Before | After  | Diff Percentage |
|--------|--------|-----------------|
| 493 ms | 140 ms | 71,6%           |

### **Endpoint** `/highest-gpa`
JMeter
Before Optimization Test Result JMeter
<img src="src/images/testresults3.jpg" alt="highest-gpa">
After Optimization Test Result JMeter
<img src="src/images/testresults3optimize.jpg" alt="highest-gpa">
Before Optimization JMeter:
<img src="src/images/jmeter_highestgpa.jpg" alt="highest-gpa"/>
After Optimization JMeter:
<img src="src/images/after_jmeter_gpa" alt="highest-gpa/>

Execution Time `findStudentWithHighestGpa()` from Intellij Profiler:

| Before | After | Diff Percentage |
|--------|-------|-----------------|
| 130 ms | 30 ms | 76,9%           |

## Reflection
### What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?
- JMeter digunakan untuk menguji kinerja aplikasi dengan mensimulasikan skenario penggunaan oleh banyak pengguna sekaligus. Tujuan utama pengujian ini adalah untuk melihat bagaimana aplikasi menangani beban kerja yang tinggi, seperti dalam kondisi penggunaan nyata, untuk memastikan kestabilan dan responsivitas sistem saat menerima banyak permintaan secara bersamaan.
- IntelliJ Profiler, di sisi lain, bertujuan untuk menganalisis perilaku runtime aplikasi guna mengidentifikasi penyebab utama perlambatan atau bottleneck dalam sistem. Profiling ini membantu menemukan masalah seperti penggunaan CPU yang tidak efisien, kebocoran memori, atau proses yang memperlambat kinerja aplikasi.
  Singkatnya, JMeter difokuskan pada pengujian ketahanan aplikasi dalam kondisi beban tinggi, sedangkan IntelliJ Profiler lebih pada analisis untuk mengoptimalkan performa internal aplikasi.
### How does the profiling process help you in identifying and understanding the weak points in your application?
- Proses profiling sangat bermanfaat dalam mengidentifikasi bottleneck dan masalah memori yang dapat menyebabkan performa aplikasi menurun. Selama proses ini, profiler akan mengumpulkan serta menganalisis data untuk menemukan bagian-bagian yang perlu dioptimalkan. Informasi yang diperoleh mencakup penggunaan CPU, alokasi memori, aktivitas garbage collection, dan konkurensi thread, sehingga kita dapat meningkatkan efisiensi serta kinerja aplikasi secara keseluruhan.
### Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?
- Menurut saya, IntelliJ Profiler sudah sangat efektif dalam mengidentifikasi bottleneck dalam aplikasi. Dengan adanya flame graph, kita dapat dengan mudah melihat bagian mana yang memerlukan waktu eksekusi paling lama. Selain itu, tab Method List memberikan informasi mengenai execution time dari setiap metode yang dijalankan. Jika kita melakukan optimasi pada suatu metode, kita dapat langsung melihat perubahan diff execution time tanpa perlu menghitung peningkatan performa secara manual. Dengan cara ini, saya dapat mengetahui bagian aplikasi yang perlu dioptimalkan, seperti getAllStudentCourses, joinStudentName, dan findStudentWithHighestGPA, lalu meningkatkan efisiensinya berdasarkan data yang diperoleh.
### What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?
- Memahami Hasil Profiling: Membaca dan menganalisis laporan hasil profiling bukanlah hal yang mudah. Saya harus memperhatikan setiap detail untuk mengidentifikasi bagian aplikasi yang menjadi bottleneck agar dapat melakukan optimasi dengan tepat.
- Melakukan Optimisasi: Setelah menemukan bottleneck, tantangan berikutnya adalah melakukan refactoring pada bagian tersebut untuk meningkatkan performa aplikasi. Proses ini cukup kompleks karena memerlukan pemahaman mendalam terhadap kode serta dampak dari perubahan yang dilakukan.
Keseluruhan proses ini menuntut ketelitian dan analisis yang mendalam untuk memastikan bahwa optimasi yang dilakukan benar-benar efektif dalam meningkatkan performa aplikasi.
### What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?
- Selain efektivitas yang telah saya sebutkan sebelumnya, saya tidak perlu menggunakan third-party apps tambahan untuk melakukan profiling, karena IntelliJ Profiler sudah tersedia langsung di dalam IntelliJ IDEA. Hal ini membuat proses profiling menjadi lebih praktis tanpa perlu melakukan setup yang rumit. Karena profiler ini sudah terintegrasi dengan IDE, saya dapat dengan mudah melakukan debugging, profiling, dan modifikasi kode dalam satu tempat, sehingga proses optimasi menjadi lebih efisien dan terorganisir
### How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?
- Saya belum mengalami hasil yang tidak konsisten dari kedua alat tersebut. Namun, jika hal tersebut terjadi, saya akan terlebih dahulu memeriksa kembali konfigurasi pada JMeter dan meninjau ulang hasil profiling dari IntelliJ Profiler untuk memastikan tidak ada kesalahan dalam pengaturan atau interpretasi data. Jika ketidaksesuaian masih terjadi, saya akan mencari penyebabnya dengan mencari referensi melalui search engine atau berdiskusi dengan teman. Selain itu, saya juga akan memastikan bahwa skenario pengujian serta beban kerja yang digunakan benar-benar mencerminkan kondisi dunia nyata, sehingga hasil yang diperoleh dapat lebih akurat dan valid untuk proses optimasi lebih lanjut. 
### What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?
- Pertama, saya mengurangi jumlah pemanggilan database pada metode getAllStudentsWithCourses(). Sebelumnya, setiap mahasiswa yang diambil harus melakukan pemanggilan tambahan ke database untuk mendapatkan daftar mata kuliah yang diikuti, yang mengakibatkan banyak query terpisah dan memperlambat proses. Untuk mengatasi hal ini, saya mengubah pendekatan dengan menggunakan studentCourseRepository.findAll() agar semua data hubungan antara mahasiswa dan mata kuliah dapat diambil dalam satu pemanggilan. Selanjutnya, saya memanfaatkan HashMap untuk menyimpan ID mahasiswa, sehingga iterasi hanya dilakukan satu kali pada StudentCourse untuk mencocokkan mahasiswa dengan data yang sesuai.
- Selain itu, saya juga mengoptimalkan struktur data untuk mengurangi alokasi memori yang tidak perlu pada metode joinStudentNames(). Sebelumnya, saya menggunakan operasi += untuk menggabungkan nama mahasiswa, yang kurang efisien karena String bersifat immutable, sehingga setiap kali dilakukan konkatensi, akan tercipta objek baru yang membebani alokasi memori. Untuk meningkatkan efisiensi, saya mengganti pendekatan ini dengan StringBuilder, yang lebih hemat memori dan lebih cepat dalam melakukan manipulasi string.
- Strategi berikutnya adalah mengoptimalkan eksekusi query dalam metode findStudentWithHighestGpa(). Awalnya, metode ini mendapatkan mahasiswa dengan IPK tertinggi dengan melakukan iterasi pada seluruh data mahasiswa dan membandingkan IPK satu per satu, yang tidak efisien terutama untuk dataset yang besar. Sebagai solusi, saya menggunakan pendekatan langsung dengan eksekusi query melalui StudentRepository: SELECT * FROM students ORDER BY gpa DESC LIMIT 1; Dengan metode ini, database dapat melakukan sorting dan filtering secara langsung, sehingga hanya mengembalikan satu mahasiswa dengan IPK tertinggi tanpa perlu iterasi manual dalam kode.