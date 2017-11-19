---
title: Hizmet Essentials | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: services, essentials
ms.assetid: fbe84ad9-efe1-48b1-aba3-b50b90424d47
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 006ab3b57a21d5b9a661f06bc984f4dca8757bfd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="service-essentials"></a>Hizmet temelleri
İki VSPackages arasında bir sözleşme hizmetidir. Bir VSPackage arabirimleri kullanmak üzere başka bir VSPackage için belirli bir dizi sağlar. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]kendisi için diğer VSPackages hizmetleri sağlayan VSPackages koleksiyonudur.  
  
 Örneğin, etkinlik günlüğüne yazmak için kullanabileceğiniz bir IVsActivityLog arabirimi sağlamak için SVsActivityLog hizmetini kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: etkinlik günlüğü kullanın](../../extensibility/how-to-use-the-activity-log.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]kayıtlı değil bazı yerleşik hizmetleri de sağlar. VSPackages yerleşik veya diğer hizmetler hizmeti geçersiz kılma sağlayarak değiştirebilirsiniz. Yalnızca bir hizmeti geçersiz kılma için herhangi bir hizmeti izin verilir.  
  
 Hizmetler hiçbir bulunabilirliği sahiptir. Bu nedenle, kullanmak istediğiniz bir hizmetin hizmet tanımlayıcısı (SID) bilmeniz gerekir ve sağladığı hangi arabirimlerin bilmeniz gerekir. Başvuru belgeleri hizmeti için bu bilgileri sağlar.  
  
-   Hizmetleri sağlayan VSPackages hizmet sağlayıcıları denir.  
  
-   Diğer VSPackages sağlanan hizmetleri küresel hizmetler denir.  
  
-   Bunları uygulayan VSPackage veya oluşturur, herhangi bir nesne için kullanılabilen Hizmetleri yerel Hizmetleri olarak adlandırılır.  
  
-   Yerleşik Hizmetleri ya da diğer paketleri tarafından sağlanan hizmetlerin değiştirmek Hizmetleri hizmeti geçersiz kılmaları çağrılır.  
  
-   Hizmetleri veya hizmeti geçersiz kılmaları, isteğe bağlı olarak yüklenir, başka bir VSPackage tarafından istenen sağladığı hizmet başka bir deyişle, hizmet sağlayıcısı yüklenir.  
  
-   İsteğe bağlı yükleme desteklemek için bir hizmet sağlayıcısı ile genel hizmetlerini kaydeder [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: bir hizmet sağlamak](../../extensibility/how-to-provide-a-service.md).  
  
-   Bir hizmet edindikten sonra kullanın [QueryInterface](/cpp/atl/queryinterface) (yönetilmeyen kodu) ya da istenen arabirimi, örneğin almak için (yönetilen kod) atama:  
  
    ```vb  
    TryCast(GetService(GetType(SVsActivityLog)), IVsActivityLog)  
    ```  
  
    ```csharp  
    GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    ```  
  
-   Yönetilmeyen kod GUID'sine Hizmeti'nin başvuruyor ancak yönetilen kod bir hizmet alt türe göre ifade eder.  
  
-   Zaman [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yükleri VSPackage bir küresel hizmetler VSPackage erişmenizi sağlayacak VSPackage için bir hizmet sağlayıcısı geçirir. Bu için "VSPackage siting" olarak adlandırılır.  
  
-   VSPackages oluşturdukları nesneler için hizmet sağlayıcıları olabilir. Örneğin, form renk hizmeti için bir isteği isteği geçebilir çerçevesine gönderme [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   Fazla iç içe veya hiç tarihli değil yönetilen nesneler çağrı <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> doğrudan erişim küresel hizmetler için.   
  
<a name="how-to-use-getglobalservice"></a>  
  
## <a name="use-getglobalservice"></a>GetGlobalService kullanın  
  
Bazen bir aracı penceresinden get bir hizmet ya da değil tarihli, aksi takdirde, istediğiniz hizmeti hakkında bilmez bir hizmet sağlayıcısı ile tarihli kapsayıcı denetimi gerekebilir. Örneğin, bir denetim içindeki etkinlik günlüğünden yazmak isteyebilirsiniz. Bunlar ve diğer senaryolar hakkında daha fazla bilgi için bkz: [nasıl yapılır: sorun giderme Hizmetleri](../../extensibility/how-to-troubleshoot-services.md).  
  
Statik çağırarak çoğu Visual Studio Hizmetleri alabilirsiniz <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> yöntemi.  
  
<xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A>bağımlı bir önbelleğe alınan hizmette herhangi VSPackage türetilmiş paketinden ilk kez başlatıldı sağlayıcısı tarihli. Bu koşul karşılanır, aksi takdirde null bir hizmet için hazırlanması güvence altına almalıdır.  
  
Neyse ki, <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> çoğu zaman düzgün çalışır.  
  
-   Yalnızca başka bir VSPackage bilinen bir hizmet bir VSPackage sağlıyorsa, hizmet talep eden VSPackage hizmeti yüklenmiş sağlama VSPackage önce tarihli.  
  
-   Araç penceresi tarafından VSPackage oluşturduysanız, araç penceresi oluşturulmadan önce VSPackage tarihli.  
  
-   Bir denetim kapsayıcısı VSPackage tarafından oluşturulan bir araç penceresi tarafından barındırılıyorsa denetimi kapsayıcısı oluşturulmadan önce VSPackage tarihli.  
  
### <a name="to-get-a-service-from-within-a-tool-window-or-control-container"></a>Araç penceresi veya denetim kapsayıcı içindeki hizmetinden almak için  
  
-   Bu kod Oluşturucu, araç penceresi veya denetimi kapsayıcısı Ekle:  
  
    ```csharp  
    IVsActivityLog log = Package.GetGlobalService(typeof(SVsActivityLog)) as IVsActivityLog;
        if (log == null) return;
    ```  
    ```vb  
    Dim log As IVsActivityLog = TryCast(Package.GetGlobalService(GetType(SVsActivityLog)), IVsActivityLog)
    If log Is Nothing Then
        Return
    End If
    ```  
    
    Bu kod bir SVsActivityLog hizmeti alır ve etkinlik günlüğüne yazmak için kullanılan bir IVsActivityLog arabirime çevirir. Bir örnek için bkz: [nasıl yapılır: etkinlik günlüğü kullanın](../../extensibility/how-to-use-the-activity-log.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanılabilen hizmetlerin listesi](../../extensibility/internals/list-of-available-services.md)   
 [Kullanarak ve hizmetleri sağlar](../../extensibility/using-and-providing-services.md)   
 [Atama ve tür dönüşümleri](/dotnet/csharp/programming-guide/types/casting-and-type-conversions)   
 [Atama](/cpp/cpp/casting)