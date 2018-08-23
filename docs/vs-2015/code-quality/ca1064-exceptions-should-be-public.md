---
title: 'CA1064: Özel durumlar genel olmamalıdır | Microsoft Docs'
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
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7a40a832ddd9342896105c6c1ede8fdcbf2266a9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687592"
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064: Özel durumlar genel olmamalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1064: özel durumlar genel](https://docs.microsoft.com/visualstudio/code-quality/ca1064-exceptions-should-be-public).  
  
TypeName | ExceptionsShouldBePublic |  
| Checkıd | CA1064 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Doğrudan genel olmayan özel durum türetilen <xref:System.Exception>, <xref:System.SystemException>, veya <xref:System.ApplicationException>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir iç özel durum yalnızca kendi iç kapsamı içinde görülebilir. İç kapsam dışında kalan özel durumlardan sonra, sadece basit istisnalar istisna yakalamak için kullanılabilir. İç özel durum öğesinden devralınan <xref:System.Exception>, <xref:System.SystemException>, veya <xref:System.ApplicationException>, harici kod özel durum ne olduğunu bilmek yeterli bilgiye sahip değildir.  
  
 Ancak, kodu daha sonra bir iç özel durum için temel olarak kullanılan genel bir özel durum varsa, çıkış kodu daha ayrıntılı temel özel durum ile akıllı bir şey mümkün olacaktır varsaymak uygun olur. Genel özel durum T:System.Exception, T:System.SystemException veya T:System.ApplicationException sağlanır değerinden daha fazla bilgi olacaktır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Özel durum Genel hale getirmek ya da iç özel durum olmayan genel bir özel durumdan türetilen <xref:System.Exception>, <xref:System.SystemException>, veya <xref:System.ApplicationException>.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Kendi iç kapsamı içinde özel durum yakalandı, tüm durumlarda eminseniz bu kuraldan bir iletiyi gösterme.  
  
## <a name="example"></a>Örnek  
 Bu kural, çünkü özel durum sınıfı doğrudan özel durumdan türetilen ve iç ilk örnek yöntem üzerinde FirstCustomException tetikler. Sınıfı ayrıca doğrudan özel durumdan türetilen olsa da, sınıfın genel olarak bildirildiğinden, kural SecondCustomException sınıfında etkinleşmez. Doğrudan türemediği üçüncü sınıfı kuralı da başlatılmıyor <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, veya <xref:System.ApplicationException?displayProperty=fullName>.  
  
 [!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.design.exceptionsshouldbepublic.ca1064/cs/ca1064 - exceptionsshouldbepublic.cs#1)]



