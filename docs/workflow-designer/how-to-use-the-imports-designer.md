---
title: "Nasıl yapılır: içeri aktarmalar Tasarımcısı'nı kullanın | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ImportDesigner.UI
ms.assetid: 61328ab6-9b66-4e12-8630-22e30ee8c9d1
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3980b43b090a0a6321ee0133e2c0ad4f5cbbffde
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-use-the-imports-designer"></a>Nasıl yapılır: içeri aktarmalar Tasarımcısı'nı kullanın
İçeri aktarmalar Tasarımcısı, ifadelerde kullanacağınız türleri için ad alanları girmenizi sağlar. Çok benzer şekilde **alır** veya **kullanarak** Visual Basic ve C içeri aktarmalar Tasarımcısı'nda ad alanları belirtme # dilindeki anahtar sözcükler İfadenizde yerine tam olarak nitelenmiş tür adı girmeniz yeterlidir olanak tanır Sürüm türü adı.  
  
 İçeri aktarmalar Tasarımcısı tepki verdiğini hem değişiklikler kullanıcı arabiriminde ve iş akışı kaydedildiğinde yapılan değişiklikler. İş akışı kaydedildikten sonra ad alanları otomatik olarak içeri aktarmalar Designer'a eklenebilir. Bunlar aşağıdakileri içerir:  
  
-   Değişkeni ve bağımsız değişken bildirimlerinde kullanılan türleri için ad alanları.  
  
-   Ad alanları ifadelerinde kullanılan türleri için.  
  
-   İş akışı (örneğin, iş akışında bırakılan özel etkinlikler tarafından kullanılan ad) serileştirmek için gereken bir diğer ad.  
  
 İş akışı kaydedildiğinde, el ile silinmiş bazı ad alanlarının önceki listede açıklanan mantığı nedeniyle otomatik olarak içeri aktarmalar Designer'a yeniden eklenen olduğunu fark edebilirsiniz.  
  
### <a name="to-add-a-namespace-to-the-list-of-imported-namespaces"></a>İçeri aktarılan ad alanları listesine bir ad eklemek için  
  
1.  Bir WCF iş akışı hizmeti uygulaması, iş akışı konsol uygulaması veya etkinlik kitaplığı projesinde açın [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] veya rehosted iş akışı uygulaması.  
  
2.  Tıklatın **içeri aktarmalar** ana tuvalin altındaki. İçeri aktarmalar Tasarımcısı görünür.  
  
3.  Girin veya bir ad alanı içeri aktarmalar Tasarımcısı üstündeki açılır liste denetimi seçin.  
  
     Siz yazarken, yazılan karakterlerle eşleşen geçerli ad alanlarının listesi görüntülenir.  
  
4.  Tuşuna **Enter** ad listesine eklemek için.  
  
5.  Listeden bir ad alanı kaldırmak istiyorsanız, ad alanını seçin ve sonra basın **silmek** klavyenizde anahtar. Ad herhangi bir nedenle örneğin ad alanını içeren derlemenin projenin artık başvurulmayan varsa geçersiz ise bir ad alanı yalnızca silinebilir olduğunu unutmayın.