---
title: 'Nasıl yapılır: Burada son kullanıcıların yükleme yapacakları konumu belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0152cf6b03f2e089ee8633ef4abae9043e41bc24
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31559601"
---
# <a name="how-to-specify-the-location-where-end-users-will-install-from"></a>Nasıl yapılır: Son Kullanıcıların Yükleme Yapacakları Konumu Belirtme
Yayımlama sırasında bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulaması, kullanıcıların gittikleri uygulamayı indirmek ve yüklemek için konum değildir burada başlangıçta yayımladığınız uygulama konumu. Örneğin, bazı kuruluşlarda Geliştirici hazırlama sunucusuna uygulama yayımlama ve ardından Yönetici uygulamayı bir Web sunucusuna taşıyabilir.  
  
 Bu durumda, kullanabileceğiniz `Installation URL` özelliği kullanıcılar nereye uygulamayı indirmek için Web sunucusu belirtin. Uygulama bildirimini güncelleştirme aramak nerede olduğunu bilmesini için bu gereklidir.  
  
 `Installation URL` Özelliği, üzerinde ayarlanabilir **Yayımla** sayfasında **Proje Tasarımcısı**.  
  
 **Not** `Installation URL` özelliği de ayarlanabilir kullanarak **PublishWizard**. Daha fazla bilgi için bkz: [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-specify-an-installation-url"></a>Bir yükleme URL'si belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Yükleme URL'si alanına biçimini kullanarak tam bir URL kullanarak yükleme konumu http://www.microsoft.com/ApplicationName, ya da aşağıdaki biçimi kullanarak bir UNC yolu \\\Server\ApplicationName.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Visual Studio dosyaları nereye kopyalayacağını belirtme](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)