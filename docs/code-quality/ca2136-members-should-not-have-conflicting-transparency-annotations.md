---
title: 'CA2136: Üyeler çakışan saydamlık ek açıklamalarına sahip olmamalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2127
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2136
helpviewer_keywords:
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2127
ms.assetid: ff5a1d18-7c52-4da5-8990-60be83a8ea81
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: afcfe25a9ff4541331ddfc35ebe86bbf884ef02e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136: Üyeler çakışan saydamlık ek açıklamalarına sahip olmamalıdır
|||
|-|-|
|TypeName|TransparencyAnnotationsShouldNotConflict|
|CheckId|CA2136|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bu kural türü üyesi ile işaretlendiğinde ateşlenir bir <xref:System.Security> üyesinin kapsayıcı güvenlik özniteliği daha farklı bir saydamlığı olan güvenlik özniteliği.

## <a name="rule-description"></a>Kural Tanımı
 Saydamlık nitelikleri, geniş kapsam kodlu öğelerden daha küçük kapsamlı öğelere uygulanır. Geniş kapsamı ile kod öğelerinin saydamlık öznitelikleri ilk öğeden kapsayan kod öğelerinin saydam öznitelikleri önceliklidir. Örneğin, ile işaretli bir sınıf <xref:System.Security.SecurityCriticalAttribute> özniteliği ile işaretlenmiş bir yöntem içeremez <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu ihlali düzeltmek için güvenlik özniteliğini alt kapsamdaki sahip code öğesini kaldırın veya onun özniteliğini içeren code öğesi ile aynı olacak şekilde değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıları bastırma değil.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, bir yöntem ile işaretlenmiş <xref:System.Security.SecuritySafeCriticalAttribute> ve özniteliği ile işaretlenmiş bir sınıf üyesi olduğu <xref:System.Security.SecurityCriticalAttribute> özniteliği. Güvenlik güvenli özniteliği kaldırılması gerekir.

 [!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../code-quality/codesnippet/CSharp/ca2136-members-should-not-have-conflicting-transparency-annotations_1.cs)]