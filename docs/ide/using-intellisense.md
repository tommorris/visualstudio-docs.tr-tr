---
title: IntelliSense kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.tools.intellisense
helpviewer_keywords:
- IntelliSense, Complete Word
- IntelliSense, completion mode
- parameter information
- IntelliSense, List Members
- Quick Info
- Parameter Info
- IntelliSense [Visual Studio]
- IntelliSense, suggestion mode
- IntelliSense, Parameter Info
- IntelliSense, customizing
- Complete Word
- IntelliSense
- List Members
ms.assetid: 9fdb489b-8b46-4b92-9ccc-c8f8cc184081
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 149cb62f35ce4b1ce15ab939a0805bc63bfb6f26
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="using-intellisense"></a>IntelliSense Kullanma
IntelliSense; Üyeleri Listeleme, Parametre Bilgisi, Hızlı Bilgi ve Tam Sözcük gibi bir dizi özellik için kullanılan genel bir terimdir. Bu özellikler, yalnızca birkaç tuş vuruşu ile kullandığınız kod hakkında daha fazla bilgi edinmenize, yazmakta olduğunuz parametreleri izlemenize ve özellik ve yöntem çağrıları eklemenize yardımcı olur.  
  
 IntelliSense'in birçok yönü dile özgüdür. Farklı dillere yönelik IntelliSense hakkında daha fazla bilgi için Ayrıca Bkz. altında listelenen konulara bakın.  
  
## <a name="list-members"></a>Üyeleri Listeleme  
 Bir tetikleyici karakter yazdıktan sonra bir türü (veya ad alanı) geçerli üyeler listesi görüntülenir (örneğin, bir süre (`.`) yönetilen kodda veya `::` C++'ta). Karakterleri yazmaya devam ederseniz, listeye bu karakterlerle başlayan üyeleri içerecek şekilde filtre veya where başlangıcı *herhangi* ad içindeki Word'ü bu karakterlerle başlatır. Eşleşmeleri görmek için üye adı yalnızca başlamalıdır her sözcüğün ilk harfi girebilmeniz için IntelliSense "ortası büyük eşleştirme" de gerçekleştirir.   
  
 Bir öğeyi seçtikten sonra SEKME tuşuna basarak veya bir boşluk girerek öğeyi kodunuza ekleyebilirsiniz. Öğeyi seçip bir nokta yazarsanız, bu noktanın arkasında başka üye listesini getiren bir öğe görüntülenir. Bir öğe seçtiğinizde, öğeyi eklemeden önce öğeye ilişkin Hızlı Bilgi alırsınız.  
  
 Üye listesinde, soldaki simge ad alanı, sınıf, işlev veya değişken gibi bir üye türünü temsil eder. Simge listesi için bkz [sınıf görünümü ve Nesne Tarayıcısı simgeleri](../ide/class-view-and-object-browser-icons.md). Liste oldukça uzun olabilir; bu yüzden listede yukarı veya aşağı gitmek için PAGE UP ve PAGE DOWN tuşlarına basabilirsiniz.  
  
 ![Visual Studio üye listesi](../ide/media/vs2015_intellisense.png "vs2015_Intellisense")  
  
 Çağırabilirsiniz **listesi üyeleri** CTRL + J tıklatarak yazarak el ile özellik **IntelliSense/düzenleme/listesi üyeleri**, veya tıklatarak **listesi üyeleri** Düzenleyicisi düğmesine araç çubuğu. Boş bir satırda veya tanınabilir bir kapsamın dışında çağrıldığında, bu liste genel ad alanında simgeleri görüntüler.  
  
 Üyeleri listeleme (onun özellikle çağrılan sürece görünmemesi için) varsayılan olarak devre dışı bırakmak için Git **Araçlar/Seçenekler/tüm diller** ve seçimini kaldırmak **otomatik listesi üyeleri**. Listesi üyeleri yalnızca belirli bir dil için etkinleştirmek istiyorsanız, Git **genel** o dil için ayarlar.  
  
 Sadece yazdığınız metnin kodun içine eklendiği öneri moduna da geçebilirsiniz. Örneğin, listede olmayan bir tanımlayıcı girip SEKME tuşuna basarsanız, tamamlama modunda bu giriş yazılan tanımlayıcının yerini alır. Tamamlanma modu ve öneri modu arasında geçiş yapmak için CTRL + ALT + ARA ÇUBUĞU tuşlarına basın veya **tamamlama modunu IntelliSense/düzenleme/Değiştir**.  
  
## <a name="parameter-info"></a>Parametre Bilgisi  
 Parametre Bilgisi; bir yöntem, öznitelik genel tür parametresi (C#) veya şablon (C++) tarafından istenen parametrelerin sayısı, adları ve türleri hakkında bilgi verir.  
  
 Kalın yazı tipli parametre, işlevi yazarken gerekli olan bir sonraki parametreyi gösterir. Aşırı yüklenmiş işlevler için, işlev aşırı yüklerine ilişkin alternatif parametre bilgilerini görüntülemek üzere YUKARI ve AŞAĞI ok tuşlarını kullanabilirsiniz.  
  
 ![Parametre bilgisi](../ide/media/vs2015_param_info.png "VS2015_param_Info")  
  
 XML Belgeleri yorumlarıyla işlevlere ve parametrelere ek açıklamalar koyduğunuzda, yorumlar Parametre Bilgisi olarak görüntülenir. Daha fazla bilgi için bkz: [XML kodu açıklamalarını sağlama](../ide/supplying-xml-code-comments.md).  
  
 Parametre bilgisi tıklayarak el ile çalıştırabilirsiniz **IntelliSense/parametre bilgi Düzenle**CTRL + SHIFT + Ara çubuğu yazarak veya tıklatarak **parametre bilgisi** Düzenleyicisi araç çubuğunda.  
  
## <a name="quick-info"></a>Hızlı Bilgi  
 Hızlı bilgi kodunuzdaki herhangi bir tanımlayıcı için bütün bildirimi görüntüler.  
  
 ![Visual Studio hızlı bilgi](../ide/media/vs2015_quick_info.png "VS2015_Quick_info")  
  
 Üyeden seçtiğinizde **listesi üyeleri** kutusunda, hızlı bilgi de görünür.  
  
 ![Parametre bilgisi C &#35; kod dosyası](../ide/media/vs2015_paraminfo.png "VS2015_ParamInfo")  
  
 Tıklayarak el ile hızlı bilgi çağırabileceği **IntelliSense/düzenleme/hızlı bilgi**yazarak CTRL + g veya tıklatarak **hızlı bilgi** Düzenleyicisi araç çubuğunda.  
  
 Bir işlev aşırı yüklenmişse, IntelliSense, tüm aşırı yük biçimleri için bilgileri görüntülemeyebilir.  
  
 C++ içinde kapalı hızlı bilgi ayarlayarak etkinleştirebilirsiniz **Araçlar / Seçenekler / metin düzenleyici/C/C + +/ Gelişmiş/otomatik hızlı bilgi** için `false`.  
  
## <a name="complete-word"></a>Tam Sözcük  
 Tam Sözcük, terim belirsizliğini ortadan kaldıracak yeterli sayıda karakter girdikten sonra değişken, komut veya işlev adının kalanını tamamlar. Tam sözcük tıklayarak çağırabileceği **IntelliSense/düzenleme/tamamlandı Word**CTRL + Ara çubuğu yazarak veya tıklatarak **tam sözcüğü** Düzenleyicisi araç çubuğunda.  
  
## <a name="intellisense-options"></a>IntelliSense Seçenekleri  
 IntelliSense seçenekleri varsayılan olarak açıktır. Bunları devre dışı bırakmak için tıklatın **Araçlar/Seçenekler/Metin Düzenleyicisi** ve seçimini kaldırmak **parametre bilgilerini** veya **otomatik listesi üyeleri** üyeleri listeleme özelliği istemiyorsanız.  
  
## <a name="troubleshooting-intellisense"></a>IntelliSense Sorunlarını Giderme  
 IntelliSense seçenekleri, belirli durumlarda beklediğiniz gibi çalışmayabilir.  
  
 **İmleç bir kod hatası var.** IntelliSense tamamlanmamış işlevi varsa kullanmanız mümkün olmayabilir veya IntelliSense kod öğeleri ayrıştırabiliyor olmayabileceğinden imleci yukarıdaki kodu başka bir hata bulunmaktadır. Uygulanabilir kodu açıklama olarak ekleyerek bu sorunu çözebilirsiniz.  
  
 **İmleç bir kod açıklaması ' dir.** İmleci, kaynak dosyanızdaki açıklamanın ise IntelliSense kullanamazsınız.  
  
 **İmleç bir dize sabit değeri var.** İmleç bir aşağıdaki örnekteki değişmez dize değeri tırnak ise IntelliSense kullanamazsınız:  
  
```  
MessageBox( hWnd, "String literal|")
```  
  
 **Otomatik seçenekleri devre dışı bırakılmıştır.** Varsayılan olarak, IntelliSense otomatik olarak çalışır, ancak devre dışı bırakabilirsiniz. Otomatik deyim tamamlama devre dışı olsa bile, bir IntelliSense özelliğini çağırabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic'e özel IntelliSense](../ide/visual-basic-specific-intellisense.md)   
 [Visual C# IntelliSense](../ide/visual-csharp-intellisense.md)   
 [JavaScript IntelliSense](../ide/javascript-intellisense.md)   
 [XML kodu açıklamalarını sağlama](../ide/supplying-xml-code-comments.md)
