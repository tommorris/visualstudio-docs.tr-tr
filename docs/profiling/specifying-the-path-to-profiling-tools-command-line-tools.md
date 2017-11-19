---
title: "Profil oluşturma yolunu belirtme Araçları komut satırı araçları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d6b05de013143c1def53044a40977657fdd2cfcb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>Profil Oluşturma Araçları Komut Satırı Araçları Yolunu Belirtme
Yolunu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları komut satırı araçları PATH ortam değişkenine eklenmez. 32-bit bilgisayarlarda, tek bir dizin araçlardır. 32 bit ve 64-bit sürümü 64-bit bilgisayarlarda profil oluşturma araçları vardır.  
  
## <a name="32-bit-computers"></a>32-bit bilgisayarlar  
 32-bit bilgisayarlarda, varsayılan profil oluşturucu Araçlar dizinidir *sürücü*\Program Visual Studio 11.0\Team Araçlar\Performans araçları.  
  
## <a name="64-bit-computers"></a>64 bit bilgisayarlar  
 64-bit bilgisayarlarda, profili uygulamanın hedef platformu göre yolu belirtin.  
  
-   32-bit uygulamalar için varsayılan profil oluşturucu Araçlar dizindir:  
  
     *Sürücü*\Program dosyaları (x86) \Microsoft Visual Studio 11.0\Team Araçlar\Performans araçları  
  
-   64-bit uygulamalar için varsayılan profil oluşturucu Araçlar dizindir:  
  
     *Sürücü*\Program dosyaları (x86) \Microsoft Visual Studio 11.0\Team Araçlar\Performans Tools\x64