---
title: 'CA1016: Derlemeleri AssemblyVersionAttribute ile işaretleme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkAssembliesWithAssemblyVersion
- CA1016
helpviewer_keywords:
- CA1016
- MarkAssembliesWithAssemblyVersion
ms.assetid: 4340aed8-d92b-4cde-a398-cb6963c6da5a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3080b5a45f61010f322ed183a8b5a7c23390de33
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31897424"
---
# <a name="ca1016-mark-assemblies-with-assemblyversionattribute"></a>CA1016: Derlemeleri AssemblyVersionAttribute ile işaretleme
|||
|-|-|
|TypeName|MarkAssembliesWithAssemblyVersion|
|CheckId|CA1016|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Derleme sürüm numarası yok.

## <a name="rule-description"></a>Kural Tanımı
 Derleme kimliğini aşağıdaki bilgilerden oluşur:

-   Derleme adı

-   Sürüm numarası

-   Kültür

-   Ortak anahtarı (kesin adlandırılmış derlemeler).

 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Sürüm numarasını bütünleştirilmiş benzersiz şekilde tanımlamak için ve kesin adlandırılmış derlemelerindeki bağlamak için kullanır. Sürüm numarası, sürüm ve yayımcı ilkesi ile birlikte kullanılır. Varsayılan olarak uygulamalar yalnızca oluşturulmuş derleme sürümlerini çalıştırır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için bir sürüm numarası derlemeye kullanarak eklemek <xref:System.Reflection.AssemblyVersionAttribute?displayProperty=fullName> özniteliği. Aşağıdaki örnekte bakın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan, üçüncü taraflar tarafından veya bir üretim ortamında kullanılan derlemeler için engelleme.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir derlemeye gösterir <xref:System.Reflection.AssemblyVersionAttribute> özniteliği uygulanmıştır.

 [!code-csharp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CSharp/ca1016-mark-assemblies-with-assemblyversionattribute_1.cs)]
 [!code-vb[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/VisualBasic/ca1016-mark-assemblies-with-assemblyversionattribute_1.vb)]
 [!code-cpp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CPP/ca1016-mark-assemblies-with-assemblyversionattribute_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.
 [Derleme sürümü oluşturma](/dotnet/framework/app-domains/assembly-versioning) [nasıl yapılır: Yayımcı ilkesi oluşturma](/dotnet/framework/configure-apps/how-to-create-a-publisher-policy)