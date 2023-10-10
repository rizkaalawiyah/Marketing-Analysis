# 🔮 Background dan Project Goals

Projek Eksplorasi Data Analisis (EDA) pada sebuah data marketing perusahaan distribusi makanan yang diperoleh dari website kaggle.com. Dataset berisikan consumer profile, product preference, dan campaign successes/failures. Tujuan dari eksplorasi data analisis pada dataset ini adalah untuk mendapatkan insight-insight yang bermanfaat dan menarik untuk tim marketing.

# 📊 Data Description
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
Pertama-tama yang dilakukan adalah melakukan data quality check. Apakah ada feature yang memiliki tipe data yang tidak sesuai, data duplicate, dan missing values.

![1_ tipe data yang tidak sesuai](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/ffe7b78b-64b9-4940-9318-1180fdc8ce8e)

ternyata pada dataset ini ada feature yang memiliki tipe data tidak sesuai yaitu dt_customer dan income. Untuk feature income memiliki spasi sebelum namanya dan memiliki dollar sign yang akan mempersulit analisis kedepannya untuk itu selain mengubah tipe data nama kolomnya juga diubah

![2_mengubah income dan dt_customer](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/a99b44ce-bde9-4ae7-aef9-e0748871c6dc)


tipe data feature income diubah dari int menjadi float, untuk tipe data dt_customer diubah dari object menjadi datetime.
selanjutnya akan kita lihat apakah ada duplikasi data atau tidak, dan ternyata pada dataset ini tidak ada duplikasi data.

![3_dupicate](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/ed6dadff-7763-4542-ae50-a321fa3a4288)
![4_missing values](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/b9d13674-cc66-410f-8c5e-e0df07c3c050)
terdapat 24 missing values pada feature income, missing values tersebut akan diisi dengan nilai median kolom income

![5_lihat outliers](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/8daa1b18-47d0-4f8c-b35d-8c54b0fc0e98)

![5_](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/dd190c96-ea42-4be8-b1af-638757551952)
![5_lihat distribusi income](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/f8a526f7-1877-4886-8415-f0bee60aed2c)
![5_lihat distribusi](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/c9252581-9579-4255-a37d-d556160be5b3)



![1  Customer_Age (Bar Chart)](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/1b4efbb6-3b88-45ab-a062-86a4a6f821e0) 
![2  customer_age, response (kde)](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/1bdbb0f5-9271-4bac-a0f1-785414c55aa1)
![3  Education, response (bar chart)](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/60d34b48-4211-42a2-a232-1c1515e6eda6)
![4  Education, income, response (boxplot)](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/79cdf8e0-fb0c-4eeb-8f4a-67c7cf766f38)
![5  Marital status, response (bar chart)](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/516dda75-52f7-4453-9af3-172d6758c82a)
![6  num dependants, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/500e5390-a50d-46f7-9a2f-19a8aad11d9c)
![7  Dt customer month, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/a869deaa-3987-4d1f-beb2-5ac73fe214ec)
![8  Dt customer year, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/099cc344-78a3-4ec7-ae35-3a35f41cf3cd)
![9  recency, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/cabe6934-217d-45b8-9e60-c1060d65cad4)
![10  total amnt spent, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/0509ef5a-5ccb-4ff1-81bf-8ed3f0a73168)
![11  total purchases, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/1d4e353b-1afb-4510-85d6-b6dfb88721ba)
![12  country, response](https://github.com/rizkaalawiyah/Marketing-Analysis/assets/43191119/6f7ffb29-7809-454e-80d2-8c1b8d13ee9b)


# 📃 Conclusion


