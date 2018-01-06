---
title: "Yazmaçlar penceresi hakkında | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Registers window, about Registers window
- debugging [Visual Studio], Registers window
ms.assetid: ab354047-053e-4f94-8ac1-26e761442b6f
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 82d8c547885021d83e272bcd3ab1a5d560c73a39
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="about-the-registers-window-in-visual-studio"></a>Visual Studio'da yazmaçlar penceresi hakkında
**Kaydeder** penceredir yalnızca adres düzeyi hata ayıklama içinde etkinse kullanılabilir **seçenekleri** iletişim kutusu, **hata ayıklama** düğümü.  
  
 Yazmaçları işlemci etkin olarak üzerinde çalıştığı veri küçük parçalarını depolamak için kullanılan özel bir işlemci (CPU) içinde yerlerdir. Derleme veya kaynak kodu yorumlama verileri bellekten kaydeder ve geri halinde yeniden taşımak yönergeleri gerektiğinde oluşturur. Yazmaçları verilere sürekli yükleyip yazmaçlar kaldırabileceğini için işlemci gerektirir kodu daha hızlı yürütmek için bir kayıttaki verileri korumak ve sürekli olarak erişmek işlemci veren kod eğilimlidir şekilde bellek, veri erişimi için karşılaştırıldığında çok hızlıdır. Yazmaçları verileri korumak ve diğer en iyi duruma getirme gerçekleştirmek derleyici kolaylaştırmak için genel değişkenler kullanmaktan kaçının ve yerel değişkenlerini mümkün olduğunca gerekir. Bu şekilde yazılan kod başvuru iyi yere göre barındırıyor olarak sınıflandırılır. C/C++ gibi bazı dillerde Programcı değişkeni bir kayıttaki her zaman korumak için en iyi denemek için derleyici bildiren bir kayıt değişkeni bildirebilir. Daha fazla bilgi için bkz: [kaydetmek anahtar sözcüğü](http://msdn.microsoft.com/en-us/5b66905a-2f7f-4918-bb55-5e66d4bc50f9).  
  
 Yazmaçları iki türlerine bölünmüş: genel amaçlı ve özel amaçlı. Genel amaçlı kayıtları iki sayının birlikte ekleme veya bir dizi bir öğe başvurma gibi genel işlemleri verilerini tutun. Özel amaçlı yazmaçlar belirli amaçlar ve özel bir anlamı vardır. Programın çağrı yığını izlemek için işlemci kullanır yığın işaretçisi kayıt buna iyi bir örnektir. Programcı olarak, yığın işaretçisi doğrudan düzenlersiniz olmayabilir. Ancak, yığın işaretçisi işlev çağrısı sonunda geri dönmek nereye işlemci bilmez çünkü uygun programınızı işlevselliği için önemlidir.  
  
 Çoğu genel amaçlı kayıtları yalnızca tek bir veri öğesi tutun. Örneğin, bir tek tamsayı, kayan noktalı sayı veya bir dizi öğesidir. Bazı yeni işlemci küçük bir veri dizisi tutabileceği vektör yazmaçlar adlı büyük kayıtları yok. Çok fazla veri tutmak için vektör yazmaçlar çok hızlı bir şekilde gerçekleştirilecek diziler ilgili işlemler izin verir. Vektör yazmaçlar ilk maliyetli, yüksek performanslı Süper bilgisayarlar üzerinde kullanılan ancak şimdi yoğun grafik işlemlerinde harika avantajı için burada kullanılan mikro kullanılabilir hale gelmektedir.  
  
 Bir işlemci, genellikle bir kayan nokta işlemleri ve diğer tamsayı işlemleri için en iyi duruma getirilmiş genel amaçlı kayıtları iki kümesi vardır. Edilebileceği, bunlar kayan nokta adlandırılır ve tamsayı kaydeder.  
  
 Yönetilen kod çalışma zamanında fiziksel yazmaçlar mikro erişen yerel koda derlenmiş. **Kaydeder** penceresinde ortak dil çalışma zamanı veya yerel koda için fiziksel bu kaydeder. **Kaydeder** penceresi komut dosyası ve SQL yazmaçlar kavramı desteklemeyen dilleri olduğundan komut dosyası veya SQL uygulaması için kayıt bilgileri görüntülemez.  
  
 Görüntüleme hakkında daha fazla bilgi için **kaydeder** penceresinde bkz [kayıtları penceresini kullanarak](../debugger/how-to-use-the-registers-window.md).  
  
 Baktığınızda **kaydeder** penceresinde, bu örnek gibi girişleri görürsünüz:  
  
```  
EAX = 003110D8  
```  
  
 Simgenin = oturum solundaki kayıt EAX, bu durumda adıdır. = Oturum sağındaki sayıya yazmaç içerikleri temsil eder.  
  
 **Kaydeder** penceresi daha fazlasını görünümü bir kaydın içeriğini yapmanıza olanak sağlar. Yerel kodda kesme modunda olduğunda, bir kayıt içeriğine tıklatın ve değeri düzenleyin. Bu şeyin rastgele yapmalısınız değildir. Düzenlemekte olduğunuz kayıt ve raporda bulunan verilere anlamadan dikkatsiz düzenleme sonucunu programın kilitlendiğini veya başka bir istenmeyen sonuç olması olasıdır. Ne yazık ki, çeşitli Intel ve Intel dönük olarak uyumlu işlemci kayıt kümeleri hakkında ayrıntılı bir açıklama kadar bu kısa giriş kapsamı dışındadır gider.  
  
## <a name="register-groups"></a>YAZMAÇ grupları  
 Görünmesine için **kaydeder** penceresi yazmaçlar gruplar halinde düzenler. Üzerinde sağ tıklattığınızda, **kaydeder** penceresini görüntüleme veya gizleme uygun gördüğünüz şekilde gruplarının bir listesini içeren bir kısayol menüsü görürsünüz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: yazmaçlar penceresini kullanma](../debugger/how-to-use-the-registers-window.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)