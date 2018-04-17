---
title: 'DA0026: Aşırı Çekirdek CPU süresi işleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0026
- vs.performance.DA0026
- vs.performance.26
ms.assetid: 4cfc8a29-b29b-4a72-b386-03d8856fdf8a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c3f7ab000e4f63c96c91038546145b85004bcc1f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="da0026-excessive-kernel-cpu-time-processing"></a>DA0026: Aşırı çekirdek CPU süresi işleme
|||  
|-|-|  
|Kural Kimliği|YAPILACAKLAR|  
|Kategori|Profil oluşturma araçları kullanım|  
|Profil oluşturma yöntemi|Örnekleme|  
|İleti|Çekirdek modu CPU zamanı görece yüksek miktarda cinsinden ölçülür. Etkin SysCall örnekleme ile kaynak araştırma göz önünde bulundurun.|  
|Kural türü|Bilgiler|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 Çekirdek modunda yürütüldü oranı CPU süresi, kullanıcı modunda harcanan süreyi aştı. Yeniden profil oluşturma ve yüksek çekirdek modu yürütme sürelerinin nedenini belirlemek için sistem çağrıları (syscalls) sayısı örnekleme göz önünde bulundurun.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Çekirdek modu yürütme uygulama harcanan süre görece yüksek oranını daha fazla araştırma isteyebilirsiniz. Bir kullanıcı modu uygulaması için iş parçacığı veya işlem eşitleme temelleri bekleyin ya da sistem çağrıları yapmak için g/ç işlemleri gerçekleştirmek için çekirdek moduna geçiş yapar. Uygulama yapar ve sistem çağrıları örnek çağrı yığınları toplamak için bu seçeneği seçtiğinizde, bunlar için sorumlu olan işlevler temel sistem çağrıları türlerini araştırabilirsiniz.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Profili yeniden çalıştırın ve sistem çağrıları dayalı örnekleri toplamak için seçeneğini belirleyin, uygulamanızın yapar sistem çağrıları türlerini araştırmak için. Bkz: [nasıl yapılır: örnekleme olayları seçin](../profiling/how-to-choose-sampling-events.md) daha fazla bilgi için IDE içinde profil oluşturma araçları çalıştırıyorsanız. Komut satırından profil oluşturma araçları çalıştırıyorsanız, bkz: **örnekleme aralığı seçenekleri** bölümünü [VSPerfCmd](../profiling/vsperfcmd.md) konuda profil oluşturma araçları komut satırı araçları başvurusu.