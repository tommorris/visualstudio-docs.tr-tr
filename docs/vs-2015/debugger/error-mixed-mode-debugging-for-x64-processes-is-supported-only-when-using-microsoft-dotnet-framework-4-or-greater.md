---
title: 'Hata: Karışık modda hata ayıklama için işlemler, yalnızca Microsoft .NET Framework 4 kullanılırken desteklenir x64 veya büyük | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: e4b0216c-7006-4832-883f-08e982ba8d3f
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 479a771300e37e09412accb16771d31454469f95
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678892"
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>Hata: x64 işlemleri için karışık modda hata ayıklama yalnızca Microsoft .NET Framework 4 veya daha yenisi kullanılırken desteklenir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: karışık modda hata ayıklama için işlemler, yalnızca Microsoft .NET Framework 4 kullanılırken desteklenir x64 veya büyük](https://docs.microsoft.com/visualstudio/debugger/error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-dotnet-framework-4-or-greater).  
  
Bir 64-bit işlem içinde karma yerel ve yönetilen kodda hata ayıklamak için olmalıdır [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] sürüm 4. İle 64-bit işlemlerinin karışık mod hata ayıklama [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] sürümleri daha önce 4 desteklenmez.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Aşağıdaki adımlardan birini uygulayın:  
  
    -   Yükseltme, [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] sürüm 4.  
  
    -   Hata ayıklama için uygulamanızın bir 32-bit sürümünü oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cihazda uzak araçları ayarlama](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)



