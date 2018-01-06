---
title: "Nasıl yapılır: ClickOnce uygulaması için güncelleştirmeleri yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.Update
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, managing applications
- ClickOnce deployment, updates
- updating data, ClickOnce
- application updates
ms.assetid: a3f23f05-e7f1-4620-b23c-2d68f9643684
caps.latest.revision: "13"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: f239f13a7dcefe0ce6f2bf8c12c641e97a48ce26
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manage-updates-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için Güncelleştirmeleri Yönetme
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]uygulamalarını otomatik olarak veya program aracılığıyla denetleyebilirsiniz. Geliştirici olarak çok sayıda güncelleştirme denetimleri ne zaman ve nasıl yapılır, güncelleştirmelerinin zorunlu olup ve uygulama güncelleştirmeleri nerede denetleyeceğini belirtme esneklik vardır.  
  
 Uygulama başlatıldıktan sonra uygulama başlamadan önce otomatik olarak veya belirlenen aralıklarda güncelleştirmeleri denetlemek için uygulamayı yapılandırabilirsiniz. Ayrıca, gerekli en düşük sürüm belirtebilirsiniz; diğer bir deyişle, kullanıcının sürümü gerekli sürümden düşükse bir güncelleştirme yüklenir.  
  
 Program aracılığıyla bir kullanıcı isteği gibi bir olay tabanlı güncelleştirmeleri denetlemek için uygulamayı yapılandırabilirsiniz. "Güncelleştirmeleri programlı olarak denetlemek için" yordamı bu konudaki kullanan kodu nasıl yazacağınızı gösterir <xref:System.Deployment.Application.ApplicationDeployment> güncelleştirmeleri denetlemek için sınıf olaya bağlı.  
  
 Ayrıca, uygulamanızı bir konumdan dağıtmak ve başka bir güncelleştirme. "Farklı bir güncelleştirme konumu belirtin." yordamına bakın  
  
 Daha fazla bilgi için bkz: [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md).  
  
 Güncelleştirme davranışı yönetilir **uygulama güncelleştirmeleri** iletişim kutusu, kullanılabilir **Yayımla** sayfasında **Proje Tasarımcısı.**  
  
### <a name="to-check-for-updates-before-the-application-starts"></a>Uygulama başlatılmadan önce güncelleştirmeleri denetlemek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **güncelleştirmeleri** açmak için düğmeye **uygulama güncelleştirmeleri** iletişim kutusu.  
  
4.  İçinde **uygulama güncelleştirmeleri** iletişim kutusunda, olduğundan emin olun **uygulama güncelleştirmeleri denetleyeceğini** onay kutusu seçilidir.  
  
5.  İçinde **Uygulama Güncelleştirmeleri denetlerken Seç** bölümünde, select **Uygulama başlatılmadan önce**. Bu, ağa her zaman bağlı kullanıcılar en son güncelleştirmeleri uygulama çalışmasını sağlar.  
  
### <a name="to-check-for-updates-in-the-background-after-the-application-starts"></a>Uygulama başlatıldıktan sonra arka planda güncelleştirmeleri denetlemek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **güncelleştirmeleri** açmak için düğmeye **uygulama güncelleştirmeleri** iletişim kutusu.  
  
4.  İçinde **uygulama güncelleştirmeleri** iletişim kutusunda, olduğundan emin olun onay kutusunu **uygulama güncelleştirmeleri denetleyeceğini** seçilir.  
  
5.  İçinde **uygulama için güncelleştirmeleri bölümüne denetlemelisiniz zaman Seç**seçin **uygulama başladıktan sonra**. Uygulama bu şekilde daha hızlı başlar ve daha sonra bu güncelleştirmeleri arka planda denetler ve bir güncelleştirme kullanılabilir olduğunda yalnızca kullanıcıya bildir. Uygulama yeniden başlatılana kadar yüklendikten sonra güncelleştirmelerin etkili olmaz.  
  
6.  İçinde **uygulama güncelleştirmeleri ne sıklıkta denetleyeceğini belirtin** bölümünde, ya da seçin **uygulama her çalıştığında denetleyin** (varsayılan) veya **denetleyin her** ve bir numara ve zaman aralığı girin.  
  
### <a name="to-specify-a-minimum-required-version-for-the-application"></a>Bir uygulama için gerekli en düşük sürüm belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **güncelleştirmeleri** açmak için düğmeye **uygulama güncelleştirmeleri** iletişim kutusu.  
  
4.  İçinde **uygulama güncelleştirmeleri** iletişim kutusunda, olduğundan emin olun **uygulama güncelleştirmeleri denetleyeceğini** onay kutusu seçilidir.  
  
5.  Seçin **bu uygulama için gerekli en düşük bir sürüm belirtin** onay kutusunu işaretleyin ve ardından girin **ana**, **küçük**, **yapı**ve  **Düzeltme** uygulama için sayı.  
  
### <a name="to-specify-a-different-update-location"></a>Farklı bir güncelleştirme konumu belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **güncelleştirmeleri** açmak için düğmeye **uygulama güncelleştirmeleri** iletişim kutusu.  
  
4.  İçinde **uygulama güncelleştirmeleri** iletişim kutusunda, olduğundan emin olun **uygulama güncelleştirmeleri denetleyeceğini** onay kutusu seçilidir.  
  
5.  İçinde **güncelleştirme konumunu** biçimi http://Hostname/ApplicationName veya biçimi kullanarak bir UNC yolu kullanarak tam bir URL ile güncelleştirme konumu alanına, \\\Server\ApplicationName, veya **Gözat** güncelleştirme konumu gözatmak için düğmeyi.  
  
### <a name="to-check-for-updates-programmatically"></a>Güncelleştirmeleri programlı olarak denetlemek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **güncelleştirmeleri** açmak için düğmeye **uygulama güncelleştirmeleri** iletişim kutusu.  
  
4.  İçinde **uygulama güncelleştirmeleri** iletişim kutusunda, olduğundan emin olun **uygulama güncelleştirmeleri denetleyeceğini** onay kutusu işaretli. (İsteğe bağlı olarak, güncelleştirmeleri programlı olarak ve aynı zamanda güncelleştirmeleri otomatik olarak denetle ClickOnce çalışma zamanı denetlemesine izin vermek için bu onay kutusunu seçebilirsiniz.)  
  
5.  İçinde **güncelleştirme konumunu** biçimi http://Hostname/ApplicationName veya biçimi kullanarak bir UNC yolu kullanarak tam bir URL ile güncelleştirme konumu alanına, \\\Server\ApplicationName, veya **Gözat** güncelleştirme konumu gözatmak için düğmeyi. Uygulamanın güncelleştirilmiş bir sürümünü kendisi için nerede görüneceğini güncelleştirme konumdur.  
  
6.  Güncelleştirmeleri denetlemek için kullanıcıları seçer bir Windows formunda bir düğme, menü öğesi veya diğer kullanıcı arabirimi öğesi oluşturun. Bu öğeye ait olay işleyiciden denetlemek ve güncelleştirmeleri yüklemek için bir yöntemini çağırın. Bu tür bir yöntemi için Visual Basic ve Visual C# kod örneğini bulabilirsiniz [nasıl yapılır: uygulama güncelleştirmeleri program aracılığıyla kullanarak için ClickOnce dağıtım API'si denetimi](../deployment/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api.md).  
  
7.  Uygulamanızı oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Deployment.Application.ApplicationDeployment>   
 [Uygulama güncelleştirmeleri iletişim kutusu](http://msdn.microsoft.com/en-us/8eca8743-8e68-4d04-bfd5-4dc0a9b2934f)   
 [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Nasıl yapılır: ClickOnce Dağıtım API'sini Kullanarak Program Aracılığıyla Uygulama Güncelleştirmelerini Denetleme](../deployment/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api.md)