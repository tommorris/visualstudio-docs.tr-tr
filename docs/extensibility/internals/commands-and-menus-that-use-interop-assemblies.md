---
title: Komutlar ve birlikte çalışma derlemeleri kullanma menüleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus, using interop assemblies
- interop assemblies, using in commands and menus
- commands, handling using interop assemblies
- command handling with interop assemblies
ms.assetid: 8f4af525-39e5-4e69-92c8-d3efabe80bb2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c48ee7eb25fa95789076454c849485f4ac1dc384
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="commands-and-menus-that-use-interop-assemblies"></a>Komutlar ve birlikte çalışma derlemeleri kullanma menüleri
Birlikte çalışma derlemeleri kullanarak menü ve araç çubuğu komutlarını uygulayan bir VSPackage gerekir:  
  
-   Bildirmek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamını (IDE) desteklediği komutlar ve bunlar şu anda etkinleştirilip etkinleştirilmediği.  
  
-   Komutları işleme için (sözleşme) kurallarına uyması.  
  
-   Komut işleme kullanarak açıkça uygulama <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> arabirimi.  
  
 Bu görevlerin nasıl yapılacağını açıklar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Birlikte Çalışma Bütünleştirilmiş Kodları Kullanarak Komut Durumunu Belirleme](../../extensibility/internals/determining-command-status-by-using-interop-assemblies.md)  
 Nasıl bir VSPackage IDE bildirir açıklar hangi komutları hakkında destekliyorsa ve bunlar şu anda etkinleştirilip etkinleştirilmediği.  
  
 [Birlikte Çalışma Bütünleştirilmiş Kodlarında Komut Sözleşmeleri](../../extensibility/internals/command-contracts-in-interop-assemblies.md)  
 Birlikte çalışma derlemeleri kullanarak komutları uygulama tüm VSPackages tarafından kullanılan temel komutu sözleşmesi tanımını sağlar  
  
 [Uygulama](../../extensibility/internals/command-implementation.md)  
 Bir komut bir VSPackage nasıl uyguladığını genel bir bakış sağlar.  
  
 [Birlikte Çalışma Bütünleştirilmiş Kodu Komut İşleyicilerini Kaydetme](../../extensibility/internals/registering-interop-assembly-command-handlers.md)  
 Bir VSPackage bir komut işleyici sağlar IDE bildirmek için gerekli kayıt defteri girdileri açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Kullanılabilirlik](../../extensibility/internals/command-availability.md)  
 IDE tarafından hangi VSPackage komutlar kullanılabilir ve hangi nesne bunları işler belirlemek için kullanılan ölçüt açıklar.  
  
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Kullanan kullanıcı Arabirimi oluşturma hakkında ayrıntılar sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komut desteği.  
  
 [VSPackage’larda Komut Yönlendirme](../../extensibility/internals/command-routing-in-vspackages.md)  
 Bir nesne doğru komutu istek ile ilişkilendirmek için kullanılan işlemine genel bakış.