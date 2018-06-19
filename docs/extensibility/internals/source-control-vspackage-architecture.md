---
title: Kaynak denetimi VSPackage mimarisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control packages, architecture
ms.assetid: 453125fc-23dc-49b1-8476-94581f05e6c7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a423b270eb8a26e9573f957da48915db37bf6851
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131900"
---
# <a name="source-control-vspackage-architecture"></a>Kaynak Denetim VSPackage mimarisi
Kaynak denetimi kullanan bir VSPackage Hizmetleri paketidir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE sağlar. Buna karşılık, bir kaynak denetimi paket kaynak denetimi hizmet olarak işlevselliği sağlar. Ayrıca, bir kaynak denetimi daha verimli bir alternatif bir kaynak denetimi kaynak denetimine tümleştirmek için eklenti daha paketidir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Kaynak denetimi kaynak denetim eklentisi API uygulayan eklenti tarafından sıkı bir sözleşme bağlıdır. Örneğin, bu eklenti varsayılan değiştirilemiyor [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kullanıcı arabirimi (UI). Ayrıca, kaynak denetim eklentisi API kendi kaynak denetimi modeli uygulamak bir eklenti etkinleştirmez. Bir kaynak denetimi paket ancak, bu sınırlamalara her ikisi de ortadan kaldırır. Kaynak denetimi paket kaynak denetimi deneyimini tam denetime sahiptir bir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kullanıcı. Ayrıca, bir kaynak denetimi paket kendi kaynak denetimi modeli ve mantığı kullanabilirsiniz ve tüm kaynak denetimi ilgili kullanıcı arabirimleri tanımlayabilirsiniz.  
  
## <a name="source-control-package-components"></a>Kaynak denetimi paketi bileşenleri  
 Mimari diyagramda gösterildiği gibi bir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kaynak denetimi saplama adlı bir kaynak denetimi paketi ile tümleşen bir VSPackage bileşenidir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Kaynak denetimi saplama aşağıdaki görevleri gerçekleştirir.  
  
-   Kaynak denetimi paketi kaydı için gerekli olan ortak bir kullanıcı Arabirimi sağlar.  
  
-   Bir kaynak denetimi paketi yükler.  
  
-   Bir kaynak denetimi paketi etkin/devre dışı ayarlar.  
  
 Kaynak denetimi saplama kaynak denetimi paket için etkin hizmet arar ve IDE gelen paket kadar olan tüm gelen hizmet çağrıları yönlendirir.  
  
 Kaynak Denetim bağdaştırıcısı özel bir kaynak denetimi paketini paketidir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sağlar. Bu paket, kaynak denetimi kaynak denetim eklentisi API'ye bağlı eklentiler desteklemek için merkezi bir bileşendir. Kaynak Denetim eklentisi eklenti etkin olduğunda, kaynak denetimi saplama olaylarına kaynak denetimi bağdaştırıcı paketi gönderir. Buna karşılık, kaynak denetim bağdaştırıcı paketi kaynak denetim eklentisi API kullanarak eklenti kaynak denetimi ile iletişim kurar ve ayrıca varsayılan tüm kaynak denetim eklentileri ortak olan kullanıcı Arabirimi sağlar.  
  
 Bir kaynak denetimi paketi etkin paketi olduğunda, diğer yandan, kaynak denetimi saplama doğrudan paketiyle kullanarak iletişim kurar [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] kaynak denetimi paket arabirimleri. Kaynak denetimi paketi, kendi kaynak denetimi UI barındırmak için sorumludur.  
  
 ![Kaynak Denetim Mimarisi grafiği](../../extensibility/internals/media/vsipsccarch.gif "VSIPSCCArch")  
  
 Bir kaynak denetimi paket için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kaynak denetim kodu veya bir API tümleştirme sağlamaz. Bunu özetlenen yaklaşım ile karşılaştırın [kaynak denetim eklentisi oluşturma](../../extensibility/internals/creating-a-source-control-plug-in.md) eklenti kaynak denetimi sahip olduğu işlevler ve geri aramalar katı bir dizi uygulamak.  
  
 Tüm VSPackage gibi bir kaynak denetimi paketi kullanılarak oluşturulan bir COM nesnesi olduğu `CoCreateInstance`. VSPackage kendisi için kullanılabilir hale getirir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uygulayarak IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>. Bir örneğini oluştururken bir VSPackage site işaretçi alır ve bir <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> kullanılabilir hizmetler ve IDE arabirimlerde VSPackage erişim sağlayan arabirim.  
  
 Kaynak Denetim eklentisi API tabanlı bir yazma değerinden daha gelişmiş programlama uzmanlık gerektirir VSPackage tabanlı kaynak denetimi paket yazma eklentisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>   
 [Başlarken](../../extensibility/internals/getting-started-with-source-control-vspackages.md)