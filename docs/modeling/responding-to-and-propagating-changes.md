---
title: "Yanıt vermek ve değişiklikleri yayılıyor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, events
ms.assetid: fc2e9ac5-7a84-44ed-9945-94e45f89c227
caps.latest.revision: "24"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 7ea11c018f210b804f4ea6542eb7a7817ae1507c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="responding-to-and-propagating-changes"></a>Değişikliklere Yanıt Verme ve Değişiklikleri Yayma
Bir öğenin oluşturulan, silinmiş veya güncelleştirildiğinde, model diğer bölümleri veya dosyaları, veritabanları veya diğer bileşenleri gibi dış kaynaklara değişikliği yayar kod yazabilirsiniz.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 Bir kılavuz olarak aşağıdaki sırayla bu teknikler göz önünde bulundurun:  
  
|Teknik|Senaryolar|Daha fazla bilgi için|  
|---------------|---------------|--------------------------|  
|Hesaplanan etki alanı özelliği tanımlarsınız.|Değeri modeldeki diğer özelliklerinden hesaplanan bir etki alanı özelliği. Örneğin, ilgili öğeler fiyatlar toplamını olan fiyat.|[Hesaplanan ve özel depolama özellikleri](../modeling/calculated-and-custom-storage-properties.md)|  
|Özel depolama etki alanı özelliği tanımlarsınız.|Diğer bölümlerinde modelinin veya harici olarak depolanan bir etki alanı özelliği. Örneğin, modeldeki bir ağacında bir ifade dizesini ayrıştırma.|[Hesaplanan ve özel depolama özellikleri](../modeling/calculated-and-custom-storage-properties.md)|  
|Geçersiz kılma OnValueChanging ve OnDeleting gibi işleyicileri değiştirme|Farklı öğeler eşit tutmak ve dış değerleri modeli ile eşitlenmiş tutar.<br /><br /> Tanımlanmış aralıklara değerlere kısıtlar.<br /><br /> Hemen önce ve özellik değerini ve diğer değişiklikler sonra çağrılır. Bir özel durum atma tarafından değişiklik sonlandırabilir.|[Etki alanı özellik değeri değişiklik işleyicileri](../modeling/domain-property-value-change-handlers.md)|  
|Kurallar|Bir değişiklik oldu bir işlem sonuna hemen önce yürütme için sıraya alınan kurallar tanımlayabilirsiniz. Bunlar, geri alma veya yineleme yürütülmez. Deponun bir bölümünü başka ile eşitlenmiş tutmak için bunları kullanın.|[Kuralları modelindeki değişiklikleri yaymak](../modeling/rules-propagate-changes-within-the-model.md)|  
|Deposu olayları|Modelleme deposu ekleme veya bir öğe veya bağlantıyı silme veya bir özelliğin değerini değiştirmek gibi olayların bildirimleri sağlar. Olay da geri alma ve yineleme üzerinde yürütülür. Deposu olayları deposunda bulunmayan değerleri güncelleştirmek için kullanın.|[Olay işleyicileri Model dışındaki değişiklikleri yaymak](../modeling/event-handlers-propagate-changes-outside-the-model.md)|  
|.NET olayları|Şekilleri fare tıklamaları ve diğer hareketleri yanıt olay işleyicileri sahiptir. Bu olayların her nesne için kaydolmanız gerekir. Kayıt InitializeInstanceResources bir geçersiz kılma genellikle yapılır ve her öğe için yapılması gerekir.<br /><br /> Bu olaylar, genellikle bir işlemin dışında oluşur.|[Nasıl yapılır: bir şekli veya oluşturma öğesi tıklama müdahale](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md)|  
|Sınırların kuralları|Sınırların kural, özellikle bir şekli sınırlarına sınırlamak için kullanılır.|[BoundsRules şekli konumunu ve boyutunu sınırlamak](../modeling/boundsrules-constrain-shape-location-and-size.md)|  
|Seçim kuralları|Seçim kurallarını özellikle hangi kullanıcı seçebilir kısıtlar.|[Nasıl yapılır: erişmek ve geçerli seçim sınırlamak](../modeling/how-to-access-and-constrain-the-current-selection.md)|  
|OnAssocatedPropertyChanged|Şekiller ve bağlayıcılar gölge, ok uçları, renk ve çizgi genişlikleri ve stil gibi özelliklerini kullanarak model öğelerini durumlarını gösterir.|[Şekiller ve bağlayıcılar modeli yansıtacak şekilde güncelleştirme](../modeling/updating-shapes-and-connectors-to-reflect-the-model.md)|  
  
## <a name="comparing-rules-and-store-events"></a>**Kuralları ve deposu olayları karşılaştırma**  
 Bir modelde değişiklik olduğunda değişiklik notifiers, kuralları ve olayları çalıştırılır.  
  
 Kuralları genellikle değişikliği oluştu son işlem sırasında uygulanır ve olayları bir işlemde değişiklikler kaydedildikten sonra uygulanır.  
  
 Model nesneleri depolama ve kuralları deposundaki tutarlılığını korumak için dışında ile eşitlemek için deposu olayları kullanın.  
  
-   **Özel kurallar oluşturmak** soyut bir kuraldan türetilmiş bir sınıf olarak özel bir kural oluşturun. Ayrıca özel kural hakkındaki framework bildirmeniz gerekir. Daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).  
  
-   **Olaylara abone olma** bir olaya abone olabilmek bir olay işleyicisi ve temsilci oluşturun. Ardından <xref:Microsoft.VisualStudio.Modeling.Store.EventManagerDirectory%2A>olaya abone olmak için özellik. Daha fazla bilgi için bkz: [olay işleyicileri yayılması değişiklikleri dışında modeli](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
-   **Değişiklikleri geri alma** bir işlemi geri almak, olayları başlatılır, ancak kurallar uygulanmaz. Bir kural bir değer değiştirir ve bu değişikliği geri alın, değer geri alma eylemi sırasında orijinal değerine sıfırlanır. Bir olay oluşturulduğunda, özgün değerine değeri el ile değiştirmeniz gerekir. Transactons ve geri alma hakkında daha fazla bilgi için bkz: [nasıl yapılır: kullanım modeli güncelleştirmek için işlemleri](../modeling/how-to-use-transactions-to-update-the-model.md).  
  
-   **Kurallar ve olayları için olay bağımsız değişkenleri geçirme** hem olayları ve kuralları geçirilir bir `EventArgs` modeli hakkında bilgi olan parametre değiştirilmiştir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir şekli veya oluşturma öğesi tıklama müdahale](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md)   
 [Bir etki alanına özgü dil kişiselleştirmek için kod yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)