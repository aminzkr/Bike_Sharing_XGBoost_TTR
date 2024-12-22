# Context

Sistem bike-sharing merupakan generasi baru dari penyewaan sepeda tradisional yang seluruh prosesnya, mulai dari keanggotaan, penyewaan, hingga pengembalian, telah menjadi otomatis. Melalui sistem ini, pengguna dapat dengan mudah menyewa sepeda dari lokasi tertentu dan mengembalikannya di lokasi lain. Saat ini, terdapat sekitar lebih dari 500 program bike-sharing di seluruh dunia yang terdiri dari lebih dari 500 ribu sepeda.
Sistem ini memiliki minat yang besar karena perannya yang penting dalam masalah lalu lintas, lingkungan, dan kesehatan.
Selain aplikasi sistem bike-sharing yang menarik di dunia nyata, karakteristik data yang dihasilkan oleh sistem ini membuatnya menarik untuk diteliti. Tidak seperti layanan transportasi lain seperti bus atau kereta bawah tanah, durasi perjalanan, posisi keberangkatan, dan kedatangan dicatat secara eksplisit dalam sistem ini. Fitur ini mengubah sistem bike-sharing menjadi jaringan sensor virtual yang dapat digunakan untuk mendeteksi mobilitas di kota. Oleh karena itu, diharapkan bahwa peristiwa terpenting di kota dapat dideteksi dengan memantau data ini.

# Potential Variabel Approaches
Dari features yang ada, terdapat potensi yang dapat di analisis yaitu:
1. Total Bike Rentals: Memprediksi keseluruhan demand dan melakukan optimasi sistem yang ada
2. User Behavior: Menganalisa dan memprediksi behavior dari masing-masing user
3. Hourly Analysis: Menganalisa penyewaan sepeda per jam untuk melakukan forecast sepeda yang tersedia secara jangka pendek
4. Daily Analysis: Melakukan analisa dengan mengagregasi `cnt` untuk mengetahui tren berdasarkan waktu dan season

# Selected Goal
Sebagai pendekatan awal, `Data Scientist` akan melakukan analisa terkait **Total Bike Rentals** dengan memprediksi keseluruhan demand dan melakukan optimasi sistem yang ada.
Hasil dari Goals ini nantinya dapat memberikan sistem model yang dapat membantu kita menentukan demand secara dinamis pada tiap kondisi baik secara waktu, kondisi cuaca dan lainnya. Nantinya model ini membantu dalam memanipulasi dan memodifikasi strategi bisnis kedepannya untuk memenuhi demand dan ekspektasi para user.

# Analytical Approaches
Dalam pemodelan menggunakan pendekatan regresi, ada yang di sebut sebagai `Metrics`. Tiap `Metrics` akan melakukan pendekatan secara berbeda-beda yang nantinya berguna untuk tiap variabel. Berikut penjelasan secara umum mengenai `Metrics` pada model Regresi.

# Benchmark Metrics

Dalam pemodelan kali ini, tim `Data Scientist` akan melakukan pendekatan model menggunakan metric `MAPE`. Alasannya karena metric ini tidak ketergantungan terhadap skala dan mampu mempredksi pada skala yang berbeda. Selain itu metric ini juga umum digunakan dalam pemahaman bisnis karna dalam bentuk persentase dan robust terhadap outlier. 

Nantinya tim `Data Scientist` seminimal mungkin mampu memperoleh model yang dapat melakukan forescasting yang masih dapat diterima dengan rentang nilai MAPE seperti dibawah.
1. MAPE < 10 = Highly Aaccurate forecasting
2. MAPE = 10-20  (Good Forecasting)
3. MAPE = 20-50 (Reasonable forecasting)
4. MAPE > 50 = Inaccurate forecasting


# Raw Data Information

Dari informasi yang diperoleh terhadap  `Features` yang ada pada data yang diberikan ke tim `Data Scientist`. Informasi tersebut adalah.
- dteday: date
- season: season (1: winter, 2: spring, 3: summer, 4: fall)
- hr: hour (0 to 23)
- holiday: holiday or not
- temp: normalized temperature in Celsius. The values are derived via (t-tmin)/(tmax-tmin), tmin=-8, t_max=+39 (only in hourly scale)
- atemp: Normalized feeling temperature in Celsius. The values are derived via (t-tmin)/(tmax-tmin), tmin=-16, t_max=+50 (only in hourly scale)
- hum: normalized humidity. The values are divided into 100 (max)
- casual: count of casual users
- registered: count of registered users
- cnt: count of total rental bikes including both casual and registered
- weathersit:
    1. Clear, Few clouds, Partly cloudy, Partly cloudy
    2. Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
    3. Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
    4. Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
