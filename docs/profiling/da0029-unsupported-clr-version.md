---
title: 'DA0029: Desteklenmeyen CLR sürümü | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f6ab40efbba692cfa85f14b750d3c853d1112704
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765745"
---
# <a name="da0029-unsupported-clr-version"></a>DA0029: Desteklenmeyen CLR sürümü
|||  
|-|-|  
|Kural Kimliği|DA0029|  
|Kategori|Profil oluşturma araçları kullanım|  
|Profil oluşturma yöntemi|Komut satırından profil oluşturma|  
|İleti|Toplama sırasında desteklenmeyen CLR sürümü algılandı. Yönetilen simgeleri doğru çözülebilir değildir.|  
|Kural türü|Bilgi.|  
  
## <a name="cause"></a>Sebep  
 Kullanan bir uygulama profili çalıştığınız [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)] profil oluşturma araçları tarafından desteklenmiyor.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Bu uyarı, profil oluşturma araçları uygulamasında çalışan yönetilen kod için simgeleri çözümleyemez oluşur. Profil Araçları çalışmakta olan uygulamalar için yönetilen kod simgeleri çözümlenemiyor [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)].  
  
## <a name="how-to-fix-violations"></a>İhlallerini düzeltmek nasıl  
 Yok.