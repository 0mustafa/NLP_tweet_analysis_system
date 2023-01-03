# NLP_tweet_analysis_system
Bu projede Twitter'dan çekilen verilerle oluşturulan veritabanı kullanılarak, girilen alternatif bir Tweet'in kime ait olabileceği yüzdesel olarak tahmin edilmektedir.


## Twitter'dan Veri Çekmek
Veri çekerken pythonda bulunan `snscrape` kütüphanesi kullanılmıştır.
Bu kütüphane temel olarak Twitter'da bulunana `Advanced Search` alanının yazılıma implemente edilmiş halidir.

```
query = "(from:netflixturkiye) until:2023-01-01 since:2021-01-01"
```
Verilen örnekte `netflixturkiye` kullanıcı adına sahip twitter hesabından 01.01.2021 - 01.01.2023 tarihleri arasındaki tüm tweetleri görmek isteyeceğimiz bir sorgu gösterilmektedir.
