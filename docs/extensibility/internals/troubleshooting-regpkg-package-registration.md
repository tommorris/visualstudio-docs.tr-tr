---
title: "RegPkg paketi kayıt sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c4a4162b91a9345c94b7bd6a7e2f1099da3d631e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="troubleshooting-regpkg-package-registration"></a>Sorun giderme RegPkg paketi kaydı
> [!NOTE]
>  Visual Studio'da paketleri kaydetmek için tercih edilen .pkgdef dosyalarını kullanarak yoludur. Bu uzantı dağıtımı için sistem kayıt defteri erişmek zorunda kalmadan sağlar. Pkgdef dosyaları kullanılarak oluşturulur [CreatePkgDef yardımcı programı](../../extensibility/internals/createpkgdef-utility.md).  
  
 Bir paket içinde RegPkg kullanarak kaydetmek için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], paketiniz için uygun olan RegPkg sürümünü kullanmanız gerekir.  
  
## <a name="regpkg-versions-related-to-package-versions"></a>Paket sürümleriyle ilgili RegPkg sürümleri  
 RegPkg iki sürümü vardır. Bir sürümü dahil [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bu sürüm aşağıdaki derlemeler birini kullanarak yerleşik paketleri kaydetmek için kullanın:  
  
1.  Microsoft.VisualStudioShell.9.0.dll  
  
2.  Microsoft.VisualStudioShell.10.0.dll  
  
3.  Microsoft.VisualStudioShell.11.0.dll  
  
 Önceki Microsoft.VisualStudio.Shell.dll derleme kullanarak yerleşik paketlerini kaydedilemiyor.  
  
 RegPkg önceki sürümünü Microsoft.VisualStudio.Shell.dll derleme kullanarak yerleşik paketleri kaydedebilirsiniz. Ancak, bu derleme'nın sonraki sürümleri kullanılarak oluşturulan paketler kaydı yapılamıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackages](../../extensibility/internals/vspackages.md)