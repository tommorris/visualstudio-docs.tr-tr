---
title: 'Nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama | Microsoft Docs'
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
- debugging [Visual Studio], ClickOnce applications
- ClickOnce deployment, debugging
- ClickOnce applications, debugging
ms.assetid: 6991ea91-5253-451b-923d-22273a3d38b1
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: adb1b3cff76cb22e54ddb5e89c714983afa3a167
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-a-clickonce-application-with-restricted-permissions"></a>Nasıl yapılır: Sınırlı İzinler ile ClickOnce Uygulamasında Hata Ayıklama
Bir geliştirici olarak, büyük olasılıkla son kullanıcı kısıtlı izinlerle çalıştırırken görebileceği bir ClickOnce uygulamasında hata ayıklarken aynı güvenlik özel durumları görmezsiniz şekilde geliştirme bilgisayarınıza tam güven izinleri ile çalışıyor.  
  
 Bu özel durumları yakalamak için son kullanıcı ile aynı izinlerle uygulamada hata ayıklama gerekir. Kısıtlı izinlerle hata ayıklama etkinleştirilebilir **güvenlik** sayfasında **Proje Tasarımcısı**.  
  
 Ayrıca, bu Web Hizmetleri, genellikle Web Hizmetleri çağıran uygulamalar geliştirirken, geliştirme bilgisayarınızda bulunur. Uygulama dağıtıldıktan sonra son kullanıcı farklı bir URL bu Web hizmetlerine erişin. Hata ayıklama sırasında son kullanıcı deneyimi benzetmek için bu URL'den çağrılan gibi bir URL ve hata ayıklayıcısı Web Hizmetleri değerlendirir belirtebilirsiniz.  
  
### <a name="to-enable-debugging-with-restricted-permissions"></a>Kısıtlı izinlerle hata ayıklamayı etkinleştirmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  İçinde **Proje Tasarımcısı**, tıklatın **güvenlik** sekmesi.  
  
3.  Seçin **ClickOnce güvenlik ayarını etkinleştir** onay kutusunu işaretleyin ve ardından **kısmi güven uygulamasıdır** seçenek düğmesi.  
  
4.  Tıklatın **Gelişmiş** düğmesi.  
  
5.  Seçin **seçili izin kümesi ile bu uygulamanın hatalarını ayıklama** onay kutusunu işaretleyin ve ardından **Tamam**.  
  
     Uygulama hata ayıklama işlemi yaparken, erişim izni kümesinin parçası olmayan bir izni girişimleri bir güvenlik özel durumu ortaya koyar.  
  
### <a name="to-specify-a-url-for-debugging"></a>Hata ayıklama için bir URL belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  İçinde **Proje Tasarımcısı**, tıklatın **güvenlik** sekmesi.  
  
3.  Seçin **ClickOnce güvenlik ayarını etkinleştir** onay kutusunu işaretleyin ve ardından **kısmi güven uygulamasıdır** seçenek düğmesi.  
  
4.  Tıklatın **Gelişmiş** düğmesi.  
  
5.  Seçin **seçili izin kümesi ile bu uygulamanın hatalarını ayıklama** onay kutusunu işaretleyin ve ardından **Tamam**.  
  
6.  İçinde **aşağıdaki URL'yi yüklenen gibi bu uygulamada hata ayıklama** metin kutusuna bir URL girin veya ağ yolu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce Uygulamalarının Güvenliğini Sağlama](../deployment/securing-clickonce-applications.md)