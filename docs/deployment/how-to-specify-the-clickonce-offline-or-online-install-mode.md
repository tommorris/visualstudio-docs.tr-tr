---
title: 'Nasıl yapılır: ClickOnce çevrimdışı belirtin veya çevrimiçi yükleme modunu | Microsoft Docs'
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
- ClickOnce deployment, specifying install mode
- install mode
- online applications
- offline applications
- ClickOnce install mode
ms.assetid: 0aee5fc1-e966-4bda-9b8f-d9997aeaa779
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 666273ddb251057ede1788747411111f997e5d39
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>Nasıl yapılır: ClickOnce Çevrimdışı veya Çevrimiçi Yükleme Modunu Belirtme
`Install Mode` İçin bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, uygulama çevrimiçi veya çevrimdışı kullanılabilir olup olmayacağını belirler. Seçtiğinizde **uygulama yalnızca çevrimiçi kullanılabilir**, kullanıcı erişimi olmalıdır [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] konumu (bir Web sayfası veya bir dosya paylaşımı) uygulamayı çalıştırmak için yayımlama. Seçtiğinizde **uygulama de çevrimdışı kullanılabilir**, uygulama için girdileri ekler **Başlat** menü ve **Program Ekle veya Kaldır** iletişim kutusu; kullanıcı olduğu Bunlar bağlı olmadığında uygulamayı çalıştırmak kullanabilirsiniz.  
  
 `Install Mode` Ayarlanabilen **Yayımla** sayfasında **Proje Tasarımcısı**.  
  
 **Not** `Install Mode` Yayımlama Sihirbazı'nı kullanarak da ayarlanabilir. Daha fazla bilgi için bkz: [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-make-a-clickonce-application-available-online-only"></a>ClickOnce Uygulama sadece çevrimiçi kullanılabilir yapmak için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  İçinde **yükleme modu ve ayarlar** alanında tıklatın **uygulama yalnızca çevrimiçi kullanılabilir** seçenek düğmesi.  
  
### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>ClickOnce uygulamasını çevrimiçi veya çevrimdışı yapmak için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  İçinde **yükleme modu ve ayarlar** alanında tıklatın **uygulama de çevrimdışı kullanılabilir** seçenek düğmesi.  
  
     Yüklendiğinde uygulama için girdileri ekler **Başlat** menü ve **Program Ekle veya Kaldır** Denetim Masası'nda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [ClickOnce Dağıtım Stratejisini Seçme](../deployment/choosing-a-clickonce-deployment-strategy.md)