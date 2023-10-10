# 🔮 Background dan Project Goals

Projek Eksplorasi Data Analisis (EDA) pada sebuah data marketing perusahaan distribusi makanan yang diperoleh dari website kaggle.com. Dataset berisikan consumer profile, product preference, dan campaign successes/failures. Tujuan dari eksplorasi data analisis pada dataset ini adalah untuk mendapatkan insight-insight yang bermanfaat dan menarik untuk tim marketing.

# 📊 Data Description
Dataset ini memiliki 28 feature dan 2240 data, di bawah ini merupakan penjelasan dari setiap feature:
1. ID: Pengenal Unik Pelanggan
2. Year Birth: Tahun Lahir Pelanggan
3. Education: ingkat pendidikan pelanggan
4. Marital Status: Status pernikahan pelanggan
5. Income: Pendapatan rumah tangga tahunan pelanggan
6. Country: Lokasi pelanggan
7. Kidhome: Jumlah anak dalam rumah tangga pelanggan
8. Teenhome: Jumlah remaja dalam rumah tangga pelanggan
9. Dt Customer: Tanggal pendaftaran pelanggan dengan perusahaan.
10. Recency: Jumlah hari sejak pembelian terakhir pelanggan
11. MntWines:Jumlah yang dihabiskan untuk wine dalam 2 tahun terakhir
12. MntFruits: Jumlah yang dihabiskan untuk buah-buahan dalam 2 tahun terakhir
13. MntMeatProducts: Jumlah yang dihabiskan untuk daging dalam 2 tahun terakhir
14. MntFishProducts: Jumlah yang dihabiskan untuk membeli ikan dalam 2 tahun terakhir
15. MntSweetProducts: Jumlah yang dihabiskan untuk permen dalam 2 tahun terakhir
16. MntGoldProds: Jumlah yang dihabiskan untuk emas dalam 2 tahun terakhir
17. NumDeals Purchases: Jumlah pembelian yang dilakukan dengan diskon
18. NumWebPurchases:Jumlah pembelian yang dilakukan melalui situs web perusahaan
19. NumCatalog Purchases: Jumlah pembelian yang dilakukan menggunakan katalog
20. NumStorePurchases: Jumlah pembelian yang dilakukan langsung di toko
21. NumWebVisits Month: Jumlah kunjungan ke situs web perusahaan dalam sebulan terakhir
22. AcceptedCmp1: 1 jika pelanggan menerima penawaran di kampanye pertama, O sebaliknya 
23. AcceptedCmp2: 1 jika pelanggan menerima penawaran di kampanye ke-2.0 sebaliknya 
24. AcceptedCmp3: 1 jika pelanggan menerima penawaran di kampanye ke-3, 0 sebaliknya 
25. AcceptedCmp4: 1 jika pelanggan menerima penawaran di kampanye ke-4,0 sebaliknya 
26. AcceptedCmp5: 1 jika pelanggan menerima penawaran dalam kampanye ke-5, 0 sebaliknya 
27. Response: 1 jika pelanggan menerima penawaran di kampanye terakhir, O sebaliknya (Variabel target)
28. Complain: 1 jika pelanggan mengeluh dalam 2 tahun terakhir. O sebaliknya

# 🧐 Analysis  
Pertama-tama yang dilakukan adalah melakukan data quality check. Beberapa pertanyaan yang harus di jawab pada tahap ini yaitu apakah ada feature yang memiliki tipe data yang tidak sesuai, apakah ada data duplicate, apakah ada missing values, dan apakah ada outliers yang tidak masuk akal. Pertanyaan-pertanyaan tersebut harus terjawab agar data bersih.    
![1_ tipe data yang tidak sesuai](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/ffe7b78b-64b9-4940-9318-1180fdc8ce8e)  

ternyata pada dataset ini ada feature yang memiliki tipe data tidak sesuai yaitu dt_customer dan income. Untuk feature income memiliki spasi sebelum namanya dan memiliki dollar sign yang akan mempersulit analisis kedepannya untuk itu selain mengubah tipe data nama kolomnya juga diubah  

![2_mengubah income dan dt_customer](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/a99b44ce-bde9-4ae7-aef9-e0748871c6dc)  


tipe data feature income diubah dari int menjadi float, untuk tipe data dt_customer diubah dari object menjadi datetime.  
selanjutnya akan kita lihat apakah ada duplikasi data atau tidak, dan ternyata pada dataset ini tidak ada duplikasi data.  

![3_dupicate](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/ed6dadff-7763-4542-ae50-a321fa3a4288)  
![4_missing values](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/2a5d1839-6695-45b4-a43c-bc0d017110cf)  
terdapat 24 missing values pada feature income, missing values tersebut akan diisi dengan nilai median kolom income  
  
![5_lihat distribusi income](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/f8a526f7-1877-4886-8415-f0bee60aed2c)
![5_](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/dd190c96-ea42-4be8-b1af-638757551952)  
Dapat dilihat dari distribusi feature income di atas bahwa terdapat pencilan yang sangat jauh, untuk itu nilai median digunakan untuk mengisi missing values pada feature income.  

  
![5_lihat distribusi](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/c9252581-9579-4255-a37d-d556160be5b3)  
![5_lihat outliers](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/8daa1b18-47d0-4f8c-b35d-8c54b0fc0e98)   

Distribusi untuk semua feature numerical rata-rata terlihat baik dan tidak ada yang kurang dari 0, namun feature year_birth memiliki outliers yang tidak masuk akal untuk itu data akan di remove.  


    
Setelah data bersih, selanjutnya akan menggali insights dari semua kolom yang ada dan melihat apakah ada sebuah pattern dengan variable target (Response).  

  
![1  Customer_Age (Bar Chart)](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/1b4efbb6-3b88-45ab-a062-86a4a6f821e0)  
Rata-rata umur customer yaitu berada pada rentang umur 40-an.  
![2  customer_age, response (kde)](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/1bdbb0f5-9271-4bac-a0f1-785414c55aa1)  
Dari bar chart di atas diketahui bahwa yang menerima tawaran campaign juga rata-rata di umur 40-an, dapat dilihat distribusi dari tawaran campaign yang diterima dan tidak diterima sama.  
![3  Education, response (bar chart)](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/60d34b48-4211-42a2-a232-1c1515e6eda6)  
Dari bar chart hubungan antara education dan response dapat diketahui bahwa customer terbanyak merupakan lulusan graduation, namun untuk yang menerima tawaran campaign hanya 13% dari total keseluruhan lulusan graduation. Customer lulusan PhD cenderung menerima tawaran campaign, 22% dari total keseluruhan lulusan PhD. Sedangkan lulusan basic paling sedikit menerima tawaran campaign.  
![4  Education, income, response (boxplot)](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/79cdf8e0-fb0c-4eeb-8f4a-67c7cf766f38)  
Dari boxplot korelasi antara education, income dan response di atas dapat dilihat bahwa semakin tinggi pendidikan maka income semakin tinggi. Graduation, PhD, dan Master memiliki rata-rata income yang sama. Dapat diketahui bahwa rata-rata income dari customer yang menerima tawaran campaign selalu lebih tinggi dibandingkan dengan yang tidak menerima tawaran campaign.  
![5  Marital status, response (bar chart)](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/516dda75-52f7-4453-9af3-172d6758c82a)
![6  num dependants, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/500e5390-a50d-46f7-9a2f-19a8aad11d9c)
![7  Dt customer month, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/a869deaa-3987-4d1f-beb2-5ac73fe214ec)
![8  Dt customer year, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/099cc344-78a3-4ec7-ae35-3a35f41cf3cd)
![9  recency, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/cabe6934-217d-45b8-9e60-c1060d65cad4)
![10  total amnt spent, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/0509ef5a-5ccb-4ff1-81bf-8ed3f0a73168)
![11  total purchases, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/1d4e353b-1afb-4510-85d6-b6dfb88721ba)
![12  country, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/6f7ffb29-7809-454e-80d2-8c1b8d13ee9b)


# 📃 Conclusion
:black_medium_square: Customer yang belum lama membeli, cenderung menerima penawaran campaign terbaru.  
:black_medium_square: Semakin lama customer sudah terdaftar dalam sistem, semakin besar kemungkinan customer akan menerima penawaran campaign.  
:black_medium_square: Jika customer sudah menghabiskan sekitar 1000-2000 dollar, maka customer ini cenderung menerima penawaran campaign.  
:black_medium_square: Campaign 1, 3 dan 5 merupakan Campaign yang paling berkolerasi.  
:black_medium_square: Customer terbanyak berasal dari Spanyol, namun hanya 16% dari total customer yang menerima penawaran campaign. Sedangkan Mexico merupakan negara dengan customer paling sedikit, namun paling banyak menerima tawaran campaign.


