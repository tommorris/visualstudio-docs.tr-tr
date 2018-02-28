---
title: "CA2137: Saydam yöntemler yalnızca doğrulanabilir IL içermelidir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3ec0dda4db164f4bd3368f1bb90c782f4aee6024
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2137-transparent-methods-must-contain-only-verifiable-il"></a>CA2137: Saydam yöntemler yalnızca doğrulanabilir IL içermelidir
|||  
|-|-|  
|TypeName|TransparentMethodsMustBeVerifiable|  
|CheckId|CA2137|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir yöntem, doğrulanamayan kodu içerir veya başvuruya göre bir tür döndürür.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, doğrulanamayan MSIL'yi (Microsoft Ara Dili) yürütmek için güvenlik saydam kodu tarafından girişimleri tetikler. Ancak kural tam IL doğrulayıcısı içermez ve MSIL doğrulamasının çoğu ihlalini yakalamak için buluşsal yöntemler kullanır.  
  
 Kodunuzu yalnızca doğrulanabilir MSIL içeren belirli olması amacıyla [Peverify.exe (PEVerify aracı)](/dotnet/framework/tools/peverify-exe-peverify-tool) derlemenizi üzerinde. PEVerify ile Çalıştır **/ saydam** hataya neden olur yalnızca doğrulanamaz saydam yöntemlerini çıkışı sınırlar seçeneği. Varsa / saydam seçeneği kullanılmaz, PEVerify doğrulanamayan kodu içeren izin önemli yöntemler de doğrular.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için yöntemiyle işaretlemek <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği veya doğrulanamayan kodu kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Bu örnekte bu yöntem doğrulanamayan kodu kullanır ve ile işaretlenmelidir <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği.  
  
 [!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../code-quality/codesnippet/CSharp/ca2137-transparent-methods-must-contain-only-verifiable-il_1.cs)]