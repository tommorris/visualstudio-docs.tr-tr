---
title: 'DA0026: Aşırı Çekirdek CPU süresi işleme | Microsoft Docs'
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
- vs.performance.rules.DA0026
- vs.performance.DA0026
- vs.performance.26
ms.assetid: 4cfc8a29-b29b-4a72-b386-03d8856fdf8a
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29eda10403e2d09f5a1bdf67911e1f2ae58bd9f0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682392"
---
# <a name="da0026-excessive-kernel-cpu-time-processing"></a>DA0026: Aşırı çekirdek CPU süresi işleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DA0026: aşırı Çekirdek CPU süresi işleme](https://docs.microsoft.com/visualstudio/profiling/da0026-excessive-kernel-cpu-time-processing).  
  
Kural Kimliği | TODO |  
| Kategori | Profil oluşturma araçları kullanım |  
| Profil oluşturma yöntemi | Örnekleme |  
| İleti | Çekirdek modu CPU zamanı görece yüksek miktarda ölçülmüştür. Kaynağı etkin syscall örneklemesiyle incelemeyi dikkate alın. |  
| Kural türü | Bilgi |  
  
 Örnekleme, .NET bellek ve kaynak çekişmesi yöntemleri kullanılarak profili, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 Çekirdek modunda yürütülen oranda CPU süresi, kullanıcı modunda harcanan süreyi aştı. Yeniden profil oluşturmayı hem de örnekleme yüksek çekirdek modu yürütme sürelerini nedenini belirlemek için sistem çağrıları (syscalls) sayısını göz önünde bulundurun.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Uygulama çekirdek modu yürütme için harcanan süre görece yüksek oranda daha fazla araştırma isteyebilirsiniz. Bir kullanıcı modu uygulaması için iş parçacığı veya işlem eşitleme temellerine bekleyin ya da sistem çağrıları yapmak için g/ç işlemleri gerçekleştirmek için çekirdek moduna geçer. Sistem çağrıları uygulama yapar ve sistem çağrıları örnek çağrı yığınlarını Topla seçeneğini belirlediğinizde, bunlardan sorumlu olan işlevleri temel tür araştırabilirsiniz.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Profili yeniden çalıştırın ve sistem çağrıları tabanlı örnekleri toplamak için seçeneğini uygulamanızı sağlayan sistem çağrıları tür araştırmak için. Bkz: [nasıl yapılır: örnekleme olayları seçin](../profiling/how-to-choose-sampling-events.md) daha fazla bilgi için IDE içinde profil oluşturma araçları çalıştırıyorsanız. Komut satırından profil oluşturma araçları çalıştırıyorsanız bkz **örnekleme aralığı seçenekleri** bölümünü [VSPerfCmd](../profiling/vsperfcmd.md) konuda Profil Araçları komut satırı araçları başvurusu.



