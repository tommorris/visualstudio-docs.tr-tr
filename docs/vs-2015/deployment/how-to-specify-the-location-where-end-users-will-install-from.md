---
title: 'Nasıl yapılır: son kullanıcıların yükleme yapacakları konumu belirtme | Microsoft Docs'
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
- deploying applications [ClickOnce], specifying an installation URL
- URLs, specifying an installation URL
- installation, specifying installation an URL
- Installation URL property
ms.assetid: 04a804bf-ed55-4a7a-a1e6-f63ed99c0276
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 68f50fe847d1432292491cd2970c7897eb1388da
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693547"
---
# <a name="how-to-specify-the-location-where-end-users-will-install-from"></a>Nasıl yapılır: Son Kullanıcıların Yükleme Yapacakları Konumu Belirtme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: konum burada son kullanıcıların olacak yükleme belirtmek](https://docs.microsoft.com/visualstudio/deployment/how-to-specify-the-location-where-end-users-will-install-from).  
  
Yayımlama sırasında bir [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] uygulama, kullanıcıların gittikleri uygulamasını indirme ve yükleme için konum değildir nerede başlangıçta yayımladığınız uygulamanın konumu. Örneğin, bazı kuruluşlarda bir geliştirici bir uygulama için bir hazırlık sunucusu yayınlayabilir ve uygulamayı bir Web sunucusuna yönetici ardından taşıyabilir.  
  
 Bu durumda, kullanabileceğiniz `Installation URL` kullanıcıları nereye uygulamayı indirmek için Web sunucusunu belirtmek için özellik. Bu, uygulama bildirimini güncelleştirmeleri aranacağı bilebilmesi gereklidir.  
  
 `Installation URL` Özelliği, üzerinde ayarlanabilir **Yayımla** sayfasının **Proje Tasarımcısı**.  
  
 **Not** `Installation URL` özelliği de ayarlanabilir kullanarak **PublishWizard**. Daha fazla bilgi için [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-specify-an-installation-url"></a>Bir yükleme URL'si belirtmek için  
  
1.  Seçili bir projeyle **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklayın **Yayımla** sekmesi.  
  
3.  Yükleme URL'si biçimi kullanarak tam bir URL kullanarak yükleme konumu alanına http://www.microsoft.com/ApplicationName, ya da UNC yolu biçiminde \\\Server\ApplicationName.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Visual Studio'nun dosyaları nereye kopyalayacağını belirtme](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



