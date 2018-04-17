---
title: 'CA2006: yerel kaynakları kapsamak için SafeHandle kullanın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2006
- UseSafeHandleToEncapsulateNativeResources
helpviewer_keywords:
- UseSafeHandleToEncapsulateNativeResources
- CA2006
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 0fdef78fdad92eb08012a474afff5c4c8c4d7ab8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006: Yerel kaynakları kapsamak için SafeHandle kullanın
|||  
|-|-|  
|TypeName|UseSafeHandleToEncapsulateNativeResources|  
|CheckId|CA2006|  
|Kategori|Microsoft.Reliability|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Yönetilen kod kullanan <xref:System.IntPtr> yerel kaynaklara erişmek için.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kullanımı `IntPtr` yönetilen kodda olası bir güvenlik ve güvenilirlik sorunu gösterebilir. Tüm kullanımlarını `IntPtr` belirlemek için gözden geçirilmesi gereken olup olmadığını kullanımını bir <xref:System.Runtime.InteropServices.SafeHandle> , veya benzer bir teknoloji, onun yerine gereklidir. Sorunları varsa gerçekleşeceği `IntPtr` bellek, bir dosya tanıtıcısı veya yönetilen kod için kendi olarak değerlendirilir, bir yuva gibi bazı yerel kaynak temsil eder. Yönetilen kod kaynak sahipse, bir Sağlanamaması kaynak sızıntısına neden olacağından, ilişkili yerel kaynaklar de serbest gerekir.  
  
 Birden çok iş parçacıklı erişime izin verilip verilmediğini gibi senaryolarda, güvenlik ve güvenilirlik sorunları da bulunacağı `IntPtr` ve tarafından temsil edilen kaynak yayınlama şekilde `IntPtr` sağlanır. Bu sorunları, geri dönüşüm içeren `IntPtr` kaynak eşzamanlı kullanımı başka bir iş parçacığında yapıldığı sırada kaynak sürüm değeri. Bu, burada bir iş parçacığı okuma veya yazma yanlış kaynakla ilişkili verileri yarış durumları neden olabilir. Örneğin, bir işletim sistemi tanıtıcısı olarak türünüz depolar bir `IntPtr` ve kullanıcıların her ikisi de çağrı olanak tanır **Kapat** ve aynı anda hem bir tür eşitleme olmadan o tanıtıcının kullanan başka bir yöntem, kodunuzun geri dönüştürme tanıtıcı sahiptir. sorun.  
  
 Sorun geri dönüştürme bu tanıtıcıyı veri bozulması ve genellikle, bir güvenlik açığı neden olabilir. `SafeHandle` ve onun eşdüzey sınıfını <xref:System.Runtime.InteropServices.CriticalHandle> tür iş parçacığı oluşturma sorunları önlenebilir böylece bir kaynak için yerel bir tanıtıcı kapsülleyen bir mekanizma sağlar. Ayrıca, kullanabileceğiniz `SafeHandle` ve onun eşdüzey sınıfını `CriticalHandle` dikkatle yerel yöntem çağrıları üzerinden yerel işleyici bir kopyasını içeren yönetilen nesnelerin ömrü denetlemek için diğer iş parçacığı oluşturma sorunları, örneğin,. Bu durumda, genellikle çağrıları kaldırabilirsiniz `GC.KeepAlive`. Tabi kullanırken performans genel gider thay `SafeHandle` ve daha düşük bir dereceye `CriticalHandle`, sık dikkatli tasarım azaltılabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Dönüştürme `IntPtr` kullanımı `SafeHandle` yerel kaynaklara erişimi güvenli bir şekilde yönetmek için. Bkz: <xref:System.Runtime.InteropServices.SafeHandle> örnekleri için başvuru konusu.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu uyarı engelleme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IDisposable>