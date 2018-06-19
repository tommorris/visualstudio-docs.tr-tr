---
title: RegPkg paketi kayıt sorunlarını giderme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4857e41888962a92dced87d63fa2b63161ecac55
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137124"
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
 [VSPackage’lar](../../extensibility/internals/vspackages.md)