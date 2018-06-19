---
title: Çözüm Yapılandırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- solution configurations
ms.assetid: f22cfc75-3e31-4e0d-88a9-3ca99539203b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f7b2a453d4ea4e8b92b40ee126f9441e6f353606
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132727"
---
# <a name="solution-configuration"></a>Çözüm Yapılandırması
Çözüm yapılandırmaları çözüm düzeyi özellikleri depolar. Davranışını doğrudan **Başlat** (F5) anahtarı ve **yapı** komutları. Varsayılan olarak, bu komutları oluşturun ve hata ayıklama yapılandırmasını başlatın. Her iki komutları bir çözüm yapılandırması bağlamında çalıştırın. Bu, başlangıç ve herhangi bir etkin çözüm Ayarları'nda yapılandırılmış derleme için kullanıcı F5 bekleyebilirsiniz anlamına gelir. Ortamı oluşturmak ve çalıştırmak için geldiğinde projeleri yerine çözümleri için en iyi duruma getirmek için tasarlanmıştır.  
  
 Standart Visual Studio araç Başlat düğmesi ve çözüm yapılandırması açılan Başlat düğmesinin sağında bulunur. Bu liste, F5 tuşuna bastığınızda, başlatılması için yapılandırmayı seçin, kendi çözüm yapılandırmaları oluşturmak veya var olan yapılandırmasını düzenlemek kullanıcıların sağlar.  
  
> [!NOTE]
>  Oluşturma veya düzenleme çözüm yapılandırmaları için hiçbir genişletilebilirlik arabirimleri vardır. Kullanmalısınız `DTE.SolutionBuilder`. Ancak, çözümü derleme yönetmek için genişletilebilirlik API'leri vardır. Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2>.  
  
 Proje türü tarafından desteklenen çözüm yapılandırmaları nasıl uygulayabilir şöyledir:  
  
-   Proje  
  
     Geçerli çözümde bulunan projeleri adlarını görüntüler.  
  
-   Yapılandırma  
  
     Proje türü tarafından desteklenen yapılandırmalar listesini sağlayın ve özellik sayfalarında görüntülenen uygulamak için <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>.  
  
     Yapılandırma sütunu, bu çözüm yapılandırması oluşturmak için proje yapılandırması adını görüntüler ve ok düğmesine tıkladığınızda tüm proje yapılandırmaları listeler. Ortam çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgNames%2A> bu listeyi doldurmak için yöntem. Varsa <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgProviderProperty%2A> yöntemi gösterir proje yapılandırmasını düzenleme, yeni destekler veya düzenleme seçimleri de yapılandırma başlığı altında görüntülenir. Bu seçimleri her başlatma yöntemlerini çağırın iletişim kutuları `IVsCfgProvider2` projenin yapılandırmaları düzenlemek için arabirim.  
  
     Proje yapılandırmaları desteklemiyorsa, yapılandırma sütun hiçbiri görüntüler ve devre dışı bırakılır.  
  
-   Platform  
  
     Seçili proje yapılandırması için derlemeler ve ok düğmesine tıkladığınızda tüm projesi için kullanılabilir platformlar listelenir platform görüntüler. Ortam çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetPlatformNames%2A> bu listeyi doldurmak için yöntem. Varsa <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgProviderProperty%2A> yöntemi gösterir proje platform düzenleme, yeni destekler veya düzenleme seçimleri de Platform başlığı altında görüntülenir. Bu seçimleri her başlatma çağırın iletişim kutuları `IVsCfgProvider2` projenin kullanılabilir platformlar düzenlemek için yöntemleri.  
  
     Bir proje platformları desteklemiyorsa, bu proje için platform sütununda hiçbiri görüntüler ve devre dışı bırakılır.  
  
-   Derleme  
  
     Proje geçerli çözüm yapılandırması tarafından oluşturulmuş olup olmadığını belirtir. Çözüm düzeyi derleme komutları içerdikleri proje bağımlılıkları rağmen çağrıldığında seçilmemiş projeleri yerleşik değil. Oluşturulacak seçili olmadığında projeleri, hata ayıklama, çalışan, paketleme ve dağıtım çözümünün hala dahil edilir.  
  
-   Dağıt  
  
     Seçilen çözümü derleme yapılandırmayla başlatma ya da Dağıt komutları kullanıldığında proje dağıtılan olup olmadığını belirtir. Bu alan için onay kutusunu proje uygulayarak dağıtma destekliyorsa kullanılabilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> üzerinde arabirim kendi <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> nesnesi.  
  
 Yeni bir çözüm yapılandırması eklendikten sonra kullanıcı oluşturma ve/veya bu yapılandırmasını başlatmak için standart araç çözüm yapılandırması açılan liste kutusundan seçebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılandırma seçenekleri yönetme](../../extensibility/internals/managing-configuration-options.md)   
 [Proje yapılandırması oluşturmak için](../../extensibility/internals/project-configuration-for-building.md)   
 [Proje Yapılandırması Nesnesi](../../extensibility/internals/project-configuration-object.md)