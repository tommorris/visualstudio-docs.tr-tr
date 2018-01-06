---
title: "CA1404: P-Invoke ardından hemen GetLastError Çağır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
helpviewer_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
ms.assetid: 52ae9eff-50f9-4b2f-8039-ca7e49fba88e
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c12d90fe9ae453f3b02c9e6c3f961e54084081aa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1404-call-getlasterror-immediately-after-pinvoke"></a>CA1404: P/Invoke ardından hemen GetLastError çağır
|||  
|-|-|  
|TypeName|CallGetLastErrorImmediatelyAfterPInvoke|  
|CheckId|CA1404|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 İçin bir çağrı yapılır <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A?displayProperty=fullName> yöntemi veya eşdeğer Win32 `GetLastError` işlevi ve hemen önce gelen çağrı değil bir platform yöntemini çağırma.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir platform yöntemi erişimleri yönetilmeyen kodu çağırma ve kullanılarak tanımlanmış `Declare` anahtar sözcük [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] veya <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> özniteliği. Genellikle, yönetilmeyen işlevleri başarısızlık durumunda, Win32 çağırmak `SetLastError` hatayla ilişkili bir hata kodu ayarlamak için işlevi. Win32 başarısız işleve çağıran çağırır `GetLastError` hata kodunu alabilir ve hatanın nedenini belirlemek için işlev. Hata kodu bir iş parçacığı başına temelinde korunur ve sonraki çağrısı tarafından üzerine `SetLastError`. Başarısız bir platform için bir çağrı çağırma sonra yöntem, yönetilen kod hata kodu çağırarak alabilirsiniz <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> yöntemi. Hata kodu, diğer yönetilen sınıf kitaplığı yöntemleri gelen iç çağrıları tarafından üzerine yazılabilir olmadığından `GetLastError` veya <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> hemen platform çağırma sonra yöntem çağrısı yöntemi'nin çağrılabilir.  
  
 Aşağıdaki çağrıları kural yoksayar platform çağrısı arasında oluştuğunda yönetilen üyeleri çağırma yöntemini ve çağrısı <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>. Bu üyeler hata değiştirmeyin kodu ve bazı platform başarısını belirlemek için yararlı olan çağırma yöntem çağrıları.  
  
-   <xref:System.IntPtr.Zero?displayProperty=fullName>  
  
-   <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>  
  
-   <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>  
  
-   <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için çağrısı taşımak <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> böylece platform çağrısı hemen izleyen yöntemini çağırma.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Yöntem çağrısının platform arasında kodu çağırma varsa bir uyarı bu kuraldan gizlemek güvenli ve <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> yöntem çağrısı olamaz açıkça veya örtük neden değiştirmek hata kodu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir yöntem ve kural karşılayan bir yöntemi gösterir.  
  
 [!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/VisualBasic/ca1404-call-getlasterror-immediately-after-p-invoke_1.vb)]
 [!code-csharp[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/CSharp/ca1404-call-getlasterror-immediately-after-p-invoke_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1060: Taşıma P/Invokes öğesini NativeMethods sınıfına](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)  
  
 [CA1400: P/Invoke giriş noktaları bulunmalıdır](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)  
  
 [CA1401: P/Invoke'lar görünür olmamalıdır](../code-quality/ca1401-p-invokes-should-not-be-visible.md)  
  
 [CA2101: P/Invoke dize bağımsız değişkenleri için sıralama belirtin](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)  
  
 [CA2205: Win32 API'sının yönetilen eşdeğerlerini kullanın](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)