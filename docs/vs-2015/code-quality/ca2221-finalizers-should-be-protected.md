---
title: 'CA2221: Sonlandırıcılar korunmalıdır | Microsoft Docs'
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
- CA2221
- FinalizersShouldBeProtected
helpviewer_keywords:
- FinalizersShouldBeProtected
- CA2221
ms.assetid: bda03aee-4cce-45d3-907d-17f4ee030acc
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f8c65ca9abf97d33d7cdce68d3f055d8c7b3f964
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693324"
---
# <a name="ca2221-finalizers-should-be-protected"></a>CA2221: Sonlandırıcılar korunmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2221: sonlandırıcılar korunmalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca2221-finalizers-should-be-protected).  
  
TypeName | FinalizersShouldBeProtected |  
| Checkıd | CA2221 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Bir genel tür ailesi (korumalı) erişim belirtmeyen bir sonlandırıcıyı uygular.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Sonlandırıcılar aile erişim değiştiricisi kullanmalıdır. Bu kural, C#, Visual Basic ve Visual C++ Derleyicileri tarafından zorlanır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için Sonlandırıcı ailesi erişilebilir olacak şekilde değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Bu kural, tüm üst düzey bir .NET dilinde ihlal olamaz; Microsoft Ara dili yazıyorsanız ihlal.  
  
```  
// =============== CLASS MEMBERS DECLARATION ===================  
//   note that class flags, 'extends' and 'implements' clauses  
//          are provided here for information only  
  
.namespace UsageLibrary  
{  
  .class public auto ansi beforefieldinit FinalizeMethodNotProtected  
         extends [mscorlib]System.Object  
  {  
    .method public hidebysig instance void  
            Finalize() cil managed  
    {  
  
      // Code size       1 (0x1)  
      .maxstack  0  
      IL_0000:  ret  
    } // end of method FinalizeMethodNotProtected::Finalize  
  
    .method public hidebysig specialname rtspecialname  
            instance void  .ctor() cil managed  
    {  
      // Code size       7 (0x7)  
      .maxstack  1  
      IL_0000:  ldarg.0  
      IL_0001:  call       instance void [mscorlib]System.Object::.ctor()  
      IL_0006:  ret  
    } // end of method FinalizeMethodNotProtected::.ctor  
  
  } // end of class FinalizeMethodNotProtected  
} // end of namespace  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dispose Deseni](http://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)



