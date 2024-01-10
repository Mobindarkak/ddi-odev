# ddi-odev

# markaTahmin-ddi

### Projeyi Hazırlayanlar;
Mobin DARKAK 213405523

#### Kullanılan Kütüphaneler
-Pandas      
-Numpy  
-Pyplot  
-Scikit-Learn  
-BeautifulSoup  

##### Veri Setinin Oluşturulması
Veri setimi internetten hazır olarak aldım 6000 veri vardı ben de 3000 veri daha ekledim. 

Veri setindeki kolonlarımız aşağıdaki gibidir;  
-Metinler      
-Durumlar    

*Oluşturulmuş Veri Seti*  
![Oluşturulmuş Veri Seti](https://github.com/Mobindarkak/ddi-odev/blob/main/images/Ekran%20görüntüsü%202024-01-10%20183911.png)

##### Yorumların Temizlenmesi ve Lemmatization İşlemi
Veri seti oluşturulduktan sonra modelin daha iyi çalışması ve başarı oranının daha yüksek olması için yorumların temizlenmesi gerekmektedir. Yorumların içerisinde emojiler, noktalama işaretleri, stop wordsler, linkler gibi istenmeyen ve modelin başarısını düşürecek veriler ilanların içerisinden temizleniyor.

*Oluşturulmuş Temiz Yorum Gösteremi*  
![Oluşturulan Temiz İlan](https://github.com/Mobindarkak/ddi-odev/blob/main/images/Ekran%20görüntüsü%202024-01-10%20183919.png)  

##### Modelin Oluşturulması
###### Model Seçimi
Yapılacak sınıflandırma işleminin hangi modelde daha yüksek başarı oranı vereceğini tespit etmek amacıyla araştırma yapılıp aynı zamanda bazı modeller üzerinde de test edilmiştir.2 model üzerinde denemeler yapılmıştır. Bu modeller Naive bayes ve Decision Tree modelleridir. Projedeki test veri seti sonuçlarına bakıldığında;  
  Decision Tree Modeli Başarısı:0.746  
Sonuçlar incelendiğinde Decision Tree modelinin projede kullanılan veri seti için daha doğru sonuç verdiği görülmüştür bu yüzden projeyi Decision Tree modeli üzerinde yapmaya karar verdik.  
  
![Oluşturulan Temiz Yorum](https://github.com/Mobindarkak/ddi-odev/blob/main/images/Ekran%20görüntüsü%202024-01-10%20183945.png)  

##### Veri Setinin Parçalanması
Model başarısını doğru şekilde değerlendirebilmek için, eğitim ve test aşamalarında farklı veri kümeleri kullanmak önemlidir. Modelin eğitiminde kullanılan veriler, test aşamasında tekrar kullanılmamalıdır çünkü bu durum modelin başarısını yanıltıcı bir şekilde yüksek gösterebilir. Bu sebeple, veri setini bölmek gereklidir. Bu proje için, veri setinin %80'i modelin eğitimi için kullanılacak, geri kalan %20'si ise modelin test edilmesi için ayrılacaktır.	
Veri setini parçalamak için train_test_split() fonksiyonu kullanılmıştır.

##### Yorumların Vektörel Matrisinin Çıkarılması
TF-IDF vektörleme yöntemi kullanılarak, her bir yorumdaki kelimelerin belge içindeki önemi istatistiksel olarak hesaplanmıştır. Bu süreçte, yaygın stopwords'lar gibi anlam taşımayan kelimeler filtrelenerek, model için gereksiz olan unsurların etkisi azaltılmıştır. Bu sayede, anlamlı ve bilgi taşıyan özellikler belirginleştirilmiştir, modelin doğruluğunu artırmak adına daha sağlam bir temel oluşturulmuştur.

#### Modelin Eğitilmesi
Decision Tree metoduyla modelimiz eğitilmiştir. Modeli eğitmek için sklearn kütüphanesinden faydalanılmıştır.
##### Modelin Başarısının Hesaplanması
Hesaplama aşağıdaki görseldedir  
![Model Başarısı](https://github.com/Mobindarkak/ddi-odev/blob/main/images/Ekran%20görüntüsü%202024-01-10%20183945.png)  

### SONUÇ
Özetle yaptığımız projede seçilen modelin ne kadar önemli olduğu görülmektedir. Başlangıçta test edilmiş olan Naive Bayes modelinin bu veri seti için Decision Tree modeline göre uygunluğu daha azdır. Ancak model seçiminin önemi kadar veri setinin de güzel bir şekilde hazırlanmış olması, güzel temizlenmesi, veri setindeki veri miktarı, veri setinin dengesiz olup olmaması, eğitim-test setinin parçalanma oranı vb. faktörler modelin başarısına etki edildiği anlaşılmıştır.
