---
title: 'CA2137: Saydam yöntemler yalnızca doğrulanabilir IL içermelidir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 536072f8dc019921fecd1fc6f53d255a1a0ae0d8
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551551"
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

## <a name="rule-description"></a>Kural açıklaması
 Bu kural, doğrulanamayan MSIL'yi (Microsoft Ara Dili) yürütmek için güvenlik saydam kodu tarafından girişimleri tetikler. Ancak kural tam IL doğrulayıcısı içermez ve MSIL doğrulamasının çoğu ihlalini yakalamak için buluşsal yöntemler kullanır.

 Kodunuzu yalnızca doğrulanabilir MSIL içeren emin olmak için çalıştırın [Peverify.exe (PEVerify aracı)](/dotnet/framework/tools/peverify-exe-peverify-tool) bütünleştirilmiş kodunuzda. PEVerify ile çalıştırma **/ saydam** hataya neden olur yalnızca doğrulanamayan saydam yöntemleri çıkışı sınırlar seçeneği. Varsa / saydam seçeneği kullanılmazsa, PEVerify doğrulanamayan kodu içermesi için izin verilen kritik yöntemleri de doğrular.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Bu kural ihlalini düzeltmek için yöntemi işaretlemek <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği veya doğrulanamaz kod kaldırın.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Bu örnekte yöntem doğrulanamaz kod kullanır ve ile işaretlenmelidir <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği.

 [!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../code-quality/codesnippet/CSharp/ca2137-transparent-methods-must-contain-only-verifiable-il_1.cs)]