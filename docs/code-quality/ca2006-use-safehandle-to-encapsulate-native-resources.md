---
title: 'CA2006: Yerel kaynakları kapsamak için SafeHandle kullanın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
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
ms.openlocfilehash: b039dc1331ae3f8a47468289611e5bb9be32134d
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45549371"
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006: Yerel kaynakları kapsamak için SafeHandle kullanın
|||
|-|-|
|TypeName|UseSafeHandleToEncapsulateNativeResources|
|CheckId|CA2006|
|Kategori|Microsoft.Reliability|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Yönetilen kod kullandığı <xref:System.IntPtr> yerel kaynaklara erişmek için.

## <a name="rule-description"></a>Kural açıklaması
 Kullanım `IntPtr` yönetilen kodda olası bir güvenlik ve güvenilirlik sorunu belirtebilir. Tüm kullanımları `IntPtr` belirlemek için gözden geçirilmesi gereken olup olmadığını kullanımı bir <xref:System.Runtime.InteropServices.SafeHandle> , veya benzer teknoloji ve onun yerine gereklidir. Sorunları varsa gerçekleşir `IntPtr` bazı bellek, dosya tanıtıcısı veya yönetilen kod için kendi olarak değerlendirilir, bir yuva gibi yerel bir kaynak temsil eder. Yönetilen kod kaynak sahipse, bunu yapmak için bir hata kaynak sızıntısına neden olacağından, ayrıca ilişkili yerel kaynakları bırakmalıdır.

 Çok iş parçacıklı erişimi izni olup olmadığını böyle senaryolarda, güvenlik ve güvenilirlik sorunları da sunulacaktır `IntPtr` ve tarafından temsil edilen kaynak serbest bir şekilde `IntPtr` sağlanır. Bu sorunları, geri dönüştürme içeren `IntPtr` başka bir iş parçacığında eşzamanlı kullanım kaynak yapılırken kaynak sürüm değeri. Bu, burada bir iş parçacığı okuma veya yanlış kaynakla ilişkilendirilen veri yazma yarış durumlarını neden olabilir. Örneğin, bir işletim sistemi tanıtıcısı olarak türünüz depolar bir `IntPtr` ve kullanıcıların çağırın olanak tanıyan **Kapat** ve aynı anda ve eşitleme tür olmadan, tanıtıcı kullanan başka bir yöntem, kodunuzu bir tanıtıcı geri dönüştürme vardır. sorun oluştu.

 Bu tanıtıcı geri dönüştürme sorun veri bozulması ve genellikle, bir güvenlik açığına neden olabilir. `SafeHandle` ve kendi eşdüzey sınıfı <xref:System.Runtime.InteropServices.CriticalHandle> tür iş parçacığı oluşturma sorunları önlenebilir bir kaynak için yerel bir tanıtıcı yalıtılacak bir mekanizma sağlar. Ayrıca, kullanabileceğiniz `SafeHandle` ve kendi eşdüzey sınıfı `CriticalHandle` dikkatle yerel yöntemlere yapılan çağrılar üzerinden yerel tanıtıcı bir kopyasını içeren, yönetilen nesnelerin ömrünü denetlemek için diğer iş parçacığı oluşturma sorunları gibi. Bu durumda, genellikle çağrıları kaldırabilirsiniz `GC.KeepAlive`. Kullanırken gerçekleştirdiğiniz performansa `SafeHandle` ve daha düşük bir düzeyde `CriticalHandle`, dikkatli bir tasarım sık azaltılabilir.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?

Dönüştürme `IntPtr` kullanımı `SafeHandle` yerel kaynaklara erişimi güvenli bir şekilde yönetmek için. Bkz: <xref:System.Runtime.InteropServices.SafeHandle> başvurusu makalesinde örnekler.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında

Bu uyarıyı bastırmayın.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.IDisposable>