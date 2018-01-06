---
title: "ExistsInCollection&lt;T&gt; etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.ExistsInCollection`1.UI
ms.assetid: 0acf9a13-caf5-4bb4-ba22-ec37d2b7267a
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: bcd3028335ed48f4eba8c647f124d0d537deaf3c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="existsincollectionlttgt-activity-designer"></a>ExistsInCollection&lt;T&gt; etkinlik Tasarımcısı
**ExistsInCollection\<T >** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.ExistsInCollection%601> etkinlik.  
  
## <a name="the-existsincollectiont-activity"></a>ExistsInCollection < T\> etkinliği  
 <xref:System.Activities.Statements.ExistsInCollection%601> Etkinlik belirli bir öğeyi belirli bir koleksiyondaki var olup olmadığını belirler.  
  
### <a name="using-the-existsincollectiont-activity-designer"></a>ExistsInCollection kullanarak\<T > etkinlik Tasarımcısı  
 **ExistsInCollection\<T >** etkinlik Tasarımcısı bulunabilir **koleksiyonu** kategorisini **araç**, hangi tıklayarakerişildiğinde **Araç kutusu** sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **ExistsInCollection\<T >** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.ExistsInCollection%601> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> ExistsInCollection, < Int32\>. (Varsayılan olarak, *TypeArgument* olan **Int32**. Bu özellik kılavuzunda değiştirilebilir.)  <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **ExistsInCollection < T\>**  etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu. Diğer özellikler ve özellik ızgarasının düzenlenmesi gerekir.  
  
### <a name="the-existsincollectiont-properties"></a>ExistsInCollection < T\> özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.ExistsInCollection%601> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.ExistsInCollection%601> etkinlik. ExistsInCollection varsayılandır < Int32\>. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.ExistsInCollection%601.Item%2A>|Doğru|Koleksiyona eklenecek öğe\<T >. Bu öğe türünde *T* türü *TypeArgument*. Öğeyi seçmek için özellik kılavuzunda bir Visual Basic ifadesi yazın.|  
|<xref:System.Activities.Statements.ExistsInCollection%601.Collection%2A>|Doğru|Öğesinin eklenmesi koleksiyon. Bu koleksiyonu türünde **ICollection < TypeArgument\>.** Koleksiyon belirtmek için özellik kılavuzunda bir Visual Basic ifadesi yazın.|  
|*TypeArgument*|Doğru|İçindeki öğe türü T <xref:System.Collections.Generic.ICollection%601>. Varsayılan olarak, bu *TypeArgument* türü ayarlanmış **Int32**. Türünü değiştirmek için değerini değiştirme *TypeArgument* özellik kılavuzunda açılan kutusunda.|  
|<xref:System.Activities.Activity%601.Result%2A>|False|Belirtilen öğe koleksiyonunda var olup olmadığını belirten bir değer. Sonucu bağlamak için bir değişken belirtmek için bir Visual Basic değişken özellik kılavuzunda yazın.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonu](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)   
 [RemoveFromCollection\<T >](../workflow-designer/removefromcollection-t-activity-designer.md)