---
title: "Nasıl yapılır: ekleme veya içeri aktarılan ad alanlarını (Visual Basic) kaldırma | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding imported namespaces
- removing imported namespaces
- namespaces [Visual Studio], imported
- imported namespaces [Visual Studio]
- references [Visual Studio], imported namespaces
ms.assetid: 44cebec3-0ea0-47c2-8406-4edeab6a997e
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 43947a2e239833459923f6991d4ee54d12876fe3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-or-remove-imported-namespaces-visual-basic"></a>Nasıl Yapılır: İçeri Aktarılan Ad Uzaylarını Ekleme veya Kaldırma (Visual Basic)
Bir ad alanı içe aktarma öğesi tam olarak niteleme olmadan bu ad alanındaki öğeler kodunuzda kullanmanıza olanak sağlar. Erişmek istiyorsanız, örneğin, `Create` yönteminde `System.Messaging.MessageQueue` alabileceğiniz sınıfı, `System.Messaging` ad alanı ve yalnızca gereksinim duyduğunuz kodda öğesine başvuruda `MessageQueue.Create`.  

 İçeri aktarılan ad alanları üzerindeki yönetilen **başvuruları** sayfasında **Proje Tasarımcısı**. Bu iletişim kutusunda belirttiğiniz içeri aktarmalar doğrudan derleyiciye geçirilir (`/imports`) ve projenizdeki tüm dosyalara uygulayabilirsiniz. Kullanmak `Imports` deyimi bir tek kaynak kodu dosyasına bir ad kullanın.  

### <a name="to-add-an-imported-namespace"></a>İçeri aktarılan ad eklemek için  

1.  İçinde **Çözüm Gezgini**, çift **My proje** projesi için düğüm.  

2.  İçinde **Proje Tasarımcısı**, tıklatın **başvuruları** sekmesi.  

3.  İçinde **içeri aktarılan ad alanları** listesinde, eklemek istediğiniz ad alanı için onay kutusunu seçin.  

    > [!NOTE]
    >  Alınmak için ad alanı başvurulan bir bileşenin olması gerekir. Ad alanı listede görünmüyorsa, içerdiği bileşenine bir başvuru eklemeniz gerekir. Daha fazla bilgi için bkz: [bir projedeki başvuruları yönetme](managing-references-in-a-project.md).  
  
### <a name="to-remove-an-imported-namespace"></a>İçeri aktarılan ad alanını kaldırmak için  

1.  İçinde **Çözüm Gezgini**, çift **My proje** projesi için düğüm.  

2.  İçinde **Proje Tasarımcısı**, tıklatın **başvuruları** sekmesi.  

3.  İçinde **içeri aktarılan ad alanları** listesinde, kaldırmak istediğiniz ad alanı için onay kutusunu temizleyin.  

## <a name="user-imports"></a>Kullanıcı içeri aktarmalar  
 Kullanıcı içeri aktarmalar, belirli bir sınıfın tüm ad alanı yerine bir ad alanı içinde almaya izin verir. Örneğin, uygulamanız için alma olabilir `Systems.Diagnostics` ad alanı, ancak ilgilendiğiniz bu ad alanındaki tek sınıf `Debug` sınıfı. Tanımlayabileceğiniz `System.Diagnostics.Debug` bir kullanıcı olarak içeri aktarma ve alma için Kaldır'ı `System.Diagnostics`.  

 Daha sonra fikir değiştirirseniz ve yalnızca karar verirseniz, gerçekten `EventLog` girin, gerekli sınıfı, `System.Diagnostics.EventLog` bir kullanıcı olarak alma ve üzerine yazma `System.Diagnostics.Debug` güncelleştirme işlevini kullanarak.  

#### <a name="to-add-a-user-import"></a>Bir kullanıcı alma eklemek için  

1.  İçinde **Çözüm Gezgini**, çift **My proje** projesi için düğüm.  

2.  İçinde **Proje Tasarımcısı**, tıklatın **başvuruları** sekmesi.  

3.  Aşağıdaki metin kutusundaki **içeri aktarılan ad alanları** listesinde, kök ad alanı dahil almak istediğiniz ad alanı için tam bir ad girin.  

4.  Tıklatın **kullanıcı alma ekleme** ad alanına eklemek için düğmeyi **içeri aktarılan ad alanları** listesi.  

    > [!NOTE]
    >  **Kullanıcı alma ekleme** düğmesi devre dışı bırakılacak ad alanı zaten listeden birini eşleşirse; bir alma işlemi iki kez eklenemiyor.  

#### <a name="to-update-a-user-import"></a>Bir kullanıcı alma güncelleştirmek için  

1.  İçinde **Çözüm Gezgini**, çift **My proje** projesi için düğüm.  

2.  İçinde **Proje Tasarımcısı**, tıklatın **başvuruları** sekmesi.  

3.  İçinde **içeri aktarılan ad alanları** listesinde, değiştirmek istediğiniz ad alanını seçin.  

4.  Aşağıdaki metin kutusundaki **içeri aktarılan ad alanları** listesinde, yeni ad alanı için bir ad girin.  

5.  Tıklatın **güncelleştirme kullanıcı alma** ad alanını güncelleştirmek için düğmesini **içeri aktarılan ad alanları** listesi.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md)
