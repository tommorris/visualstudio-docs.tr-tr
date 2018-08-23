---
title: RemoveFromCollection&lt;T&gt; etkinlik Tasarımcısı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 9cb791c64909cf8c494b5c5b3dc481f106dc8cf1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693910"
---
# <a name="removefromcollectionlttgt-activity-designer"></a>RemoveFromCollection&lt;T&gt; etkinlik Tasarımcısı
**RemoveFromCollection\<T >** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.RemoveFromCollection%601> etkinlik.  
  
## <a name="the-removefromcollectiont-activity"></a>RemoveFromCollection\<T > etkinliği  
 <xref:System.Activities.Statements.RemoveFromCollection%601> Etkinlik belirtilen bir öğenin belirli bir koleksiyondan kaldırır.  
  
### <a name="using-the-removefromcollectiont-activity-designer"></a>RemoveFromCollection kullanarak\<T > etkinlik Tasarımcısı  
 **RemoveFromCollection\<T >** etkinlik Tasarımcısı bulunabilir **koleksiyon** kategorisi **araç kutusu**, hangi erişilen tıklayarak **Araç kutusu** sekmesinde [!INCLUDE[wfd2](../includes/wfd2-md.md)] (Alternatif olarak, seçin **araç** gelen **görünümü** menüsünü veya CTRL + ALT + X.)  
  
 **RemoveFromCollection\<T >** etkinlik Tasarımcısı, gelen sürüklenebilir **araç kutusu** ve oturum bırakılan [!INCLUDE[wfd2](../includes/wfd2-md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi içinde bir <xref:System.Activities.Statements.Sequence>. Bu, oluşturur bir <xref:System.Activities.Statements.RemoveFromCollection%601> etkinliği ile bir varsayılan <xref:System.Activities.Activity.DisplayName%2A> RemoveFromCollection,\<Int32 >. <xref:System.Activities.Activity.DisplayName%2A> Değeri üst bilgisinde düzenlenebilir **RemoveFromCollection\<T >** etkinlik Tasarımcısı veya **DisplayName** özellik kılavuzunda kutusu. Özellik Kılavuzu'nun diğer özellikleri düzenlenmesi gerekir.  
  
### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection\<T > Özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.RemoveFromCollection%601> özellikleri Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adı <xref:System.Activities.Statements.RemoveFromCollection%601> etkinlik. RemoveFromCollection varsayılandır\<Int32 >.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kati şekilde gerekli değil kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|Doğru|Eklenecek öğenin **koleksiyon\<T >**. Bu öğe türünde *T*, türünde *TypeArgument*. Öğesini belirtmek için bir Visual Basic ifadesinin özellik kılavuzunda yazın.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|Doğru|Öğesi eklenmesi gereken koleksiyon. Bu koleksiyonu türünde **ICollection\<TypeArgument >.** Koleksiyon belirtmek için bir Visual Basic ifadesinin özellik kılavuzunda yazın.|  
|*TypeArgument*|Doğru|İçindeki öğe türü T <xref:System.Collections.Generic.ICollection%601>. Varsayılan olarak, bu *TypeArgument* türü ayarlandığında **Int32**. Türü değiştirmek için değerini değiştirmek *TypeArgument* birleşik giriş kutusundaki özellik kılavuzunda.|  
|<xref:System.Activities.Activity%601.Result%2A>|False|Belirtilen öğeyi koleksiyondan kaldırılıp kaldırılmadığını belirten bir değer. Sonucu bağlamak için bir değişken olarak belirtmek için bir değişken özellik kılavuzunda yazın|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyon](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)   
 [Existsıncollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)