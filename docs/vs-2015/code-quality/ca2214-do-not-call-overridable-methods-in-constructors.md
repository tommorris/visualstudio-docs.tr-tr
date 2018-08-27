---
title: 'CA2214: geçersiz kılınabilir yöntemleri oluşturucular içinde çağırmayın | Microsoft Docs'
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
- DoNotCallOverridableMethodsInConstructors
- CA2214
helpviewer_keywords:
- CA2214
- DoNotCallOverridableMethodsInConstructors
ms.assetid: 335b57ca-a6e8-41b4-a20e-57ee172c97c3
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8e813488e5e935c54a50238c3c993c6efcbf232c
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902249"
---
# <a name="ca2214-do-not-call-overridable-methods-in-constructors"></a>CA2214: Geçersiz kılınabilir yöntemleri oluşturucular içinde çağırmayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2214: geçersiz kılınabilir yöntemleri oluşturucular içinde çağırmayın](https://docs.microsoft.com/visualstudio/code-quality/ca2214-do-not-call-overridable-methods-in-constructors).

|||
|-|-|
|TypeName|DoNotCallOverridableMethodsInConstructors|
|CheckId|CA2214|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Bozucu olmayan|

## <a name="cause"></a>Sebep
 Mühürlenmemiş bir tür Oluşturucu, sınıfta tanımlanan sanal bir yöntemi çağırır.

## <a name="rule-description"></a>Kural Tanımı
 Sanal bir yöntem çağrıldığında yöntem gerçek tür çalışma zamanına kadar seçilmedi. Bir kurucu sanal bir yöntemi çağırdığında, yapıcı yöntemini çağıran örneği için değil yürütüldü mümkündür.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için türün sanal yöntemleri türün oluşturucular içinde çağırmayın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın. Sanal yöntem çağrısı ortadan kaldırmak için oluşturucu yeniden tasarlanması gerekir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kuralın ihlali etkisini gösterir. Test uygulama örneği oluşturur `DerivedType`, onun temel sınıfından neden olur (`BadlyConstructedType`) yürütmek için oluşturucu. `BadlyConstructedType`ın Oluşturucusu yanlış sanal yöntemini çağırır `DoSomething`. Çıktıda gösterildiği gibi `DerivedType.DoSomething()` yürütür ve bu nedenle önce yapar `DerivedType`'s Oluşturucusu yürütür.

 [!code-csharp[FxCop.Usage.CtorVirtual#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.CtorVirtual/cs/FxCop.Usage.CtorVirtual.cs#1)]
 [!code-vb[FxCop.Usage.CtorVirtual#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.CtorVirtual/vb/FxCop.Usage.CtorVirtual.vb#1)]

 Bu örnek aşağıdaki çıktıyı üretir.

 **Temel ctor çağrılıyor. ** 
 **DoSomething türetilen çağrılır - başlatılır? Hayır**
**arama türetilmiş ctor.**



