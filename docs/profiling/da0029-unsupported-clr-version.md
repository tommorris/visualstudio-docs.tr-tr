---
title: "DA0029: Desteklenmeyen CLR sürümü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dfc7d33396825263a5fd846c62426fa67509e0da
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="da0029-unsupported-clr-version"></a>DA0029: Desteklenmeyen CLR Sürümü
|||  
|-|-|  
|Kural Kimliği|DA0029|  
|Kategori|Profil oluşturma araçları kullanım|  
|Profil oluşturma yöntemi|Komut satırından profil oluşturma|  
|İleti|Toplama sırasında desteklenmeyen CLR sürümü algılandı. Yönetilen simgeleri doğru çözülebilir değildir.|  
|Kural türü|Bilgi.|  
  
## <a name="cause"></a>Sebep  
 Kullanan bir uygulama profili çalıştığınız [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)] profil oluşturma araçları tarafından desteklenmiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu uyarı, profil oluşturma araçları uygulamasında çalışan yönetilen kod için simgeleri çözümleyemez oluşur. Profil Araçları çalışmakta olan uygulamalar için yönetilen kod simgeleri çözümlenemiyor [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)].  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Yok.