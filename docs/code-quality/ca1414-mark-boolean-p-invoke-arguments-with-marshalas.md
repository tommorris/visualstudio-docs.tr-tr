---
title: 'CA1414: Boolean P-Invoke bağımsız değişkenlerini MarshalAs ile işaretleyin | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
helpviewer_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
ms.assetid: c0c84cf5-7701-4897-9114-66fc4b895699
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 16e561e04444fba7200c00f299cc775978829100
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1414-mark-boolean-pinvoke-arguments-with-marshalas"></a>CA1414: Boolean P/Invoke bağımsız değişkenlerini MarshalAs ile işaretleyin
|||  
|-|-|  
|TypeName|MarkBooleanPInvokeArgumentsWithMarshalAs|  
|CheckId|CA1414|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir platform çağırma yöntemi bildirimi içeren bir <xref:System.Boolean?displayProperty=fullName> parametresi veya dönüş değeri ancak <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName> özniteliği için parametre veya dönüş değeri uygulanmaz.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir platform yöntemi erişimleri yönetilmeyen kodu çağırma ve kullanılarak tanımlanmış `Declare` anahtar sözcük [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] veya <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. <xref:System.Runtime.InteropServices.MarshalAsAttribute> Yönetilen ve yönetilmeyen kodu arasında veri türlerine dönüştürmek için kullanılan hazırlama davranışı belirtir. Gibi pek çok basit veri türleri <xref:System.Byte?displayProperty=fullName> ve <xref:System.Int32?displayProperty=fullName>, tek bir gösterimi yönetilmeyen kodunda varsa ve hazırlama davranışlarını belirtimi gerektirmez; ortak dil çalışma zamanı otomatik olarak doğru davranış sağlar.  
  
 <xref:System.Boolean> Veri türüne sahip birden çok Beyanları yönetilmeyen kodunda. Zaman <xref:System.Runtime.InteropServices.MarshalAsAttribute> , hazırlama davranışı için varsayılan belirtilmemiş <xref:System.Boolean> veri türü <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>. Tüm durumlarda uygun olmayan bir 32 bit tamsayı budur. Yönetilmeyen yöntemi tarafından gerekli Boolean gösterimi belirledi ve uygun eşleşen <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>. UnmanagedType.Bool her zaman 4 bayt olan Win32 BOOL türü değil. C++ için UnmanagedType.U1 kullanılmalıdır `bool` veya diğer 1 bayt türleri.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için uygulama <xref:System.Runtime.InteropServices.MarshalAsAttribute> için <xref:System.Boolean> parametresi veya dönüş değeri. Özniteliğin değerini uygun ayarlayın <xref:System.Runtime.InteropServices.UnmanagedType>.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Varsayılan hazırlama davranışı uygun olsa bile davranışı açıkça belirtildiğinde kod daha kolay korunur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iki platform çağırma uygun ile işaretlenmiş yöntemleri gösterir <xref:System.Runtime.InteropServices.MarshalAsAttribute> öznitelikleri.  
  
 [!code-csharp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CSharp/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cs)]
 [!code-vb[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/VisualBasic/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.vb)]
 [!code-cpp[FxCop.Interoperability.BoolMarshalAs#1](../code-quality/codesnippet/CPP/ca1414-mark-boolean-p-invoke-arguments-with-marshalas_1.cpp)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1901: P/Invoke bildirimleri taşınabilir olmalıdır](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)  
  
 [CA2101: P/Invoke dize bağımsız değişkenleri için sıralama belirtin](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>   
 [Yönetilmeyen Kod ile Birlikte Çalışma](/dotnet/framework/interop/index)