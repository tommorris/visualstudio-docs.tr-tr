---
title: ClickOnce dağıtım stratejisini seçme | Microsoft Docs
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
- ClickOnce deployment, strategies
- deploying applications, ClickOnce
ms.assetid: 98bcab65-ab8b-4ed1-9adc-fdacf92b8106
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 19df2f0fcef6cdcdffb2424a89118c8fe72040c9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="choosing-a-clickonce-deployment-strategy"></a>ClickOnce Dağıtım Stratejisini Seçme
Dağıtımı için üç farklı strateji vardır bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] öncelikle dağıtmakta olduğunuz uygulama türüne bağlıdır seçtiğiniz strateji; uygulama. Üç dağıtım stratejisi aşağıdaki gibidir:  
  
-   Web'den veya bir Ağ Paylaşımı'ndan yükle  
  
-   CD'den yükle  
  
-   Uygulamayı Web'den veya Ağ Paylaşımı'ndan başlat  
  
    > [!NOTE]
    >  Dağıtım stratejisi seçmenin yanı sıra, uygulama güncelleştirmeleri sağlamak için de bir strateji seçmek isteyeceksiniz. Daha fazla bilgi için bkz: [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md).  
  
## <a name="install-from-the-web-or-a-network-share"></a>Web'den veya bir Ağ Paylaşımı'ndan yükle  
 Bu stratejiyi kullandığınızda, uygulamanız bir Web sunucusuna veya ağ dosyası paylaşımına dağıtılır. Son kullanıcı uygulamayı yüklemek istediğinde, Web sayfası üzerinde bir simgeye tıklar veya dosya paylaşımındaki simgeye çift tıklar. Sonra son kullanıcının bilgisayarında uygulama indirilir, kurulur ve başlatılır. Öğeleri eklenir **Başlat** menü ve **Program Ekle veya Kaldır** içinde **Denetim Masası**.  
  
 Bu strateji ağ bağlantısına bağlı olduğundan, yerel ağ veya yüksek hızlı Internet bağlantısı erişimi olan kullanıcılar çok iyi çalışır.  
  
 Uygulamayı Web'den dağıtırsanız, URL kullanımı etkinleştirildiğinde bağımsız değişkenleri uygulamaya geçirebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: çevrimiçi bir ClickOnce uygulamasında sorgu dize bilgilerini alma](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md). Bu belgede açıklanan diğer yöntemleri kullanarak etkinleştirilen bir uygulamaya bağımsız değişkenler geçirilemez.  
  
 Bu dağıtım stratejisini etkinleştirmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], tıklatın **From Web** veya **gelen bir UNC yolu veya dosya paylaşımı** üzerinde **nasıl yükleneceğini** Yayımlama Sihirbazı sayfası.  
  
 Bu, varsayılan dağıtım stratejisidir.  
  
## <a name="install-from-a-cd"></a>CD'den yükle  
 Bu stratejiyi kullandığınızda, uygulamanız CD-ROM veya DVD gibi çıkarılabilir ortamla dağıtılır. Önceki seçenek uygulamayı yüklemek kullanıcı seçer, yüklenmiş ve başlatılmış ve öğeleri eklenir, olduğu gibi **Başlat** menü ve **Program Ekle veya Kaldır** içinde **denetim Panel**.  
  
 Bu strateji en iyi, devamlı ağ bağlantısı olmayan veya bant genişliği düşük bağlantısı olan kullanıcılara dağıtılacak uygulamalar için çalışır. Uygulama çıkarılabilir ortamdan yüklendiğinden yükleme için ağ bağlantısı gerekmez, ancak ağ bağlantısını yine de uygulama güncelleştirmeleri için gereklidir.  
  
 Bu dağıtım stratejisini etkinleştirmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], tıklatın **gelen bir CD-ROM veya DVD-ROM'UNDAN** üzerinde **nasıl yükleneceğini** Yayımlama Sihirbazı sayfası.  
  
 Bu dağıtım stratejisini el ile etkinleştirmek için değiştirme **deploymentProvider** dağıtım bildiriminde etiketi. (Visual Studio'da bu özellik olarak sunulan **yükleme URL'si** üzerinde **Yayımla** sayfası Proje Tasarımcısı'nın. İçinde Bu Mage.exe **Başlat konumu**.)  
  
## <a name="start-the-application-from-the-web-or-a-network-share"></a>Uygulamayı Web'den veya Ağ Paylaşımı'ndan başlat  
 Uygulamanın bir Web uygulaması gibi davranması dışında, bu strateji birinci stratejiye benzer. Kullanıcı Web sayfası üzerinde bir bağlantıyı tıkladığında (veya dosya paylaşımında bir simgeye çift tıklarsa) uygulama başlatılır. Kullanıcılar uygulamayı kapattığınızda, artık yerel bilgisayarlarında kullanılamıyor; hiçbir şey eklenen **Başlat** menüsü veya **Program Ekle veya Kaldır** içinde **Denetim Masası**.  
  
> [!NOTE]
>  Teknik olarak uygulama, Web uygulamalarının Web önbelleğine indirilmesi gibi yerel bilgisayar üzerinde uygulama önbelleğine indirilir ve kurulur. Web önbelleği gibi, dosyalar son olarak uygulama önbelleğinden atılır. Ancak, kullanıcı uygulamanın Web'den veya dosya paylaşımından çalıştığını zanneder.  
  
 Bu strateji en iyi seyrek kullanılan uygulamalar için çalışır. Örneğin, genellikle her yıl yalnızca bir kez çalıştırılan bir çalışan-yarar aracı.  
  
 Bu dağıtım stratejisini etkinleştirmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], tıklatın **uygulama yüklemeyen** üzerinde **yükleme veya Web'den çalıştırmak** Yayımlama Sihirbazı sayfası.  
  
 Bu dağıtım stratejisini el ile etkinleştirmek için değiştirme **yükleme** dağıtım bildiriminde etiketi. (Değerini olabilir **true** veya **false**. İçinde Mage.exe, kullanım **yalnızca çevrimiçi** seçeneğini **uygulama türü** listesi.)  
  
## <a name="web-browser-support"></a>Web Tarayıcısı Desteği  
 .NET Framework 3.5 kullanan uygulamalar herhangi bir tarayıcı kullanarak yüklenebilir.  
  
 .NET Framework 2.0 kullanan uygulamalar Internet Explorer gerektirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [ClickOnce Uygulamalarının Güvenliğini Sağlama](../deployment/securing-clickonce-applications.md)