---
title: "Proje bağlam | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: projects [Visual Studio SDK], opening items
ms.assetid: d1803f4a-24eb-44b0-b5d2-cb40c15534be
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 368f6ecb67bc8b01df975da6e68e95b553a0e31d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="project-context"></a>Proje bağlamı
Kullanıcı ekler veya projeleri ve proje öğeleri ile çalışır, IDE proje bağlamı kavramı nasıl çeşitli işlemleri yapılması gerektiğini belirlemek için kullanır.  
  
 Genellikle, dosyaları seçerek kullanıcı açıkça oluşturan standart proje nesneleridir **yeni proje** komut veya seçerek kullanılabilir hale getirir **Proje Aç** komutunu  **Dosya** menüsü. Bu durumda, dosyaları oluşturulur ve bir proje bağlamında açılır ve proje türüne belge düzenlenmek bağlamı tanımlar.  
  
 Bazı projeler çok zengin bir bağlam sağlar. Örneğin, bir proje kapsamı, programlı ad alanı veya veri bağlama için Proje kapsamlı veritabanı bağlantısı proje yönetir. Kullanıcının sık dosyaları veya veritabanı bağlantılarını doğrudan Çözüm Gezgini'nde görüntülenen bir proje öğesi gibi bir projedeki nesnesi kullanarak açabilirsiniz.  
  
 Diğer saatlerde öğeyi proje bağlamında açıkça belirtilmedi. Seçerek kullanıcı bir dosyayı açtığında, örneğin, bir öğenin bağlam kullanılamıyor **açık varolan dosyayı** komutunu **dosya** hata ayıklayıcı bir dosyada veya kullanıcı tıklattığında çalıştığında menüsünde. **Dosyaları bulmak** komutunu **bulma ve değiştirme** iletişim kutusu. Bu durumlarda, IDE çağrıları işlemek için <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument> bir belgeyi açmak için en iyi proje bulma işlemini yönetmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje önceliği](../../extensibility/internals/project-priority.md)   
 [Proje ve proje öğesi şablonları ekleme](../../extensibility/internals/adding-project-and-project-item-templates.md)