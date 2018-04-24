---
title: 'Nasıl yapılır: ClickOnce uygulaması için bir yayımlama sayfası belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], specifying publish page
- Publish Page property
- publishing, ClickOnce
- ClickOnce deployment, specifying publish page
ms.assetid: 9d70eebb-bdee-4b42-8e7e-7a07e199bdf7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 864d0ef0f4934e040722a9a9fc00ba7a54f3331c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-specify-a-publish-page-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için bir Yayımlama Sayfası Belirtme
Yayımlama sırasında bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, varsayılan bir Web sayfası (publish.htm) oluşturulur ve uygulama ile birlikte yayımlanır. Bu sayfa uygulama, uygulama ve/veya herhangi bir önkoşulu yüklemek için bir bağlantı ve bir Yardım konusu açıklayan bir bağlantı adını içeren [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. **Yayımla Sayfası** projeniz için özellik sağlar, Web sayfası için bir ad belirtmek, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
 Sonraki yayımladığınızda, yayımlama sayfası belirtilen sonra onu yayımlama konumuna kopyalanacak; yeniden yayımlarsanız yazılmaz. Sayfa görünümünü özelleştirmek istiyorsanız, değişikliklerinizi kaybetme hakkında endişelenmeden bunu yapabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce Varsayılan Web sayfasını özelleştirme](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md).  
  
 **Yayımla Sayfası** özelliği, ayarlanabilir **Yayımla Seçenekleri** iletişim kutusu, erişilebilir **Yayımla** bölmesinde **Proje Tasarımcısı**.  
  
### <a name="to-specify-a-custom-web-page-for-a-clickonce-application"></a>ClickOnce uygulaması için özel bir Web sayfasını belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünü tıklatın **özellikleri**.  
  
2.  Seçin **Yayımla** bölmesi.  
  
3.  Tıklatın **seçenekleri** açmak için düğmeye **Yayımla Seçenekleri** iletişim kutusu.  
  
4.  Tıklatın **dağıtım**.  
  
5.  İçinde **Yayımla Seçenekleri** iletişim kutusunda, olduğundan emin olun **açık dağıtım web sayfası sonra Yayımlama** onay kutusu seçilidir (varsayılan olarak seçili).  
  
6.  İçinde **dağıtım web sayfası:** kutusunda, Web sayfası için bir ad girin ve ardından **Tamam**.  
  
### <a name="to-prevent-the-publish-page-from-launching-each-time-you-publish"></a>Yayımla Sayfası her yayımladığınızda başlamasını engellemek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünü tıklatın **özellikleri**.  
  
2.  Seçin **Yayımla** bölmesi.  
  
3.  Tıklatın **seçenekleri** açmak için düğmeye **Yayımla Seçenekleri** iletişim kutusu.  
  
4.  Tıklatın **dağıtım**.  
  
5.  İçinde **Yayımla Seçenekleri** iletişim kutusu, Temizle **açık dağıtım web sayfası sonra Yayımlama** onay kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Nasıl yapılır: ClickOnce Varsayılan Web sayfasını özelleştirme](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)