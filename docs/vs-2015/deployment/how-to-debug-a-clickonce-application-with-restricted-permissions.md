---
title: 'Nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama | Microsoft Docs'
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
- debugging [Visual Studio], ClickOnce applications
- ClickOnce deployment, debugging
- ClickOnce applications, debugging
ms.assetid: 6991ea91-5253-451b-923d-22273a3d38b1
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 7733eeefc758f5e5cd6940108ef6ade645893407
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683659"
---
# <a name="how-to-debug-a-clickonce-application-with-restricted-permissions"></a>Nasıl yapılır: Sınırlı İzinler ile ClickOnce Uygulamasında Hata Ayıklama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama](https://docs.microsoft.com/visualstudio/deployment/how-to-debug-a-clickonce-application-with-restricted-permissions).  
  
Bir geliştirici olarak, büyük olasılıkla son kullanıcı, kısıtlı izinlerle çalıştırırken görebilirsiniz bir ClickOnce uygulamasında hata ayıklarken aynı güvenlik özel durumları görmezsiniz için geliştirme bilgisayarınıza tam güven izinleri ile çalışıyor.  
  
 Bu özel durumları yakalamak için son kullanıcı olarak aynı izinlere sahip bir uygulamada hata ayıklamak gerekir. Sınırlı izinler ile hata ayıklama etkinleştirilebilir **güvenlik** sayfasının **Proje Tasarımcısı**.  
  
 Ayrıca, bu Web Hizmetleri, genellikle Web Hizmetleri çağıran uygulamaları geliştirdiğinizde, geliştirme bilgisayarınızda bulunur. Dağıtıldıktan sonra son kullanıcının farklı bir URL bu Web Hizmetleri erişir. Hata ayıklama sırasında son kullanıcı deneyimi yaşamak için bir URL ve hata ayıklayıcı bu URL'den çağrılan gibi Web Hizmetleri değerlendirilecektir belirtebilirsiniz.  
  
### <a name="to-enable-debugging-with-restricted-permissions"></a>Sınırlı izinler ile hata ayıklamayı etkinleştirmek için  
  
1.  Seçili bir projeyle **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  İçinde **Proje Tasarımcısı**, tıklayın **güvenlik** sekmesi.  
  
3.  Seçin **ClickOnce güvenlik ayarını etkinleştir** onay kutusunu işaretleyin ve ardından **kısmi güven uygulamasıdır** seçenek düğmesini.  
  
4.  Tıklayın **Gelişmiş** düğmesi.  
  
5.  Seçin **bu uygulama için seçili izin kümesi ile hata ayıklama** onay kutusunu işaretleyin ve ardından **Tamam**.  
  
     Uygulamayı hata ayıklaması yaparken erişim izin kümesinin parçası olmayan bir izni girişimleri bir güvenlik özel durumu verir.  
  
### <a name="to-specify-a-url-for-debugging"></a>Hata ayıklama için bir URL belirtmek için  
  
1.  Seçili bir projeyle **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  İçinde **Proje Tasarımcısı**, tıklayın **güvenlik** sekmesi.  
  
3.  Seçin **ClickOnce güvenlik ayarını etkinleştir** onay kutusunu işaretleyin ve ardından **kısmi güven uygulamasıdır** seçenek düğmesini.  
  
4.  Tıklayın **Gelişmiş** düğmesi.  
  
5.  Seçin **bu uygulama için seçili izin kümesi ile hata ayıklama** onay kutusunu işaretleyin ve ardından **Tamam**.  
  
6.  İçinde **aşağıdaki URL'den yüklendiyse bu uygulamada hata ayıklama** metin kutusuna bir URL girin veya ağ yolu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce Uygulamalarının Güvenliğini Sağlama](../deployment/securing-clickonce-applications.md)



