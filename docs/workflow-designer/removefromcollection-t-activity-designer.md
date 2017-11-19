---
title: "RemoveFromCollection&lt;T&gt; etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: b792eee528ced288a4073d103286e7b052aa6448
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="removefromcollectionlttgt-activity-designer"></a>RemoveFromCollection&lt;T&gt; etkinlik Tasarımcısı
**RemoveFromCollection\<T >** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.RemoveFromCollection%601> etkinlik.  
  
## <a name="the-removefromcollectiont-activity"></a>RemoveFromCollection < T\> etkinliği  
 <xref:System.Activities.Statements.RemoveFromCollection%601> Etkinlik belirli bir koleksiyondaki belirli bir öğeyi kaldırır.  
  
### <a name="using-the-removefromcollectiont-activity-designer"></a>RemoveFromCollection kullanarak\<T > etkinlik Tasarımcısı  
 **RemoveFromCollection\<T >** etkinlik Tasarımcısı bulunabilir **koleksiyonu** kategorisini **araç**, hangi tıklayarak erişildiğinde **Araç** sekmesi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **RemoveFromCollection\<T >** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.RemoveFromCollection%601> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> RemoveFromCollection, < Int32\>. <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **RemoveFromCollection < T\>**  etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu. Diğer özellikler ve özellik ızgarasının düzenlenmesi gerekir.  
  
### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection < T\> özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.RemoveFromCollection%601> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.Activities.Statements.RemoveFromCollection%601> etkinlik. RemoveFromCollection varsayılandır < Int32\>.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|Doğru|Öğe eklemek için **koleksiyonu\<T >**. Bu öğe türünde *T*, türündeki *TypeArgument*. Öğeyi seçmek için bir Visual Basic ifade özellik kılavuzunda yazın.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|Doğru|Öğesinin eklenmesi koleksiyon. Bu koleksiyonu türünde **ICollection < TypeArgument\>.** Koleksiyon belirtmek için Visual Basic ifade özellik kılavuzunda yazın.|  
|*TypeArgument*|Doğru|İçindeki öğe türü T <xref:System.Collections.Generic.ICollection%601>. Varsayılan olarak, bu *TypeArgument* türü ayarlanmış **Int32**. Türünü değiştirmek için değerini değiştirme *TypeArgument* özellik kılavuzunda açılan kutusunda.|  
|<xref:System.Activities.Activity%601.Result%2A>|False|Belirtilen öğeyi koleksiyondan kaldırıldı olup olmadığını belirten bir değer. Bir değişkende özellik kılavuzunda sonucu bağlamak için bir değişken belirtmek için şunu yazın|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonu](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)   
 [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)