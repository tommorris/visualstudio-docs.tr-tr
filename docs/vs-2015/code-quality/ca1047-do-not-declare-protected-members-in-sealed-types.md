---
title: 'CA1047: korumalı türlerde korunan üyeleri bildirmeyin | Microsoft Docs'
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
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8a9c61d3910a550f957b9940c1280f4fd2c17bdc
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900863"
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047: Korumalı türlerde korunan üyeleri bildirmeyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1047: korumalı türlerde korunan üyeleri bildirmeyin](https://docs.microsoft.com/visualstudio/code-quality/ca1047-do-not-declare-protected-members-in-sealed-types).

|||
|-|-|
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|
|CheckId|CA1047|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Genel bir tür `sealed` (`NotInheritable` Visual Basic'te) ve korumalı bir üye veya korumalı iç içe geçmiş bir tür bildirir. Bu kural ihlallerini raporlamaz <xref:System.Object.Finalize%2A> yöntemleri bu deseni izlemelidir.

## <a name="rule-description"></a>Kural Tanımı
 Türler, devralmasına erişebileceğiniz veya üyeyi geçersiz kılmak için korunan üyelerin türlerini bildirir. Tanımı gereği, yöntemi mühürlenmiş türler üzerindeki korunan anlamına çağrılamaz sealed türünden devralınamaz.

 C# Derleyici, bu hata için bir uyarı verir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için üye erişim düzeyini private olarak değiştirin ya da türü devralınabilir yapın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın. Geçerli durumunda türü bırakarak bakım sorunlarına neden olabilir ve herhangi bir avantaj sağlamaz.

## <a name="example"></a>Örnek
 Aşağıdaki örnek bu kuralı ihlal eden bir tür gösterir.

 [!code-csharp[FxCop.Design.SealedNoProtected#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.SealedNoProtected/cs/FxCop.Design.SealedNoProtected.cs#1)]
 [!code-vb[FxCop.Design.SealedNoProtected#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.SealedNoProtected/vb/FxCop.Design.SealedNoProtected.vb#1)]



