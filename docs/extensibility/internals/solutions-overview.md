---
title: Çözümlerine genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- solutions, about solutions
ms.assetid: 3b21e3a1-170a-4485-941e-6b04b7b27886
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d64175c570c4fbca26bae0aa587b66e04cbee2be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="solutions-overview"></a>Çözümlerine genel bakış
Bir çözüm, bir uygulama oluşturmak için birlikte çalışan bir veya daha fazla projeleri gruplandırmasıdır. Çözüme ilgili proje ve durum bilgilerini iki farklı çözüm dosyasında depolanır. Metin tabanlı çözüm (.sln) dosyasıdır ve kullanılabilir kaynak kodu denetimi altında yerleştirilir ve kullanıcı arasında paylaşılan. Çözüm kullanıcı seçeneği (.suo) ikili dosyadır. Sonuç olarak, .suo dosya kaynak kodu denetimi altında yer alamaz ve kullanıcıya özgü bilgileri içerir.  
  
 Tüm VSPackage çözüm dosyası iki tür birine yazabilirsiniz. Dosyaları yapısı nedeniyle, bunları yazmak için uygulanan iki farklı arabirimleri vardır. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> Arabirimi .sln dosyasını metin bilgi yazar ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> arabirimi ikili akışlar .suo dosyasına yazar.  
  
> [!NOTE]
>  Bir proje açıkça bir giriş kendisi için çözüm dosyasına yazmak zorunda değildir; ortamı, proje için işler. Bu nedenle, ek içerik özellikle çözüm dosyasına eklemek istediğiniz sürece, bu şekilde, VSPackage kaydetmek gerekmez.  
  
 Çözüm Kalıcılık destekleyen her VSPackage üç arabirimi kullanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> ortamı tarafından uygulanan ve VSPackage tarafından çağrılır, arabirim ve `IVsPersistSolutionProps` ve `IVsPersistSolutionOpts`, her ikisi de uygulanan hangi olan VSPackage tarafından. `IVsPersistSolutionOpts` Arabirimi yeterlidir özel bilgileri tarafından VSPackage .suo dosyasına yazılması yoksa uygulanacak.  
  
 Bir çözüm açıldığında, aşağıdaki süreç gerçekleşir.  
  
1.  Ortam çözümü okur.  
  
2.  Ortam bulursa bir `CLSID`, karşılık gelen VSPackage yükler.  
  
3.  Bir VSPackage yüklendiği varsa, ortam çağrıları `QueryInterface` için <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> VSPackage gerektirir arabirimi için arabirim.  
  
    1.  Bir .sln dosyasından okurken ortamı çağırır `QueryInterface` için `IVsPersistSolutionProps`.  
  
    2.  Bir .suo dosyasından okurken ortamı çağırır `QueryInterface` için `IVsPersistSolutionOpts`.  
  
 Bu dosyaları kullanmak için ilgili belirli bilgileri bulunabilir [çözüm (. Sln) dosya](../../extensibility/internals/solution-dot-sln-file.md) ve [çözüm kullanıcı seçenekleri (. Suo) dosya](../../extensibility/internals/solution-user-options-dot-suo-file.md).  
  
> [!NOTE]
>  Yeni bir çözüm yapılandırması iki proje yapılandırmalarını oluşan ve üçüncü bir derlemeden dışlama oluşturmak istiyorsanız, otomasyon ve özellik sayfaları UI kullanmak gerekir. Çözüm derleme Yöneticisi yapılandırmaları ve özellikleri doğrudan değiştiremezsiniz, ancak çözüm yapı Yöneticisi'ni kullanarak işleyebileceğiniz `SolutionBuild` DTE sınıfında otomasyon modeli. Çözümleri yapılandırma hakkında daha fazla bilgi için bkz: [çözüm yapılandırması](../../extensibility/internals/solution-configuration.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>