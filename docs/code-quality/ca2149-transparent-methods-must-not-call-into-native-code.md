---
title: 'CA2149: Saydam yöntemler yerel kod içine çağırmamalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2149
ms.assetid: 28951bd7-f3db-4871-99aa-bad68d1ead80
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: ba8d92d2ab453172b919f019acce0ea27e96bef3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2149-transparent-methods-must-not-call-into-native-code"></a>CA2149: Saydam metotlar yerel kod içine çağırmamalıdır
|||  
|-|-|  
|TypeName|TransparentMethodsMustNotCallNativeCode|  
|CheckId|CA2149|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Yerel bir işleve yöntemi saplama P/Invoke gibi aracılığıyla bir yöntemi çağırır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, örneğin P/Invoke gibi yerel kod içinde doğrudan çağıran herhangi bir saydam yöntemi tetikler. Bu kural ihlalleri neden bir <xref:System.MethodAccessException> Düzey 2 saydamlık modeli ve tam bir talep <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> düzey 1 saydamlık modeli.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için yerel kod ile çağıran yöntemi işaretlemek <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[FxCop.Security.CA2149.TransparentMethodsMustNotCallNativeCode#1](../code-quality/codesnippet/CSharp/ca2149-transparent-methods-must-not-call-into-native-code_1.cs)]