---
title: ": Ca2223 üyeler dönüş türünden daha farklı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MembersShouldDifferByMoreThanReturnType
- CA2223
helpviewer_keywords:
- CA2223
- MembersShouldDifferByMoreThanReturnType
ms.assetid: eb326d9f-50d9-48cb-84be-d41c84a8fe09
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4c72475c76a85216499a389d12f090ef302fc143
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="ca2223-members-should-differ-by-more-than-return-type"></a>CA2223: Üyeler dönüş türünden daha fazla farklı olmalıdır
|||  
|-|-|  
|TypeName|MembersShouldDifferByMoreThanReturnType|  
|CheckId|CA2223|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 İki ortak veya korumalı üyeler dönüş türü dışında birbirinin aynı olan imzalar sahiptir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Ortak dil çalışma zamanı dışında aynı üyeleri arasında ayırt etmek için dönüş türleri kullanımına izin verir ancak bu özellik ortak dil belirtimi değil veya .NET programlama dillerini ortak bir özellik değil. Üyeleri yalnızca dönüş türüne göre farklılık gösterir, geliştiriciler ve geliştirme araçları doğru bunlar arasında ayrım.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için böylece yalnızca, adları ve parametre türleri göre benzersiz veya üyeleri gösterme üyeleri tasarımını değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, Microsoft Ara dili (MSIL), bu kural ihlal eden bir tür gösterir. Bu kural C# veya Visual Basic kullanarak ihlal olamaz dikkat edin.  
  
```  
  
.namespace UsageLibrary  
{  
  .class public auto ansi beforefieldinit ReturnTypeTest  
         extends [mscorlib]System.Object  
  {  
    .method public hidebysig instance int32  
            AMethod(int32 x) cil managed  
    {  
      // Code size       6 (0x6)  
      .maxstack  1  
      .locals init (int32 V_0)  
      IL_0000:  ldc.i4.0  
      IL_0001:  stloc.0  
      IL_0002:  br.s       IL_0004  
  
      IL_0004:  ldloc.0  
      IL_0005:  ret  
    } // end of method ReturnTypeTest::AMethod  
  
    .method public hidebysig instance string  
            AMethod(int32 x) cil managed  
    {  
      // Code size       10 (0xa)  
      .maxstack  1  
      .locals init (string V_0)  
      IL_0000:  ldstr      "test"  
      IL_0005:  stloc.0  
      IL_0006:  br.s       IL_0008  
  
      IL_0008:  ldloc.0  
      IL_0009:  ret  
    } // end of method ReturnTypeTest::AMethod  
  
    .method public hidebysig specialname rtspecialname  
            instance void  .ctor() cil managed  
    {  
      // Code size       7 (0x7)  
      .maxstack  1  
      IL_0000:  ldarg.0  
      IL_0001:  call       instance void [mscorlib]System.Object::.ctor()  
      IL_0006:  ret  
    } // end of method ReturnTypeTest::.ctor  
  
  } // end of class ReturnTypeTest  
  
} // end of namespace UsageLibrary  
  
```