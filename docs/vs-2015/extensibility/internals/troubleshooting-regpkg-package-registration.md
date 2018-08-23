---
title: RegPkg paket kaydı sorunlarını giderme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c5b2ebc470d12586957d77bbe7b076c053567742
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674963"
---
# <a name="troubleshooting-regpkg-package-registration"></a>RegPkg Paket Kaydı Sorunlarını Giderme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [RegPkg paket kaydı sorunlarını giderme](https://docs.microsoft.com/visualstudio/extensibility/internals/troubleshooting-regpkg-package-registration).  
  
> [!NOTE]
>  Visual Studio'da paketleri kaydetmek için tercih edilen yol, .pkgdef dosyaları kullanmaktır. Bu uzantı dağıtım için sistem kayıt defterine erişmek zorunda kalmadan sağlar. Pkgdef dosyaları kullanılarak oluşturulan [CreatePkgDef yardımcı programı](../../extensibility/internals/createpkgdef-utility.md).  
  
 Bir paket içinde RegPkg kullanarak kaydetmek için [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], paketiniz için uygun olan RegPkg sürümünü kullanmanız gerekir.  
  
## <a name="regpkg-versions-related-to-package-versions"></a>Paket sürümleri için ilgili RegPkg sürümleri  
 RegPkg iki sürümü vardır. Bir sürüm eklenir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Bu sürüm aşağıdaki derlemeleri kullanarak oluşturulan paketler kaydetmek için kullanın:  
  
1.  Microsoft.VisualStudioShell.9.0.dll  
  
2.  Microsoft.VisualStudioShell.10.0.dll  
  
3.  Microsoft.VisualStudioShell.11.0.dll  
  
 Bu, önceki Microsoft.VisualStudio.Shell.dll derlemeyi kullanarak oluşturulan paketler kaydedilemiyor.  
  
 RegPkg önceki sürümünü Microsoft.VisualStudio.Shell.dll derlemeyi kullanarak oluşturulan paketler kaydedebilirsiniz. Ancak, bu derlemenin daha yeni sürümleri kullanılarak oluşturulan paketler kayda alınamıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir ürün serbest bırakma](../../misc/releasing-a-visual-studio-integration-product.md)

