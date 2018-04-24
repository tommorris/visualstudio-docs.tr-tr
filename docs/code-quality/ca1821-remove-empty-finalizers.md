---
title: 'CA1821: Boş sonlandırıcıları kaldırın'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ccd6ca16dc8a4ca2ce2f2883958ed82fa1c4b3ba
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: Boş sonlandırıcıları kaldırın
|||
|-|-|
|TypeName|RemoveEmptyFinalizers|
|CheckId|CA1821|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir tür boş, yalnızca temel tür sonlandırıcıyı çağıran veya koşullu olarak yöntemleri yayılan yalnızca çağıran bir sonlandırıcı uygular.

## <a name="rule-description"></a>Kural Tanımı
 Güncelleştirirken, nesne kullanım süresini izleme söz konusu olduğunda ek performans yükü nedeniyle sonlandırıcılardan kaçının. Nesne topladığı önce atık toplayıcı sonlandırıcıyı çalıştırın. Başka bir deyişle, iki koleksiyon nesnesi toplamak için gerekli olacaktır. Boş bir Sonlandırıcısı bu ek yükü bir fayda eklenen doğurur.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Boş sonlandırıcıyı kaldırın. Bir sonlandırıcı hata ayıklama için gereklidir, tüm sonlandırıcıyı içine `#if DEBUG / #endif` yönergeleri.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural gelen iletiyi bastırmak değil. Sonlandırma gizlemek için hata performansı düşürür ve hiçbir avantaj sağlar.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, kaldırılmalıdır boş bir Sonlandırıcısı, içine bir sonlandırıcı gösterir `#if DEBUG / #endif` yönergeleri ve kullandığı bir sonlandırıcı `#if DEBUG / #endif` yönergeleri doğru.

 [!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]