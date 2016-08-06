---
layout: post
encoding: utf-8
title: Steganografi ve LSB
---

Steganografi, içinde gizli mesaj veya bilgiler bulunan bir veriyi, alıcıdan başka kimsenin fark edemeyeceği bir biçimde gönderme sanatıdır. Buradaki amaç, iletilmek istenen bilgiyi ve bu bilginin varlığını başkalarının fark etmesini engelleyebilecek kadar iyi saklamaktır. İçerisinde gizlenmiş bilgiler barındıran bir veriye herhangi birisi ulaşabilse dahi bu verideki Steganografi işlemini fark edebilmeli ve güvenlik yöntemleri ve seviyelerine bağlı olan anahtar bilgiye de sahip olmalıdır.

# Steganografi ve Kriptografi
Veri gizleme işlemi olan Steganografi, şifre bilimi olan Kriptografi'den oldukça farklıdır. Kriptografi, iletilmek istenen bilgilerin belirli bir şifreleme algoritmasına tabi tutulmasının ardından, alıcının bu iletileri ancak deşifre etmesi ile ulaşabildiği yöntemdir. Steganografi ise iletilmek istenen bilgiyi başka bilgiler içerisinde saklayarak diğer kişiler tarafından ulaşılmasına engel olur.

Steganografi'de bilginin taşınacağı bir haberleşme kanalı, bilgiyi barındıran bir taşıyıcı, bilginin nasıl ve hangi yolla taşınacağı ve nasıl çözüleceği bilgileri bulunmak zorundadır. Kriptografi'de ise bilginin açığa çıkmasını engellemek için güçlü bir şifreleme algoritması kullanılır ve haberleşmenin izlenip izlenmediği ile ilgilenilmez. Bilginin gizliliğini saklama ihtiyacı duyulmaz.

Steganografi ile içerisine bir bilgi gizlenmiş olan veriyi elinde bulunduran bir kimsenin bu veride gizli bir mesaj olduğunu fark etmesi neredeyse imkansızdır. Eldeki veriden şüphe duyulması durumunda veri analiz edilerek (bkz: [Steganalysis](https://en.wikipedia.org/wiki/Steganalysis)) işlem fark edilebilir ancak mesajın ayıklanarak ele geçirilmesi farklı bir süreç olacaktır. Verinin güvenliğinin sağlanması adına çeşitli güvenlik yöntemleri uygulanarak süreç güç bir hale getirilebilir.  

Aşağıdaki resimde Steganografi işleminin tespit edilmesine yönelik yapılmış bir analiz mevcut.

<img src="/assets/img/2015/lsbanalyse.jpg" style="width: 600px;"/>

3'üncü resimde gizlenmiş veri çok açık bir biçimde görülmekte.

# Piksellerin Yapısı
Sayısal resimler N satır ve M sütunluk bir dizi ile temsil edilir. Bir resim dizisinin elemanlarına piksel denir. En basit durumda pikseller 0 ve 1 değerini alırlar. Bu piksellerden oluşan resimlere ikili(binary) resim denir.

![](/assets/img/2015/pixelarray.jpg)

# En Önemsiz Bit (Least Significant Bit)

Resim içerisinde veri gizlerken en çok kullanılan yöntem resmi oluşturan piksellerin en düşük anlamlı bitine veriyi gömmektir. Uygulaması çok basit olan bir yöntem olmasına karşın, dikkatsizce uygulanması durumunda veri kayıpları oluşabilir. Bu yöntem ile gizlenecek verinin her biti, resim verisinin bir baytının son bitine yazılır. Bu yöntemin en çok tercih edilen yöntemlerden biri olmasının sebebi en son bitte yapılan değişikliğin gözle görülür bi fark yaratmamasıdır. Bunun bir örneğini Github profilimde yer alan [Steg](https://github.com/ertseyhan/steg.git) projesini inceleyerek görebilirsiniz.

![](/assets/img/2015/lsbits.jpg)

Kaynaklar  
1. [http://ab.org.tr/ab13/bildiri/59.pdf](http://ab.org.tr/ab13/bildiri/59.pdf)  
2. [http://bilgisayarkavramlari.sadievrenseker.com/2009/06/05/steganografi-ve-lsb/](http://bilgisayarkavramlari.sadievrenseker.com/2009/06/05/steganografi-ve-lsb/)  
3. [http://web.itu.edu.tr/~orssi/thesis/2008/BetulElci_bit.pdf](http://web.itu.edu.tr/~orssi/thesis/2008/BetulElci_bit.pdf)  
4. [https://tr.scribd.com/doc/48764974/31/VISUAL-C](https://tr.scribd.com/doc/48764974/31/VISUAL-C)  
5. [https://lvee.org/en/abstracts/106](https://lvee.org/en/abstracts/106)  