---
title: "Nasıl yapılır: Burada son kullanıcıların yükleme yapacakları konumu belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], specifying an installation URL
- URLs, specifying an installation URL
- installation, specifying installation an URL
- Installation URL property
ms.assetid: 04a804bf-ed55-4a7a-a1e6-f63ed99c0276
caps.latest.revision: "9"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: a3a2770933f4a9f600b12a2d601deca855de3a94
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-location-where-end-users-will-install-from"></a>Nasıl yapılır: Son Kullanıcıların Yükleme Yapacakları Konumu Belirtme
Yayımlama sırasında bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulaması, kullanıcıların gittikleri uygulamayı indirmek ve yüklemek için konum değildir burada başlangıçta yayımladığınız uygulama konumu. Örneğin, bazı kuruluşlarda Geliştirici hazırlama sunucusuna uygulama yayımlama ve ardından Yönetici uygulamayı bir Web sunucusuna taşıyabilir.  
  
 Bu durumda, kullanabileceğiniz `Installation URL` özelliği kullanıcılar nereye uygulamayı indirmek için Web sunucusu belirtin. Uygulama bildirimini güncelleştirme aramak nerede olduğunu bilmesini için bu gereklidir.  
  
 `Installation URL` Özelliği, üzerinde ayarlanabilir **Yayımla** sayfasında **Proje Tasarımcısı**.  
  
 **Not** `Installation URL` özelliği de ayarlanabilir kullanarak **PublishWizard**. Daha fazla bilgi için bkz: [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-specify-an-installation-url"></a>Bir yükleme URL'si belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Yükleme URL'si alanına http://www.microsoft.com/ApplicationName formatını veya biçimi kullanarak bir UNC yolu kullanarak tam bir URL kullanarak yükleme konumu \\\Server\ApplicationName.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Visual Studio dosyaları nereye kopyalayacağını belirtme](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)