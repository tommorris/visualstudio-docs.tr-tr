---
title: "Kural kümesi Düzenleyici iletişim kutusu (eski) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Workflow.Activities.Rules.Design.RuleSetDialog.UI
helpviewer_keywords:
- Rule Set Editor dialog box
ms.assetid: 7cfd5df1-1115-4e5c-9b72-121f39419e83
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 989e0ed3f390513efeb849a71f94d5d61aecc57e
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="rule-set-editor-dialog-box-legacy"></a>Kural kümesi Düzenleyici iletişim kutusu (eski)
Bu konuda açıklanmaktadır kullanma **kural kümesi düzenleyici** eski Windows iş akışı Tasarımcısı'nda iletişim kutusu. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ya da hedeflemek gerektiğinde [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 **Kural kümesi düzenleyici** iletişim kutusu oluşturmak ve değiştirmek için kullanılan [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) kural .rules dosyasına serileştirilmiş ayarlar.

> [!NOTE]
> .Rules dosyasıyla açmak istiyorsanız **kodlamalı XML Düzenleyicisi**, için iş akışı veya etkinlik ilişkili Tasarımcı penceresini kapatın.

 Nasıl erişileceği hakkında bilgi için **kural kümesi düzenleyici** iletişim kutusu, bkz: [nasıl yapılır: bir PolicyActivity kural kümesi (eski) oluşturma](../workflow-designer/how-to-create-a-policyactivity-rule-set-legacy.md).

> [!WARNING]
> Eski kuralları Düzenleyicisi'ni [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ya da hedeflemek için kullanılan [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] çoklu sürüm desteği desteklemiyor.

 Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **kural kümesi düzenleyici** iletişim kutusu.

|Arabirim Öğesi|Açıklama|
|----------------|-----------------|
|**Kural Ekle**|Yeni bir kural tanımı kural kümesine ekler.|
|**Sil**|Seçilen kuralı kural kümesinden siler.|
|**Zincirleme**|Kural kümesi ile kullanmak için İleri zincirleme hangi türünü belirtir. Mevcut seçenekler şunlardır:<br /><br /> -   **Tam zincirleme**, tüm ileriye doğru zincirleme mekanizmaları kullanılacağını belirtir: dolaylı yöntem öznitelik atanıyor ve açık kullanarak bir **güncelleştirme** işlevi.<br />-   **Sıralı**, herhangi bir iletme zincirleme kullanmayacak şekilde belirtir.<br />-   **Yalnızca açık güncelleştirme**, belirten yalnızca üzerinde İleri zincirleme gerçekleştirmek için **güncelleştirme** eylemler.<br /><br /> İletme zincir hakkında daha fazla bilgi için bkz: [PolicyActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65004).|
|**Ad**|Kural listesi sütun başlığını ayarlayın. Kurallar listesinin adına göre sıralamak için tıklatın.|
|**Öncelik**|Kural listesi sütun başlığını ayarlayın. Kurallar listesi önceliğe göre sıralamak için tıklatın.|
|**Yeniden değerlendirme**|Kural listesi sütun başlığını ayarlayın. Kuralları yeniden değerlendirme türe göre sıralamak için tıklatın.|
|**Kural Önizleme**|Kural listesi sütun başlığını ayarlayın. Kurallar listesinin bir kuralın koşul ve eylemleri önizlemesini göre sıralamak için tıklatın.|
|**Ad:**|Kuralın adını girin.|
|**Öncelik:**|Kural için bir öncelik girin. Varsayılan öncelik 0'dır.|
|**Yeniden değerlendirme:**|Kuralıyla kullanmak için kuralı yeniden değerlendirme türünü belirtir. Mevcut seçenekler şunlardır:<br /><br /> -   **Her zaman**, kuralın için gerektiği gibi yeniden değerlendirimiş neden olur.<br />-   **Hiçbir zaman**, kuralın için hiçbir zaman yeniden değerlendirimiş neden olur. Bu durumda bir kural yalnızca bir kez çalıştırılır.|
|**Etkin**|Kural etkin hale getirmek için denetleyin.|
|**Koşul:**|Kural koşulu için bir ifade girin. Deyim sözdizimi hakkında daha fazla bilgi için bu sayfanın "Koşul ve eylem ifadelerinin girilmesi" bölümüne bakın.|
|**Daha sonra eylemler:**|Then ifadesi girin eylemler. Deyim sözdizimi hakkında daha fazla bilgi için bu sayfanın "Koşul ve eylem ifadelerinin girilmesi" bölümüne bakın.|
|**Başka eylemler:**|Else eylemler için ifade girin. Deyim sözdizimi hakkında daha fazla bilgi için bu sayfanın "Koşul ve eylem ifadelerinin girilmesi" bölümüne bakın.|
|**TAMAM**|Kural kümesi .rules dosyasına kaydetmek için tıklatın.|

 Kural kümeleri hakkında daha fazla bilgi için bkz: [PolicyActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65004).

## <a name="entering-condition-and-action-expressions"></a>Koşul ve eylem ifadeleri girme
 Koşul ve ardından için ifadeler girin ve başka eylemler metin olarak kendi ilgili metin kutularındaki **kural kümesi düzenleyici** iletişim kutusu. Yazabilirsiniz **bu.** alanlar, özellikleri ve yöntemleri iş akışı içinde kullanılan başvurmak için düzenleyiciye menüsünün bir IntelliSense türü kullanıyor. Veya doğrudan bir iş akışı üye adı yazın. Statik yöntemler başvurulan türlerinde yöntemi adından sınıf adını yazarak çağırabilirsiniz.

 AND, OR gibi koşul mantıksal işleçler ekleyebilirsiniz ve değil. Koşulları de ekleyebilirsiniz. Bir koşul, ikili işleç ve iki işlenen ' dir. Desteklenen ikili işleçler olan ==, >, \<, > =, ve < =. Desteklenen işlenenler sabit değer, aritmetik işlevi ve kapsamlı Genel Üyeler ' dir.

 Karşılaştırma için türünü belirtebilirsiniz ve'karşılaştırabilirsiniz **null** ya da boş bir dize. Örneğin, bir karmaşık tür içeren bir değişkeni üyelerinde çağrıları geçirebilmenize `this.Address.State == "WA"`.

 İfadeler aşağıdaki işleçleri destekler:

-   İlişkisel işleçleri: ==, =,! =

-   Karşılaştırma işleçleri: <, \<=, >, > =

-   Aritmetik işleçler: +, -, *, /, MOD

-   Mantıksal işleçler: ve, & &, OR &#124; &#124;değil,!

-   Bitwise operators: &, &#124;

 İfade İşleç önceliği C# işleci öncelik kuralları izler.

 Koşullar hakkında daha fazla bilgi için bkz: [kullanan koşulları iş akışlarında](http://msdn.microsoft.com/en-us/541211f5-d382-4810-894f-71f00b34fa77).

### <a name="halt-and-update-functions"></a>Durdurmak ve güncelleştirme işlevleri
 **Daha sonra eylemler:** ve **başka eylemler:** ifadeleri Destek **durdurmak** ve **güncelleştirme** işlevleri. Kullanılacak **durdurmak** işlev, yazın **durdurmak** içine bir **eylemi:** veya **başka eylem:** metin kutusu. **Durdurmak** eylem kural kümesi yürütmenin hemen durmasına neden olur ve denetim çağıran kodu döndürür. Kullandığınız **güncelleştirme** İleri zincirleme ile işlevi.

 Bir **güncelleştirme** deyimi ifade edilir iki forms birinde düzenleyicisinde; her iki forms aşağıdaki örnekte gösterilir:

```
Update(this.Address.State)
Update("this/Address/State")
```

 Kullanma hakkında daha fazla bilgi için **güncelleştirme** iletme zincirleme bkz [PolicyActivity etkinliğini kullanarak](http://go.microsoft.com/fwlink?LinkID=65004).

## <a name="see-also"></a>Ayrıca bkz.

- [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)
- [Kural Kümesi Seç İletişim Kutusu (Eski)](../workflow-designer/select-rule-set-dialog-box-legacy.md)
- [PolicyActivity etkinliğini kullanma](http://go.microsoft.com/fwlink?LinkID=65004)
- [İş akışlarında koşullar kullanma](http://go.microsoft.com/fwlink?LinkID=65009)