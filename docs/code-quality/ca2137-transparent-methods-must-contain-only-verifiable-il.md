---
title: 'CA2137: Saydam yöntemler yalnızca doğrulanabilir IL içermelidir | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 83c366bb69e25d128b190a9ee8b192f13cf61013
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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