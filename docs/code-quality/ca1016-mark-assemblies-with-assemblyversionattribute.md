---
title: "CA1016: Derlemeleri AssemblyVersionAttribute işaretleyin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MarkAssembliesWithAssemblyVersion
- CA1016
helpviewer_keywords:
- CA1016
- MarkAssembliesWithAssemblyVersion
ms.assetid: 4340aed8-d92b-4cde-a398-cb6963c6da5a
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b716a809f1d2a5bcf73b9dda77b94d637b2e8493
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
 [Derleme sürümü oluşturma](/dotnet/framework/app-domains/assembly-versioning)   
 [Nasıl yapılır: Yayımcı İlkesi Oluşturma](/dotnet/framework/configure-apps/how-to-create-a-publisher-policy)