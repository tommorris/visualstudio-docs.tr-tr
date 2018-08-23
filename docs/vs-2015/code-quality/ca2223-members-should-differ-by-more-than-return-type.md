---
title: 'CA2223: Üyeler dönüş türünden daha fazla tarafından farklı olmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MembersShouldDifferByMoreThanReturnType
- CA2223
helpviewer_keywords:
- CA2223
- MembersShouldDifferByMoreThanReturnType
ms.assetid: eb326d9f-50d9-48cb-84be-d41c84a8fe09
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 37758f49e7dcaa7e41e873dd617e041a97c9e61e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632123"
---
# <a name="ca2223-members-should-differ-by-more-than-return-type"></a>CA2223: Üyeler dönüş türünden daha fazla farklı olmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2223: üyeler dönüş türünden daha fazla tarafından farklı](https://docs.microsoft.com/visualstudio/code-quality/ca2223-members-should-differ-by-more-than-return-type).  
  
TypeName | MembersShouldDifferByMoreThanReturnType |  
| Checkıd | CA2223 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 İki ortak veya korumalı üyeler dönüş türü dışında aynı imzalara sahip olduğunu.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Ortak dil çalışma zamanı aynı üyeler arasında ayrım yapmak için dönüş türleri kullanımına izin verse de, bu özellik ortak dil belirtimi ne de, bir .NET programlama dillerinin ortak özelliğidir. Üyeler yalnızca dönüş türüne göre farklı olduğunda, geliştiricilerin ve geliştirme araçları doğru bunları ayırt değil.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için böylece yalnızca, adları ve/veya parametre türleri dayalı olarak benzersizdirler veya üyeleri gösterme üyelerin tasarım değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, bu kuralı ihlal eden bir tür Microsoft Ara dilini (MSIL) gösterir. Bu kural C# veya Visual Basic .NET kullanarak ihlal olamaz dikkat edin.  
  
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



