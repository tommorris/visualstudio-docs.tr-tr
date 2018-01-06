---
title: "CA2205: Win32 API eşdeğerlerini yönetilen kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
helpviewer_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
ms.assetid: 1c65ab59-3e50-4488-a727-3969c7f6cbe4
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: ea1c408e524614009c8c12bda85afad397faf607
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2205-use-managed-equivalents-of-win32-api"></a>CA2205: Win32 API'sının yönetilen eşdeğerlerini kullanın
|||  
|-|-|  
|TypeName|UseManagedEquivalentsOfWin32Api|  
|CheckId|CA2205|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Bir platform çağırma yöntemi tanımlanır ve eşdeğer işlevselliğe sahip bir yöntem bulunmaktadır [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sınıf kitaplığı.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir platform çağırma yöntemi kullanılarak tanımlanır ve bir yönetilmeyen DLL işlevi çağırmak için kullanılan <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> özniteliği veya `Declare` Visual Basic anahtar sözcüğü. Hatalı tanımlanmış bir platform çağırma yöntemi için çalışma zamanı özel durumları, parametre ve dönüş değeri veri türleri ve çağırma kuralı ve karakter gibi hatalı alan belirtimleri eşleme hatalı misnamed bir işlev gibi sorunları nedeniyle yol açabilir ayarlayın. Mevcut ise, genellikle daha basit ve daha az hataya daha tanımlayın ve yönetilmeyen yöntemi doğrudan çağırmanız eşdeğer yönetilen yöntemini çağırmak içindir. Platform çağırma yöntemi çağırma ele alınması gereken ek güvenlik sorunları da yol açabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için yönetilen eşdeğerine çağrısıyla yönetilmeyen işlev çağrısı değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Önerilen değiştirme yöntemi gerekli işlevselliği sağlamıyorsa bu kural bir uyarıdan engelleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği bir platform kuralını ihlal yöntemi tanımı çağırır. Ayrıca, platform çağrıları yöntemini çağırmak ve eşdeğer Yönetilen yöntemi gösterilir.  
  
 [!code-csharp[FxCop.Usage.ManagedEquivalents#1](../code-quality/codesnippet/CSharp/ca2205-use-managed-equivalents-of-win32-api_1.cs)]
 [!code-vb[FxCop.Usage.ManagedEquivalents#1](../code-quality/codesnippet/VisualBasic/ca2205-use-managed-equivalents-of-win32-api_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1404: P/Invoke ardından hemen GetLastError Çağır](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)  
  
 [CA1060: Taşıma P/Invokes öğesini NativeMethods sınıfına](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)  
  
 [CA1400: P/Invoke giriş noktaları bulunmalıdır](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)  
  
 [CA1401: P/Invoke'lar görünür olmamalıdır](../code-quality/ca1401-p-invokes-should-not-be-visible.md)  
  
 [CA2101: P/Invoke dize bağımsız değişkenleri için sıralama belirtin](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)