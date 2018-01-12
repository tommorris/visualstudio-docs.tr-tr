---
title: "Nasıl yapılır: bir özelliği yerelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- features [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1ddb5e705fd581ce2717539ac6daf3e9a2081f6d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-localize-a-feature"></a>Nasıl yapılır: Bir Özelliği Yerelleştirme
  Varsayılan olarak, özellik başlıkları ve açıklamaları sabit kodlanmış dize değerlerini kullanın. Özellik başlığı ve açıklamayı yerelleştirme için yerelleştirilmiş kaynaklar başvuru ifadelerle dizeleri değiştirin.  
  
## <a name="localizing-a-feature"></a>Bir özelliği yerelleştirme  
  
#### <a name="to-localize-a-feature"></a>Bir özelliği yerelleştirme için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **Feature1** düğümünü ve ardından **özelliği kaynak ekleme**.  
  
2.  İçinde **kaynak ekleme** iletişim kutusunda, seçin **sabit dil** kültürü için varsayılan dili özelliği kaynak dosyası olarak listeden.  
  
3.  Kaynak dosyaları yerelleştirilmiş özellik için tercih ettiğiniz dillerini seçme yerelleştirilmiş her dil için önceki adımı yineleyin.  
  
     Ayrı bir özellik kaynak dosyaları oluşturulur: varsayılan dil için bir tane ve her bir yerelleştirilmiş desteklemek istediğiniz dili.  
  
4.  Her kaynak dosyasını kaynak düzenleyicisinde açın ve tüm dize kimlikleri ve bunların değerleri girin.  
  
     Örneğin, varsayılan özellik kaynak dosyasında bir dize kimliği girin **başlık** değerini **My özellik başlığı**, ve ikinci bir dize Kimliğini **açıklama** değerini **My özellik açıklaması**. Her bir yerelleştirilmiş kaynak dosya için varsayılan özellik kaynak kullanılan kimlikleri aynı dizeyi kullanın, ancak yerelleştirilmiş dizeleri için değerleri girin.  
  
5.  Tüm kaynak değerleri girdikten sonra (örneğin, Feature1.feature) özelliği için kısayol menüsünü açın ve ardından **Görünüm Tasarımcısı** özellik Tasarımcısı'nda özelliğini açmak için.  
  
6.  Yerelleştirme için **başlık** ve **açıklama** özelliği alanlarında kendi kutularına değerleri girmek için aşağıdaki biçimi kullanın:  
  
     `$Resources:`*Dize kimliği*  
  
     $Resources örneğin:**başlık** içinde **özellik başlığı** kutusu ve $Resources:**açıklama** içinde **özellik açıklaması** kutusu .  
  
     Kimlik dizesi kaynak dosyalarında kullanılan eşleşmelidir.  
  
7.  Derleme ve uygulamayı çalıştırmak için F5 tuşuna seçin.  
  
8.  SharePoint'te açmak **Site eylemleri** menüsünde seçin **Site Ayarları**ve ardından **Site eylemleri** bölümü seçin **Site özellikleriyönetme** bağlantı.  
  
9. SharePoint'te varsayılandan görüntüleme dilini değiştirin.  
  
     Yerelleştirilmiş özellik başlığı ve açıklamayı uygulamada görüntülenir. Yerelleştirilmiş kaynakları görüntülemek için SharePoint sunucusu kaynak dosyanın kültür eşleşen bir dil paketi olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Çözümlerini Yerelleştirme](../sharepoint/localizing-sharepoint-solutions.md)   
 [Nasıl yapılır: kaynak dosyası ekleme](../sharepoint/how-to-add-a-resource-file.md)   
 [Nasıl yapılır: ASPX biçimlendirmesini yerelleştirme](../sharepoint/how-to-localize-aspx-markup.md)   
 [Nasıl yapılır: Kod Yerelleştirme](../sharepoint/how-to-localize-code.md)  
  
  