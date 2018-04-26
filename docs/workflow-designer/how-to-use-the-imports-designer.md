---
title: "İş Akışı Tasarımcısı - nasıl yapılır: içeri aktarmalar Tasarımcısı'nı kullanın"
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Presentation.View.ImportDesigner.UI
ms.assetid: 61328ab6-9b66-4e12-8630-22e30ee8c9d1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de974ebba6fbe746a4d7acb4c1a20fefa5488a8e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-the-imports-designer"></a>Nasıl yapılır: içeri aktarmalar Tasarımcısı'nı kullanın

İçeri aktarmalar Tasarımcısı, ifadelerde kullanacağınız türleri için ad alanları girmenizi sağlar. Çok benzer şekilde **alır** veya **kullanarak** Visual Basic ve C içeri aktarmalar Tasarımcısı'nda ad alanları belirtme # dilindeki anahtar sözcükler İfadenizde yerine tam olarak nitelenmiş tür adı girmeniz yeterlidir olanak tanır Sürüm türü adı.

İçeri aktarmalar Tasarımcısı tepki verdiğini hem değişiklikler kullanıcı arabiriminde ve iş akışı kaydedildiğinde yapılan değişiklikler. İş akışı kaydedildikten sonra ad alanları otomatik olarak içeri aktarmalar Designer'a eklenebilir. Bunlar aşağıdakileri içerir:

-   Değişkeni ve bağımsız değişken bildirimlerinde kullanılan türleri için ad alanları.

-   Ad alanları ifadelerinde kullanılan türleri için.

-   İş akışı (örneğin, iş akışında bırakılan özel etkinlikler tarafından kullanılan ad) serileştirmek için gereken bir diğer ad.

 İş akışı kaydedildiğinde, el ile silinmiş bazı ad alanlarının önceki listede açıklanan mantığı nedeniyle otomatik olarak içeri aktarmalar Designer'a yeniden eklenen olduğunu fark edebilirsiniz.

## <a name="to-add-a-namespace-to-the-list-of-imported-namespaces"></a>İçeri aktarılan ad alanları listesine bir ad eklemek için

1.  Bir WCF iş akışı hizmeti uygulaması, iş akışı konsol uygulaması veya etkinlik Kitaplığı projesini Visual Studio 2010 veya rehosted iş akışı uygulaması açın.

2.  Tıklatın **içeri aktarmalar** ana tuvalin altındaki. İçeri aktarmalar Tasarımcısı görünür.

3.  Girin veya bir ad alanı içeri aktarmalar Tasarımcısı üstündeki açılır liste denetimi seçin.

     Siz yazarken, yazılan karakterlerle eşleşen geçerli ad alanlarının listesi görüntülenir.

4.  Tuşuna **Enter** ad listesine eklemek için.

5.  Listeden bir ad alanı kaldırmak istiyorsanız, ad alanını seçin ve sonra basın **silmek** klavyenizde anahtar. Ad herhangi bir nedenle örneğin ad alanını içeren derlemenin projenin artık başvurulmayan varsa geçersiz ise bir ad alanı yalnızca silinebilir olduğunu unutmayın.