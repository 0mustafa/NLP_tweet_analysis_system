# NLP_tweet_analysis_system
Bu projede Twitter'dan çekilen verilerle oluşturulan veritabanı kullanılarak, girilen alternatif bir Tweet'in kime ait olabileceği yüzdesel olarak tahmin edilmektedir.
  ### Projenin Kullanım Alanları
    - Bir tweetin daha önce birisi tarafından paylaşılmış olma ihtimali hesaplanabilir.
    - Daha önce paylaşılmamış bir tweetin hangi kullanıcı tarafından yazılmış olabileceği tahmin edilebilir.
<br/>
<br/>
<br/>

## Twitter'dan Veri Çekmek
Veri çekerken pythonda bulunan `snscrape` kütüphanesi kullanılmıştır.<br/>
Bu kütüphane temel olarak Twitter'da bulunana `Advanced Search` alanının yazılıma implemente edilmiş halidir.

```
query = "(from:netflixturkiye) until:2023-01-01 since:2021-01-01"
```
Verilen örnekte `netflixturkiye` kullanıcı adına sahip twitter hesabından `01.01.2021 - 01.01.2023` tarihleri arasındaki tüm tweetleri görmek isteyeceğimiz bir sorgu gösterilmektedir.
<br/>
Daha sonrasında çekilen veriler bir csv dosyasına aktarılarak işlenmeye hazır hale getirilmektedir.
<br/>
<br/>

## Verilerin işlenmesi
Başka bir python dosyasında içeri aktarılan veriler bir temizleme fonksiyonundan geçmektedir.
![Screenshot_3](https://user-images.githubusercontent.com/78226423/210452126-2dc6ae3a-60ab-41fc-beca-5031be8228dd.png)
<br/>
Bu temizleme fonksiyonunda verilerin içindeki sayılar ve bazı kelimeler herhangi bir anlam ifade etmediğinden verimizin içinden çıkarılmıştır.
<br/>
Devamında noktalama işaretlerinden de ayıklanan tweetlerimiz `clean` sütunu altına yazılmıştır.
<br/>
Algoritmamızın düzgün çalışabilmesi için tweetleri etiketlememiz gerekmektedir.
<br/>
```
* Acun Ilıcalı: 0
* Rasim Ozan Kütahyalı: 1
* Webtekno: 2
* Netflix: 3
```
<br/>
Yukarıdaki etiketlemeye sadık kalarak verilerimizi etiketliyoruz.
<br/>

![Screenshot_4](https://user-images.githubusercontent.com/78226423/210455971-670e4385-9498-47ed-b119-8e375de1fd02.png)

<br/>

Verilerden elde edeceğimiz analiz için `TF-IDF`, `Bayes teoremi` ve `Decision Tree` algoritmalarını kullanıyoruz.
<br/>
Projemiz artık bitmiş durumda verilen bir Tweet'in 4 kullanıcıdan hangilerine ait olabileceğini sağlıklı bir şekilde oransallaştırabilmektedir.
<br/>

![Screenshot_5](https://user-images.githubusercontent.com/78226423/210456303-2c421dbb-0a9c-4570-afe2-7e68a7041f48.png)
Projemize son olarak Netflix'in eskiden attığı `önerdiğim diziyi izledin mi diyorum bana nau nau diyor` Tweet'ini veriyoruz ve bize aşağıdaki sonuçları veriyor.
<br/>

```
* Acun Ilıcalı: %0.56
* Rasim Ozan Kütahyalı: %6.95
* Webtekno: %4.92
* Netflix: %87.57
```




