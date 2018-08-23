---
title: ': COM kayıt yöntemleri ca1410 eşleşmelidir | Microsoft Docs'
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
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3fb0ce9e0b2c8440b452c895d23c46a7f4350bbc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630531"
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410: COM kayıt yöntemleri eşleşmelidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1410: COM kayıt yöntemleri eşleşen](https://docs.microsoft.com/visualstudio/code-quality/ca1410-com-registration-methods-should-be-matched).  
  
TypeName | ComRegistrationMethodsShouldBeMatched |  
| Checkıd | CA1410 |  
| Kategori | Microsoft.Interoperability|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 İle işaretlenmiş bir yöntem bir tür bildirir <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> özniteliği ancak ile işaretlenmiş bir yöntemi bildirmez <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> özniteliği, ya da tam tersi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Oluşturulacak Bileşen Nesne Modeli (COM) istemciler için bir [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] türü, tür önce kayıtlı olması gerekir. Varsa, ile işaretlenmiş bir yöntemi <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> özniteliği, kullanıcı tarafından belirtilen kodu çalıştırmak için kayıt işlemi sırasında çağrılır. Karşılık gelen ile işaretlenmiş bir yöntemi <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> özniteliği, kayıt yöntemini işlemleri tersine çevirmek için kayıt silme işlemi sırasında çağrılır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için karşılık gelen bir kayıt veya silme yöntemi ekleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir. Açıklamalı kod düzeltme ihlali gösterir.  
  
 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComRegistration/cs/FxCop.Interoperability.ComRegistration.cs#1)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.ComRegistration/vb/FxCop.Interoperability.ComRegistration.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1411: COM kayıt yöntemleri görünebilir olmamalıdır](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>   
 [Derlemeleri COM ile kaydetme](http://msdn.microsoft.com/library/87925795-a3ae-4833-b138-125413478551)   
 [Regasm.exe (Derleme Kayıt Aracı)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb)



