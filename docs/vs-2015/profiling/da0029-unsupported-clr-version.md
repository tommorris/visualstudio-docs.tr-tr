---
title: 'DA0029: Desteklenmeyen CLR sürümü | Microsoft Docs'
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
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df5deda533c21033d26af4b8dc08d98a5dafc583
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631704"
---
# <a name="da0029-unsupported-clr-version"></a>DA0029: Desteklenmeyen CLR Sürümü
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DA0029: Desteklenmeyen CLR sürümü](https://docs.microsoft.com/visualstudio/profiling/da0029-unsupported-clr-version).  
  
Kural Kimliği | DA0029 |  
| Kategori | Profil oluşturma araçları kullanım |  
| Profil oluşturma yöntemi | Komut satırından profil oluşturma |  
| İleti | Koleksiyon sırasında desteklenmeyen CLR sürümü algılandı. Yönetilen semboller değil çözebilir doğru. |  
| Kural türü | Bilgi. |  
  
## <a name="cause"></a>Sebep  
 Kullanan bir uygulama profili çalıştığınız [!INCLUDE[net_v11_long](../includes/net-v11-long-md.md)] profil oluşturma araçları tarafından desteklenmiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Profil oluşturma araçlarından uygulama içinde çalışan yönetilen kod için simgeleri çözme mümkün olmayacaktır. Bu uyarı oluşur. Profil oluşturma araçlarından çalışmakta olan uygulamalar için yönetilen kodu sembol çözümlenemiyor [!INCLUDE[net_v11_long](../includes/net-v11-long-md.md)].  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Yok.



