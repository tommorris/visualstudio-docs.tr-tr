---
title: Profil oluşturma yolunu belirterek Araçları komut satırı araçları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ccf7739a8efacacec3c48b47a59d6db6f6e8de8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634141"
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>Profil Oluşturma Araçları Komut Satırı Araçları Yolunu Belirtme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [profil oluşturma araçları komut satırı araçları yolunu belirtme](https://docs.microsoft.com/visualstudio/profiling/specifying-the-path-to-profiling-tools-command-line-tools).  
  
Yolu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Profil Araçları komut satırı araçları, PATH ortam değişkenine eklenmez. 32-bit bilgisayarlarda, tek bir dizinde araçlardır. Profil oluşturma araçlarından 64-bit bilgisayarlarda 32 bit ve 64-bit sürümleri vardır.  
  
## <a name="32-bit-computers"></a>32-bit bilgisayarlar  
 Varsayılan profil oluşturucu Araçlar Dizin 32-bit bilgisayarlarda, *sürücü*\Program Visual Studio 11.0\Team Araçlar\Performans araçları.  
  
## <a name="64-bit-computers"></a>64 bit bilgisayarlar  
 64-bit bilgisayarlarda, profili oluşturulan uygulamanın hedef platformu göre yolu belirtin.  
  
-   32-bit uygulamalar için varsayılan profil oluşturucu Araçlar dizindir:  
  
     *Sürücü*\Program dosyaları (x86) \Microsoft Visual Studio 11.0\Team Araçlar\Performans araçları  
  
-   64-bit uygulamalar için varsayılan profil oluşturucu Araçlar dizindir:  
  
     *Sürücü*\Program dosyaları (x86) \Microsoft Visual Studio 11.0\Team Araçlar\Performans Tools\x64



