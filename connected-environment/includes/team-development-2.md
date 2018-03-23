2. F5 isabet (veya türü `vsce up` Terminal penceresinde) hizmetini çalıştırmak için. Bunu otomatik olarak çalıştırılacak onu yeni seçilen bizim alanı `scott`. 
1. Biz çalıştırarak doğrulayabilirsiniz `vsce list` yeniden. İlk olarak, bir örneğini göreceksiniz `mywebapi` şu anda çalışıyor `scott` alanı (çalışan sürüm `mainline` hala çalışıyor, ancak listede olmayan). İkincisi, erişim noktası için URL `webfrontend` metinle "tan-" öneki. Bu URL için benzersiz olan `scott` boşluk ve "Tan URL'ye" gönderilen istekleri Hizmetleri'nde ilk yol dener güveninin `scott` boşluk ve Hizmetleri için döner `mainline` alanı.

```
Name         Space     Chart              Ports   Updated     Access Points
-----------  --------  -----------------  ------  ----------  -------------
mywebapi     scott     mywebapi-0.1.0     80/TCP  15s ago     http://localhost:61466
webfrontend  mainline  webfrontend-0.1.0  80/TCP  5h ago      https://scott-webfrontend-contosodev.vsce.io
```

![](../media/space-routing.png)

Test ortamı bağlı etkinleştirir, bu yerleşik yetenek yerlerini Hizmetleri'nde tam yığını yeniden oluşturmak her geliştirici gerek kalmadan baştan sona paylaşılan ortamından içindeki kod. Bu yönlendirme, uygulama kodunuzda iletilecek yayma üstbilgileri bu kılavuzun önceki adımda gösterildiği gibi gerektirdiğini unutmayın.

## <a name="test-code-in-a-space"></a>Boşluk Testi kodu
Bizim yeni bir sürümü test etmek için `mywebapi` birlikte `webfrontend`, webfrontend genel erişim noktası URL'si tarayıcınızı açın ve hakkında sayfasına gidin. Yeni, ileti görürsünüz.

Şimdi, URL "tan-" bölümünü kaldırın ve tarayıcıyı yenileyin. Eski davranışı görmeniz gerekir (tarafından sergilenen `mywebapi` çalışır durumda sürüm `mainline`).