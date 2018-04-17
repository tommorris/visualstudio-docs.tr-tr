---
title: 'Nasıl yapılır: Hizmetleri sorunlarını giderme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- services, troubleshooting
ms.assetid: 001551da-4847-4f59-a0b2-fcd327d7f5ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d9efe3c1c7032f1db41272a03cf689e015a79522
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-troubleshoot-services"></a>Nasıl yapılır: Hizmetleri sorunlarını giderme
Bir hizmet almayı deneyin yüklendiğinde oluşabilecek bazı ortak sorunlar vardır:  
  
-   Hizmet kayıtlı değil [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
-   Hizmet arabirimi türüne göre ve hizmet türü tarafından istendi.  
  
-   Hizmet isteyen VSPackage tarihli değil.  
  
-   Yanlış hizmeti sağlayıcısı kullanılır.  
  
 İstenen hizmet elde edilemiyor varsa, çağrısı <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> null döndürür. Null bir hizmet istedikten sonra her zaman test etmeniz gerekir:  
  
```csharp  
IVsActivityLog log =   
    GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
if (log == null) return;  
```  
  
### <a name="to-troubleshoot-a-service"></a>Bir hizmet gidermek için  
  
1.  Hizmet doğru şekilde kayıtlı olup olmadığını görmek için sistem kayıt defteri inceleyin. Daha fazla bilgi için bkz: [nasıl yapılır: bir hizmet sağlamak](../extensibility/how-to-provide-a-service.md).  
  
     Aşağıdaki .reg dosyasını parça SVsTextManager hizmet nasıl kayıtlı gösterir:  
  
    ```  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\<version number>\Services\{F5E7E71D-1401-11d1-883B-0000F87579D2}]  
    @="{F5E7E720-1401-11d1-883B-0000F87579D2}"  
    "Name"="SVsTextManager"  
    ```  
  
     Yukarıdaki örnekte, sürüm numarası sürümüdür [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]12.0 veya 14.0, {F5E7E71D-1401-11d1-883B-0000F87579D2} anahtar hizmeti, SVsTextManager ve varsayılan değeri {hizmet tanımlayıcısı (SID) gibi F5E7E720-1401-11D1-883B-0000F87579D2} metin Yöneticisi hizmeti sağlayan VSPackage GUİD'si paketidir.  
  
2.  GetService çağırdığınızda hizmet türü ve arabirim türü kullanabilirsiniz. Bir hizmetinden isterken [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], <xref:Microsoft.VisualStudio.Shell.Package> türünden GUID ayıklar. Aşağıdaki koşullar doğruysa bir hizmet bulunamayacaktır:  
  
    1.  Bir arabirim türünün GetService için hizmet türü yerine geçirilir.  
  
    2.  Hiç GUID açıkça arabirime atanmış. Bu nedenle, sistem gerektiği gibi bir nesne için varsayılan bir GUID oluşturur.  
  
3.  Hizmet isteyen VSPackage tarihli emin olun. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir VSPackage, oluşturma sonrasında ve çağırmadan önce siteleri <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>.  
  
     Bir hizmetin ihtiyaç VSPackage oluşturucuda kodu varsa, bu, Initialize yöntemi başına taşıyın.  
  
4.  Doğru hizmet sağlayıcısı kullandığınızdan emin olun.  
  
     Tüm hizmet sağlayıcıları benzer. Hizmet sağlayıcısı, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir VSPackage geçirmeden bir araç penceresi geçer farklıdır. Araç penceresi hizmet sağlayıcısı bildiği <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>, hakkında bilgi sahibi değildir ancak <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>. Çağırabilirsiniz <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> VSPackage hizmet sağlayıcıdan bir araç penceresi içinden almak için.  
  
     Araç penceresi bir kullanıcı denetimi veya başka bir denetim kapsayıcısı barındırıyorsa, kapsayıcı Windows Bileşen modeli tarafından tarihli ve herhangi bir erişemeyecektir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Hizmetleri. Çağırabilirsiniz <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> VSPackage hizmet sağlayıcıdan bir denetim kapsayıcısı içinde alınamıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanılabilen hizmetlerin listesi](../extensibility/internals/list-of-available-services.md)   
 [Kullanarak ve hizmetleri sağlar](../extensibility/using-and-providing-services.md)   
 [Hizmet Temel Bileşenleri](../extensibility/internals/service-essentials.md)