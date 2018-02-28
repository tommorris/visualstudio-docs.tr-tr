---
title: "CA2149: Saydam yöntemler yerel kod içine çağırmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2149
ms.assetid: 28951bd7-f3db-4871-99aa-bad68d1ead80
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9377a30d2fc56c8acef16b6bcf1187d0e9fa8741
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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