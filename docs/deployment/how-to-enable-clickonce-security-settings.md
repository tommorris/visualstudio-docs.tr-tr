---
title: 'Nasıl yapılır: ClickOnce güvenlik ayarlarını etkinleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- security [Visual Studio], ClickOnce applications
- ClickOnce deployment, security settings
- security settings, ClickOnce deployment
ms.assetid: 73cd3e9d-cd72-4ad2-8cae-94d6bb6b01e0
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 5c59786a49f09efd2dc4d906511ac2602c765c07
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-enable-clickonce-security-settings"></a>Nasıl yapılır: ClickOnce Güvenlik Ayarlarını Etkinleştirme
ClickOnce uygulamaları için kod erişimi güvenliği, uygulama yayımlamak için etkinleştirilmelidir. Yayımlama Sihirbazı'nı kullanarak bir uygulama yayımladığınızda, bu otomatik olarak gerçekleştirilir.  
  
 Bazı durumlarda, kod erişim güvenliği etkinleştirme oluşturma veya uygulamanızın hatalarını ayıklama performansı etkileyebilir; Bu durumlarda, güvenlik ayarlarını geçici olarak devre dışı bırakmak isteyebilir.  
  
 ClickOnce güvenlik ayarlarını etkin veya devre dışı **güvenlik** sayfasında **Proje Tasarımcısı**.  
  
### <a name="to-enable-clickonce-security-settings"></a>ClickOnce güvenlik ayarlarını etkinleştirmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **güvenlik** sekmesi.  
  
3.  Seçin **ClickOnce güvenlik ayarlarını etkinleştir** onay kutusu.  
  
     Şimdi, güvenlik sayfasında uygulamanız için güvenlik ayarlarını özelleştirebilirsiniz.  
  
    > [!NOTE]
    >  Bu onay kutusunu uygulama ile yayımlanır her zaman otomatik olarak seçilir **Yayımla** Sihirbazı.  
  
### <a name="to-disable-clickonce-security-settings"></a>ClickOnce güvenlik ayarlarını devre dışı bırakmak için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **güvenlik** sekmesi.  
  
3.  Clear **ClickOnce güvenlik ayarlarını etkinleştir** onay kutusu.  
  
     Uygulamanızın tam güven güvenlik ayarlarıyla çalışacağı; herhangi bir ayarı **güvenlik** sayfa yok sayılacak.  
  
    > [!NOTE]
    >  Uygulama Yayımla Sihirbazı ile her yayımlandığında, bu onay kutusu seçili; Bunu yeniden her başarılı yayımlamanın ardından temizlemeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce Uygulamaları İçin Kod Erişimi Güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 
