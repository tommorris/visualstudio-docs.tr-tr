---
title: 'Nasıl yapılır: ClickOnce güvenlik ayarlarını etkinleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- security [Visual Studio], ClickOnce applications
- ClickOnce deployment, security settings
- security settings, ClickOnce deployment
ms.assetid: 73cd3e9d-cd72-4ad2-8cae-94d6bb6b01e0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 65cba913afdee2379e5f702dda460cea2a33598f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634135"
---
# <a name="how-to-enable-clickonce-security-settings"></a>Nasıl yapılır: ClickOnce Güvenlik Ayarlarını Etkinleştirme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: ClickOnce güvenlik ayarlarını etkinleştirme](https://docs.microsoft.com/visualstudio/deployment/how-to-enable-clickonce-security-settings).  
  
ClickOnce uygulamaları için kod erişimi güvenliği, uygulama yayımlamak için etkinleştirilmesi gerekir. Yayımlama Sihirbazı'nı kullanarak bir uygulama yayımladığınızda, bu otomatik olarak gerçekleştirilir.  
  
 Bazı durumlarda, kod erişim güvenliği etkinleştirme oluşturma veya uygulamanızı hata ayıklama performansı etkileyebilir; Bu durumlarda, güvenlik ayarlarını geçici olarak devre dışı bırakmak isteyebilir.  
  
 ClickOnce güvenlik ayarlarını etkinleştirilebilir veya devre dışı **güvenlik** sayfasının **Proje Tasarımcısı**.  
  
### <a name="to-enable-clickonce-security-settings"></a>ClickOnce güvenlik ayarlarını etkinleştirme  
  
1.  Seçili bir projeyle **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklayın **güvenlik** sekmesi.  
  
3.  Seçin **ClickOnce güvenlik ayarlarını etkinleştirme** onay kutusu.  
  
     Ayrıca, uygulamanızın Güvenlik sayfasında artık güvenlik ayarlarını özelleştirebilirsiniz.  
  
    > [!NOTE]
    >  Bu onay kutusu ile uygulamanın yayımlandığı her zaman otomatik olarak seçilen **Yayımla** Sihirbazı.  
  
### <a name="to-disable-clickonce-security-settings"></a>ClickOnce güvenlik ayarlarını devre dışı bırakmak için  
  
1.  Seçili bir projeyle **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklayın **güvenlik** sekmesi.  
  
3.  NET **ClickOnce güvenlik ayarlarını etkinleştirme** onay kutusu.  
  
     Uygulama tam güven güvenlik ayarlarıyla çalışır; herhangi bir ayarı **güvenlik** sayfa yok sayılacak.  
  
    > [!NOTE]
    >  Uygulama Yayımlama Sihirbazı kullanarak, her yayımlandığında, bu onay kutusu işaretli; yeniden başarılı her yayımlamadan sonra temizlemelisiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce Uygulamalarının Güvenliğini Sağlama](../deployment/securing-clickonce-applications.md)



