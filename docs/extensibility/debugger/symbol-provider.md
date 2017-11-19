---
title: "Sembol sağlayıcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- symbol handler
- debugging [Debugging SDK], symbol handler
ms.assetid: 5fce651b-fead-4418-81b0-a011df7644ab
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f845e18bbd4c06d5652571ec83270a80d31ec852
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="symbol-provider"></a>Sembol sağlayıcısı
İfade değerlendirici uygulaması değişkenleri ve ifadeler değerlendirmek için dil derleyici tarafından üretilen simgesel hata ayıklama bilgileri erişmeniz gerekir. Bunu bir simge işleyici olarak da bilinir simgesi sağlayıcısı (SP) arabirimlerini kullanan tarafından yapar.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Program veritabanı (PDB) simgesi dosya biçimini kullanarak yerel kod yanı sıra yönetilen kod için Sp'ler sağlar. Olmadığı sürece güçlü bir özel bir biçimde depolanan sembolleri kullanmak, program için gereken, tarafından sağlanan Sp'ler kullanmanız önerilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="implementation-notes"></a>Uygulama Notları  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Hata ayıklama motorları beklediğiniz ortak dil çalışma zamanı (CLR) arabirimleri kullanarak SP ile iletişim kurabilecek şekilde. Sonuç olarak, Visual Studio hata ayıklama motorları ile çalışan bir SP CLR desteklemesi gerekir. Hata ayıklama arabirimleri tüm CLR tam bir listesi yer debugref.doc içinde bulunabilir, [!INCLUDE[winsdklong](../../deployment/includes/winsdklong_md.md)].  
  
 Yalnızca özel hata ayıklama alt yapısı ile SP çalışacaksınız, hata ayıklama altyapınız gereksinimlerine bağlı olarak uygun gördüğünüz şekilde SP uygulayabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı bileşenleri](../../extensibility/debugger/debugger-components.md)