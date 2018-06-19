---
title: System.Deployment.Application kullanan ClickOnce uygulamalarında hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, debugging
- debugging, ClickOnce applications
- debugging, System.Deployment
- deploying applications [ClickOnce], debugging
ms.assetid: 86f31948-2ca8-47c0-8e8b-c2b817bbf79f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 30cbf4aab2975b95703c24462604c1a43ed3554c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31561668"
---
# <a name="debugging-clickonce-applications-that-use-systemdeploymentapplication"></a>System.Deployment.Application Kullanan ClickOnce Uygulamalarında Hata Ayıklama
İçinde [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım, bir uygulamanın nasıl güncelleştirileceğini yapılandırmanıza olanak sağlar. Ancak, kullanın ve özelleştirmek gerekiyorsa Gelişmiş [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım özellikleri tarafından sağlanan dağıtım nesne modeline erişmeniz gerekir <xref:System.Deployment.Application>. Kullanabileceğiniz <xref:System.Deployment.Application> API'leri için Gelişmiş görevler gibi:  
  
-   "Şimdi güncelleştir" seçeneğini uygulamanızı oluşturma  
  
-   Koşullu, isteğe bağlı çeşitli uygulama bileşenlerini yükler  
  
-   Doğrudan uygulamaya tümleşik güncelleştirmeleri  
  
-   İstemci uygulama her zaman güncel olmasını güvence altına alır  
  
 Çünkü <xref:System.Deployment.Application> API'leri iş yalnızca bir uygulama ile dağıtıldığında [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] teknolojisi, bunlardan hata ayıklamanın tek yoludur kullanılarak uygulama dağıtmak için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], ekleyebilir ve sonra bu hata ayıklama. Hata ayıklayıcısını zor olabilir yeterince erken, uygulama başlatıldığında ve hata ayıklayıcısı eklemeden önce yürütür bu kodu genellikle çalıştığı için. Güncelleştirme onay kodu veya isteğe bağlı kodu önce sonları (veya Visual Basic projeleri için durdurulur) yerleştirmek için kullanılan bir çözümdür.  
  
 Önerilen hata ayıklama tekniği aşağıdaki gibidir:  
  
1.  Başlamadan önce simge (.pdb) ve kaynak dosyaları arşivlenmiş emin olun.  
  
2.  Uygulamanın sürüm 1 dağıtın.  
  
3.  Yeni boş bir çözüm oluşturun. Gelen **dosya** menüsünde tıklatın **yeni**, ardından **proje**. İçinde **yeni proje** açık iletişim kutusunu **diğer proje türleri** düğümünü, ardından **Visual Studio çözümleri** klasör. İçinde **şablonları** bölmesinde, **boş çözüm**.  
  
4.  Bu yeni çözüm özelliklerini arşivlenmiş kaynak konumunu ekleyin. İçinde **Çözüm Gezgini**, çözüm düğümüne sağ tıklayın ve ardından **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda **kaynak dosyalarında Hata Ayıkla**, arşivlenen kaynak kodu dizinini ekleyin. Aksi halde, kaynak dosya yolları .pdb dosyasına kaydedilir bu yana hata ayıklayıcı güncel kaynak dosyaları bulur. Hata ayıklayıcı güncel olmayan kaynak dosyalarını kullanıyorsa, kaynak eşleşmiyor söyleyen bir ileti görür.  
  
5.  Hata ayıklayıcı .pdb dosyaları bulabileceğinden emin olun. Hata ayıklayıcı uygulamanızla dağıttıysanız, bunları otomatik olarak bulur. Her zaman yanındaki derleme önce söz konusu görünüyor. Aksi takdirde, arşiv yolunu eklemeniz gerekir **simge (.pdb) dosya konumları** (Bu seçenek erişmek için **Araçları** menüsünde tıklatın **seçenekleri**, açın **Hata ayıklama** düğümü ve tıklatın **simgeleri**).  
  
6.  Arasında ne gerçekleştiğini tespit `CheckForUpdate` ve `Download` / `Update` yöntem çağrıları.  
  
     Örneğin, güncelleştirme kodu aşağıdaki gibi olabilir:  
  
    ```  
        Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
            If My.Application.Deployment.IsNetworkDeployed Then  
  
                If (My.Application.Deployment.CheckForUpdate()) Then  
  
                    My.Application.Deployment.Update()  
                    Application.Restart()  
  
                End If  
  
            End If  
        End Sub  
    ```  
  
7.  Sürüm 2 dağıtın.  
  
8.  Sürüm 2 güncelleştirmesi indirilirken hata ayıklayıcı sürüm 1 uygulamasına iliştirin. Alternatif olarak kullanabileceğiniz `System.Diagnostics.Debugger.Break` yöntemi ya da yalnızca `Stop` Visual Basic'te. Elbette, üretim kodunda bu yöntem çağrılarını bırakmamalısınız.  
  
     Örneğin, bir Windows Forms uygulaması geliştirme ve güncelleştirme mantığı ile bu yöntem için bir olay işleyicisi içinde sahip varsayın. Düğmesine basıldığında sonra bir kesme noktası belirleyerek önce bu hata ayıklamak için basitçe ekleme (uygun arşivlenmiş dosyasını açın ve kesme var. ayarlayın emin olun).  
  
 Kullanım <xref:System.Deployment.Application.ApplicationDeployment.IsNetworkDeployed%2A> çağrılacak özelliği <xref:System.Deployment.Application> yalnızca uygulama dağıtıldığında API'leri; API içinde hata ayıklama sırasında çağrılmamalıdır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Deployment.Application>