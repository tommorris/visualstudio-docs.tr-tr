---
title: "Nasıl yapılır: ClickOnce uygulamasıyla Önkoşulları Yükleme | Microsoft Docs"
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
- deploying applications [ClickOnce], prerequisites
- prerequisites, ClickOnce
- components, bootstrapping
ms.assetid: e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5
caps.latest.revision: "13"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 83458b627949cda5f918ec06a5f84bd9697ba6d9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-install-prerequisites-with-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulamasıyla Önkoşulları Yükleme
Tüm [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaları gerektirir çalıştırılabilmesi için önce .NET Framework'ün doğru sürümünü bir bilgisayara yüklenir; pek çok uygulama diğer Önkoşullar da vardır. Yayımlama sırasında bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, uygulamanızın birlikte paketlenmesi önkoşul bileşenleri kümesini seçebilirsiniz. Yükleme sırasında her önkoşulu zaten olup olmadığını belirlemek bir denetim gerçekleştirilir; Bunu yüklemeden önce değil yüklenecekse [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
 Paketleme ve önkoşulları yerine bileşenler için bir yükleme konumu da belirtebilirsiniz. Örneğin, yayımladığınız her uygulama Önkoşullar dahil yerine, bir merkezi dosya paylaşımı veya tüm önkoşulların yükleyicileri içeren Web konumu kullanabilirsiniz — yükleme zamanında bileşenlerinin indirileceği ve Bu konumdan yüklü.  
  
> [!IMPORTANT]
>  İlk yayımlamadan önce önkoşul yükleyicisi paketleri geliştirme bilgisayarınıza eklemelisiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulamasına Önkoşullar dahil](../deployment/how-to-include-prerequisites-with-a-clickonce-application.md).  
  
 Önkoşullar yönetilen **Önkoşullar** iletişim kutusu, erişilebilir **Yayımla** bölmesinde **Proje Tasarımcısı**.  
  
> [!NOTE]
>  Önceden belirlenmiş Önkoşullar listesine ek olarak, kendi bileşenlerinizi listesine ekleyebilirsiniz. Daha fazla bilgi için bkz: [önyükleyici paketleri oluşturma](../deployment/creating-bootstrapper-packages.md).  
  
### <a name="to-specify-prerequisites-to-install-with-a-clickonce-application"></a>İle bir ClickOnce uygulamasını yüklemek için önkoşulları belirlemek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünü tıklatın **özellikleri**.  
  
2.  Seçin **Yayımla** bölmesi.  
  
3.  Tıklatın **Önkoşullar** açmak için düğmeye **Önkoşullar** iletişim kutusu.  
  
4.  İçinde **Önkoşullar** iletişim kutusunda, olduğundan emin olun **Önkoşul bileşenlerini yüklemek için Kurulum programını oluşturun** onay kutusu seçilidir.  
  
5.  İçinde **Önkoşullar** listesinde, yükleyin ve ardından istediğiniz bileşenleri seçin **Tamam**.  
  
     Seçili bileşenler paketlenir ve uygulamanız ile birlikte yayımlanan.  
  
### <a name="to-specify-a-different-download-location-for-prerequisites"></a>Önkoşullar için farklı indirme konumu belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünü tıklatın **özellikleri**.  
  
2.  Seçin **Yayımla** bölmesi.  
  
3.  Tıklatın **Önkoşullar** açmak için düğmeye **Önkoşullar** iletişim kutusu.  
  
4.  İçinde **Önkoşullar** iletişim kutusunda, olduğundan emin olun **Önkoşul bileşenlerini yüklemek için Kurulum programını oluşturun** onay kutusu seçilidir.  
  
5.  İçinde **Önkoşullar için yükleme konumu belirtmek** bölümünde, select **önkoşulları aşağıdaki konumdan indirmek**.  
  
6.  Aşağı açılan listeden bir konum seçin veya bir URL, dosya yolu veya FTP konumunu girin ve ardından **Tamam.**  
  
    > [!NOTE]
    >  Belirtilen bileşenleri için yükleyiciler belirtilen konumda bulunduğundan emin olmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)