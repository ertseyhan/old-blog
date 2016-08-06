---
layout: post
encoding: utf-8
title: Azure üzerinde Ghost Blog Güncellemesi
---

Henüz genç bir proje olan ve geliştirilmeye devam eden Ghost, kendi içerisinde bir güncelleme sistemi bulundurmuyor. Bu nedenle güncellemeyi Azure üzerinde yapabilmek için ufak bir araç kullanmakla yükümlüyüz.

Eğer Azure üzerinde yeni bir Web App oluşturmuş ve Ghost kurulumunu otomatik yaptırdıysanız, `0.5.7` sürümünün yüklendiğini göreceksiniz. Bu yazıyı yazdığım tarihte ise Ghost'un `0.7.1` versiyonu mevcut. Bu gibi durumlarda güncelleme yapmanız sağlıklı olacaktır.

# Yedek alın
İşleme başlamadan önce sunucunuzda yedek almak gibi bir zorunluluğunuz yok. Kullanacağımız araç yedekleme işlemini eğer isterseniz, sizin yerinize yapacak. Olası bir hata ile karşılaşmanız durumunda ise aldığınız yedeği tekrar yükleyip kaldığınız yerden devam edebileceksiniz.

Yinede ben işimi koda bırakmam diyorsanız, elbette kendi yedeğinizi almanızda bir sakınca yok.

# İndirmeler

İlk olarak yukarıda bahsettiğimiz güncelleme işlemini yapacağınız aracı indiremeniz gerekmekte. [Bu bağlantıdan](https://github.com/felixrieseberg/Ghost-Updater-Azure/releases) kendi işletim sisteminize uygun olan paketi indirin.

Kendi güncellememi Linux üzerinden yaptığımı ve bu anlatımı da buna göre yaptığımı belirteyim.

Aracı indirdikten sonra yayınlanan son sürüm Ghost paketini indirmeniz gerekiyor. Onu da [bu bağlantıdan](https://github.com/TryGhost/Ghost/releases) indirin.

64 bit sistemlerde Runtime hatası alabilrsiniz. 32 bit kütüphaneleri kurmanız gerekmekte.

Herhangi bir sorun oluşmadan uygulamayı çalıştırdıysanız aşağıdaki gibi bir arayüz ile karşılaşacaksınız.
<img src="/assets/img/2015/9c549f5fa4.jpg" style="width: 600px;"/>

Blog URL kısmına blogunuzun adresini yazdıktan sonra kullanıcı adınızı ve şifrenizi girin. Eğer hatırlamıyorsanız, Azure üzerinde Web App kontrol paneli'ne gidin ve `Reset your deployment credentials` seçeneği ile yeni bir şifre alın. Ancak daha önce bu şifreyi oluşturmadıysanız, yine kontrol paneli üzerinden `Set up deployment credentials` seçeneği ile şifrenizi oluşturun. Buraya kadar gerekli alanları doldurduktan sonra, indirdiğiniz Ghost paketini seçin ve devam edin.
<img src="/assets/img/2015/58j23bn912.jpg" style="width: 600px;"/>

Eğer daha önce kendiniz yedek almadıysanız bu aşamada yedek almalısınız. Tercihinize göre istediğiniz seçeneği seçin ve devam edin.

Aşağıdaki gibi bir güncelleme ekranı göreceksiniz. Aşağıdaki çıktıdan'da neler döndüğünü az çok görebilirsiniz.
<img src="/assets/img/2015/47jg25a21b.jpg" style="width: 600px;"/>

İşlem bittiğinde ise işlemin başarılı olduğuna dair bir mesaj aldıktan sonra blog adresinize girip, her şeyin yolunda olup olmadığını kontrol edin. Herhangi bir hata ile karşılaşmadıysanız eğer sorun yok demektir. Yönetici paneline girip Ghost uygulamasının sürümünü de kontrol etmek isteyebilirsiniz.

Kontrolünüzü yaptınız ve sorun ile karşılaşmadıysanız araç üzerinden aldığınız yedeği silebilirsiniz. Veya herhangi bir hata durumunda aldığınız yedeği `Restore Backup` seçeneği ile yükleyebilirsiniz. Bu sayede aldığınız yedeği tekrar aktif etmiş olacaksınız.