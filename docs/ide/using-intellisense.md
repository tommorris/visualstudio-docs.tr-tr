---
title: Visual Studio IntelliSense | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-general
ms.topic: article
f1_keywords:
- vc.tools.intellisense
helpviewer_keywords:
- Quick info
- Parameter info
- Complete word
- List members
- IntelliSense [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 88ee47502d0aa15e391155cae918c8e579e72194
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="using-intellisense-in-visual-studio"></a>Visual Studio'da IntelliSense kullanma

IntelliSense; Üyeleri Listeleme, Parametre Bilgisi, Hızlı Bilgi ve Tam Sözcük gibi bir dizi özellik için kullanılan genel bir terimdir. Bu özellikler, yalnızca birkaç tuş vuruşu ile kullandığınız kod hakkında daha fazla bilgi edinmenize, yazmakta olduğunuz parametreleri izlemenize ve özellik ve yöntem çağrıları eklemenize yardımcı olur.

IntelliSense'in birçok yönü dile özgüdür. Farklı diller için IntelliSense hakkında daha fazla bilgi için listelenen konulara bakın [Ayrıca bkz.](#see-also) bölümü.

## <a name="list-members"></a>Üyeleri Listeleme

Bir tetikleyici karakter yazdıktan sonra bir türü (veya ad alanı) geçerli üyeler listesi görüntülenir (örneğin, bir süre (`.`) yönetilen kodda veya `::` C++'ta). Karakterleri yazmaya devam ederseniz, listeye bu karakterlerle başlayan üyeleri içerecek şekilde filtre veya where başlangıcı *herhangi* ad içindeki Word'ü bu karakterlerle başlatır. Eşleşmeleri görmek için üye adı yalnızca başlamalıdır her sözcüğün ilk harfi girebilmeniz için IntelliSense "ortası büyük eşleştirme" de gerçekleştirir.

Bir öğe seçtikten sonra kodunuza tuşlarına basarak eklenebilir **sekmesini** veya boşluk yazarak. Öğeyi seçip bir nokta yazarsanız, bu noktanın arkasında başka üye listesini getiren bir öğe görüntülenir. Bir öğe seçtiğinizde, öğeyi eklemeden önce öğeye ilişkin Hızlı Bilgi alırsınız.

Üye listesinde, soldaki simge ad alanı, sınıf, işlev veya değişken gibi bir üye türünü temsil eder. Simge listesi için bkz [sınıf görünümü ve Nesne Tarayıcısı simgeleri](../ide/class-view-and-object-browser-icons.md). Basabilirsiniz şekilde listesi çok uzun olabilir **PgUp** ve **PgDn** listede yukarı veya aşağı gitme.

![Visual Studio üye listesi](../ide/media/vs2015_intellisense.png "vs2015_Intellisense")

Çağırabilirsiniz **listesi üyeleri** yazarak el ile özellik **CTRL** + **J**, seçme **Düzenle**  >  **IntelliSense** > **listesi üyeleri**, veya seçerek **listesi üyeleri** Düzenleyicisi araç çubuğunda. Boş bir satırda veya tanınabilir bir kapsamın dışında çağrıldığında, bu liste genel ad alanında simgeleri görüntüler.

Üyeleri listeleme (onun özellikle çağrılan sürece görünmemesi için) varsayılan olarak devre dışı bırakmak için Git **Araçları** > **seçenekleri** > **tüm diller**ve seçimini **otomatik listesi üyeleri**. Listesi üyeleri yalnızca belirli bir dil için etkinleştirmek istiyorsanız, Git **genel** o dil için ayarlar.

Sadece yazdığınız metnin kodun içine eklendiği öneri moduna da geçebilirsiniz. Liste ve tuşuna değil bir tanımlayıcı girin, örneğin, **sekmesini**, tamamlanmasında modu giriş yazılan tanımlayıcı değiştirirsiniz. Tamamlanma modu ve öneri modu arasında geçiş yapmak için basın **Ctrl** + **Alt** + **boşluk**, veya seçin **Düzenle**  >  **IntelliSense** > **geçiş tamamlama modu**.

## <a name="parameter-info"></a>Parametre Bilgisi

Parametre Bilgisi; bir yöntem, öznitelik genel tür parametresi (C#) veya şablon (C++) tarafından istenen parametrelerin sayısı, adları ve türleri hakkında bilgi verir.

Kalın yazı tipli parametre, işlevi yazarken gerekli olan bir sonraki parametreyi gösterir. Aşırı yüklenmiş işlevler için, işlev aşırı yüklerine ilişkin alternatif parametre bilgilerini görüntülemek üzere YUKARI ve AŞAĞI ok tuşlarını kullanabilirsiniz.

![Parametre bilgisi](../ide/media/vs2015_param_info.png "VS2015_param_Info")

XML Belgeleri yorumlarıyla işlevlere ve parametrelere ek açıklamalar koyduğunuzda, yorumlar Parametre Bilgisi olarak görüntülenir. Daha fazla bilgi için bkz: [XML kodu açıklamalarını sağlama](../ide/supplying-xml-code-comments.md).

Parametre bilgisi seçerek el ile çalıştırabilirsiniz **Düzenle** > **IntelliSense** > **parametre bilgisi**, basarak **Ctrl**   +  **Shift** + **alanı**, veya seçerek **parametre bilgisi** Düzenleyicisi araç çubuğunda.

## <a name="quick-info"></a>Hızlı Bilgi

Hızlı bilgi kodunuzdaki herhangi bir tanımlayıcı için bütün bildirimi görüntüler.

![Visual Studio hızlı bilgi](../ide/media/vs2015_quick_info.png "VS2015_Quick_info")

Üyeden seçtiğinizde **listesi üyeleri** kutusunda, hızlı bilgi de görünür.

![Parametre bilgisi bir c&#35; kod dosyası](../ide/media/vs2015_paraminfo.png "VS2015_ParamInfo")

Seçerek el ile hızlı bilgi çağırabileceği **Düzenle** > **IntelliSense** > **hızlı bilgi**, basarak **Ctrl**  +  **I**, veya seçerek **hızlı bilgi** Düzenleyicisi araç çubuğunda.

Bir işlev aşırı yüklenmişse, IntelliSense, tüm aşırı yük biçimleri için bilgileri görüntülemeyebilir.

Hızlı bilgi C++ kodunu giderek kapatabilirsiniz **Araçları** > **seçenekleri** > **metin düzenleyici** > **C / C++** > **Gelişmiş**ve ayarı **otomatik hızlı bilgi** için `false`.

## <a name="complete-word"></a>Tam Sözcük

Terim belirsizliğini ortadan kaldırmak için yeterli sayıda karakter girdikten sonra tam sözcüğü bir değişken, komut veya işlev adı kalan tamamlar. Tam sözcük seçerek çağırabileceği **Düzenle** > **IntelliSense** > **tam sözcüğü**, basarak **Ctrl** + **Alanı**, veya seçerek **tam sözcüğü** Düzenleyicisi araç çubuğunda.

## <a name="intellisense-options"></a>IntelliSense Seçenekleri

IntelliSense seçenekleri varsayılan olarak açıktır. Bunları devre dışı bırakmak için seçin **Araçları** > **seçenekleri** > **metin düzenleyici** ve seçimini **parametre bilgilerini**veya **otomatik listesi üyeleri** üyeleri listeleme özelliği istemiyorsanız.

## <a name="troubleshooting-intellisense"></a>IntelliSense Sorunlarını Giderme

IntelliSense seçenekleri, belirli durumlarda beklediğiniz gibi çalışmayabilir.

**İmleç bir kod hatası var.** IntelliSense tamamlanmamış işlevi varsa kullanmanız mümkün olmayabilir veya IntelliSense kod öğeleri ayrıştırabiliyor olmayabileceğinden imleci yukarıdaki kodu başka bir hata bulunmaktadır. Uygulanabilir kodu açıklama olarak ekleyerek bu sorunu çözebilirsiniz.

**İmleç bir kod açıklaması ' dir.** İmleci, kaynak dosyanızdaki açıklamanın ise IntelliSense kullanamazsınız.

**İmleç bir dize sabit değeri var.** İmleç bir aşağıdaki örnekteki değişmez dize değeri tırnak ise IntelliSense kullanamazsınız:

```cpp
MessageBox( hWnd, "String literal|")
```

**Otomatik seçenekleri devre dışı bırakılmıştır.** Varsayılan olarak, IntelliSense otomatik olarak çalışır, ancak devre dışı bırakabilirsiniz. Otomatik deyim tamamlama devre dışı olsa bile, bir IntelliSense özelliğini çağırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md)  
[C# IntelliSense](../ide/visual-csharp-intellisense.md)  
[JavaScript IntelliSense](../ide/javascript-intellisense.md)  
[Kod yazma ve yeniden düzenleme (C++)](/cpp/ide/writing-and-refactoring-code-cpp)  
[XML kodu açıklamalarını sağlama](../ide/supplying-xml-code-comments.md)
