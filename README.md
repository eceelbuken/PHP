# PHP
 ##
                                                                 PHP RAPORU
                                                                 
  PHP NEDİR?
  PHP; dinamik web siteleri, web uygulamaları geliştirmek için oluşturulan web tabanlı olarak çalışan bir programlama dilidir. PHP site ve PHP programlar için kullanılabilir.
  DEĞİŞKENLER
  Php’de bir değişken $ işareti ile başlar.
  Değişkenler rakam ile başlayamazlar.
  _ dışında özelm karakter kullanılamaz mesela + - * ? ! vs. şeklinde
  Türkçe karakter kullanılmamalıdır.
  Echo komutu ile ekrana yazdırılırlar.
  Değişkenlerde veri türü tanımlanmıyor direkt değerin veri türüne göre değişkenimiz o veri türüne sahip oluyor.
  Birden fazla değişken ekrana bastırılacaksa   *echo "$ad $yas";  şeklinde tırnak içine alınarak yazılır.
  Eğer *echo '$ad $yas'; yazılırsabu sefer ekrana değişkenin değeri değil doğrudan değişken yazılır mesela bu örnek için ekran çıktımız $ad $yas olacaktır.
  Değişkenler ile dizi de tanımlanabilir mesela $dizi = array("ece","ramazan"); şeklinde yazılarak dizi tanımlanabilir ve ekrana bastırılmak istendiğinde ise echo $dizi[0] diyerek index değeri verilir ve index değerindeki eleman ekrana bastırılmış olur.
  boolean şeklinde kullanmak istersek eğer o zaman da şöyle yazıyoruz $kontrol = true; eğer bunu yazarsak ekrana 1 basar $kontrol= false; yazılırsa da ekranda bir şey gözükmez yani boşluk basmış olur.
  PHP'de Veri Türleri
PHP'de 4 farklı temel veri türü vardır:   
boolean : TRUE (Doğru) ya da FALSE (Yanlış) değeri alan bir veri türüdür.     
integer : Bir tamsayı değer içeren bir veri türüdür.     
float : Büyük ve ondalıklı sayıları tanımlamaya yarayan veri türüdür.     
string : Karakter dizileri tanımlamaya yarayan bir veri türüdür.
PHP''de 2 bileşik veri türü vardır:      
Dizi (Array) : Farklı veri türlerini tek bir değişken adı ile tanımlayan bir veri kümesidir.     
Nesne (Object) : Farklı veri türlerine ve fonksiyonlardan oluşan bir veri topluluğuna tek bir isim ile erişim sağlayan bir veri türüdür.
PHP DİZİLERLE ÇALIŞMA
<?php

$hafta = array("pazartesi","Salı","Çarşamba","Perşembe",

             "Cuma","Cumartesi","Pazar");

echo $hafta[3]; // ekrana perşembe yazar

?>
burada dizi oluşturmaya ve ekrana bastırmaya bir örnek vererek konu özetini geçiyorum.
PHP RAKAMLARLA ÇALIŞMA
echo 5 - 9;
echo 8 + 7;
echo 5.7 * 9;
echo 5.7 / 9;
echo 10 % 3;
echo (4+5) * 10;
bu şekilde kodlayarak rakamlarla 4 işlem yapılabilir veya başka bir seçenek olarak da değişken tanımlarsın o değişkene değer atarsın ve değişkenler ile  oynayarak ekrana yine dört işlem sonucunu bastırırsın mesela bir örnek vereyim;
$sayi1 = 10;
$sayi2 =20;
echo $sayi1 + $sayi2; // + - * gibi oynama yapılabilir bu şekilde
bunu yazarsak ekrana sonuç olarak 30 bastırılır.
GET VE POST KARŞILAŞTIRMASI
Get ve post kullanıcıdan alınan bilgileri iletmek için kullanılan methodlardır. Aradaki fark şu;
Get'te verileri açık olarak gönderilirken postta verileri tamamen kapalı şekilde gönderiyoruz. Gette gönderdiğimiz veriler gözükebilirken postta gönderdiğimiz veriler gözükmez.Arka tarafta gizli olarak iletilir.Sayfalarda get methodunun kullanımı güvenlik açısından tehlikelidir.Özellikle SQL injection yapıları, SQL sorgularına yapılan müdahaleler bu yapılar üzerinden işleniyor.






GET İÇİN ÖRNEK VERİRSEK;  (hazır örnek kullanımı daha iyi anlaşılması için koydum)
Anasayfa, Hakkımızda ve haberler adında 3 adet sayfamız olsun. Bu 3 sayfa içinde farklı farklı php dosyası oluşturmak hem bizim işimizi zorlaştırır hemde hafıza maliyetimizi artırır. Biz tek bir sayfada kullanıcıya 3 sayfa gösterelim hem sayfa fazlalığından hemde hafıza maliyetinden kar etmeye çalışalım.

Algoritmamız: Sayfalarımıza bizim belirlediğimiz indis numaraları verelim.

anasayfa
hakkımızda
haberler
Daha sonra anasayfada get methodu ile bu indisleri kullanarak diğer sayfalarımza erişelim.

Kodumuz:

<?php

$v = isset($_GET["v"]) ? intval(trim($_GET["v"])) : 1;
// eğer $_GET["v"] değişkenimiz yoksa biz anasayfadayızdır bu yüzden indisi 1 yaptık. 

// linklerimiz Tüm Sayfalarda Görünsün.
echo '
<a href="?v=1">Anasayfa</a> | 
	<a href="?v=2">Hakkımızda</a> | 
	<a href="?v=3">Haberler</a> | <hr>

';


if($v == 1) {
	// Burada Anasayfa Görünür.
	
	echo '
	Merhaba Anasayfadasın.';
	
}else if($v == 2) {
	// Burada Hakkımızda Görünür.
	echo "Merhaba Hakkımızda Sayfasındasın.";
}else if($v == 3) {
	// Burada Haberler Görünür.
	echo "Merhaba Haberler Sayfasındasın.";
}else {
	// Burasıda Farklı Bir İndis Gelirse Yapılan İşlemlerimiz.
	echo "Üzgünüm Bu Sayfa Henüz Oluşturulmadı. Bunun Bir Hata Olduğunu Düşünüyorsan Bize Bildir... ";
	

<?php
 
$v = isset($_GET["v"]) ? intval(trim($_GET["v"])) : 1;
// eğer $_GET["v"] değişkenimiz yoksa biz anasayfadayızdır bu yüzden indisi 1 yaptık. 
 
// linklerimiz Tüm Sayfalarda Görünsün.
echo '
<a href="?v=1">Anasayfa</a> | 
 <a href="?v=2">Hakkımızda</a> | 
 <a href="?v=3">Haberler</a> | <hr>
 
';
 
 
if($v == 1) {
 // Burada Anasayfa Görünür.
 
 echo '
 Merhaba Anasayfadasın.';
 
}else if($v == 2) {
 // Burada Hakkımızda Görünür.
 echo "Merhaba Hakkımızda Sayfasındasın.";
}else if($v == 3) {
 // Burada Haberler Görünür.
 echo "Merhaba Haberler Sayfasındasın.";
}else {
 // Burasıda Farklı Bir İndis Gelirse Yapılan İşlemlerimiz.
 echo "Üzgünüm Bu Sayfa Henüz Oluşturulmadı. Bunun Bir Hata Olduğunu Düşünüyorsan Bize Bildir... ";
 
}
 
?>




