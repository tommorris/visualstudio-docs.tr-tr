---
title: "CA1410: COM kayıt yöntemleri eşleştirilmesini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 660524e4198a06eb6a7e3d627e28acaa721bf8c2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410: COM kayıt yöntemleri eşleşmelidir
|||  
|-|-|  
|TypeName|ComRegistrationMethodsShouldBeMatched|  
|CheckId|CA1410|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir tür ile işaretli bir yöntem bildirir <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> özniteliği ancak ile işaretli bir yöntem bildirmiyor <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> özniteliği veya tam tersi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bileşen Nesne Modeli (COM) istemcilerin oluşturmak bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] türü, türü önce kaydedilmesi gerekir. Kullanılabilirse, ile işaretli bir yöntem <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> öznitelik kullanıcı tarafından belirtilen kodu çalıştırmak için kayıt işlemi sırasında çağrılır. İle işaretlenen karşılık gelen bir yöntemi <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> özniteliği kayıt yöntemi operations tersine çevirmek için kayıt silme işlemi sırasında çağrılır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için karşılık gelen bir kayıt veya silme yöntemi ekleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir. Açıklamalı kod ihlali için düzeltmeyi gösterir.  
  
 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1411: COM kayıt yöntemleri görünebilir olmamalıdır](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [Derlemeleri COM ile kaydetme](/dotnet/framework/interop/registering-assemblies-with-com)   
 [Regasm.exe (Derleme Kayıt Aracı)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)