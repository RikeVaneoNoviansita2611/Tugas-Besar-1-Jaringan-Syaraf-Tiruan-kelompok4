## 9. Pembahasan & Analisis Komparatif

Berdasarkan hasil eksperimen pada data Telco Customer Churn, diperoleh beberapa poin analisis utama:

- Separabilitas Linier Data: Data tidak bersifat linearly separable (dapat dipisahkan secara linier). Hal ini dibuktikan oleh kurva Perceptron yang tidak pernah menyentuh nilai 0 misclassification error hingga epoch ke-50, serta kurva MSE ADALINE yang melandai pada angka 0.342 tanpa pernah mencapai nol.

- Perbedaan Mekanisme Error: Perceptron menggunakan error diskrit berbasis fungsi tangga (ŷ ∈ {-1, +1}), sehingga pembaruan bobot hanya terjadi saat terjadi kesalahan prediksi kelas. Sebaliknya, ADALINE memanfaatkan error kontinu berbasis keluaran linier z, yang memperhitungkan seberapa jauh jarak prediksi dari target asli sehingga mampu memberikan batas keputusan yang lebih stabil.

- Dampak Standardisasi & Learning Rate: Standardisasi fitur terbukti sangat vital bagi ADALINE. Tanpa standardisasi (E8), fitur berskala besar seperti TotalCharges menyebabkan gradien meledak (gradient explosion) yang menghasilkan nilai NaN. Pemilihan η = 0.1 pada ADALINE (E7) juga menyebabkan overshooting pada fungsi kerugian.

## 10. Keterbatasan & Pengembangan Selanjutnya

Keterbatasan utama dari model Perceptron dan ADALINE adalah keterbatasannya sebagai pengklasifikasi linier lapis tunggal (single-layer), sehingga tidak mampu mempelajari pola hubungan non-linier yang kompleks antar atribut pelanggan. Sebagai langkah pengembangan selanjutnya, disarankan untuk mengimplementasikan arsitektur Multi-Layer Perceptron (MLP) dengan fungsi aktivasi non-linier (seperti Sigmoid atau ReLU) serta algoritma Backpropagation guna meningkatkan daya generalisasi model.

## 11. Kesimpulan

Model ADALINE dengan konfigurasi terstandardisasi dan η = 0.01 (E6) memberikan kinerja terbaik dengan akurasi uji sebesar 80.1% dan MSE sebesar 0.342. Meskipun Perceptron mampu mencapai akurasi uji 78.8%, proses pembelajarannya tidak konvergen secara mulus akibat sifat data yang tidak terpisah secara linier. Implementasi eksperimen ini berhasil membuktikan secara empiris perbedaan mendasar mekanisme pembelajaran Hebbian pada Perceptron dan Delta Rule pada ADALINE.
