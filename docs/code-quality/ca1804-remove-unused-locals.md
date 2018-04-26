---
title: 'CA1804: Kullanılmayan yerel öğeleri kaldırın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1804
- RemoveUnusedLocals
helpviewer_keywords:
- RemoveUnusedLocals
- CA1804
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a9212d4fd11a13e9905d0327e3c4c91413e2a8d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1804-remove-unused-locals"></a>CA1804: Kullanılmayan yerel öğeleri kaldırın
|||
|-|-|
|TypeName|RemoveUnusedLocals|
|CheckId|CA1804|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir yöntem yerel bir değişken bildiren ancak dışında değişkeni büyük olasılıkla bir atama deyimi alıcısı olarak kullanmaz. Çözümleme için bu kural tarafından test edilmiş derleme hata ayıklama bilgileri ile oluşturulması ve ilişkili program veritabanı (.pdb) dosyası kullanılabilir olması gerekir.

## <a name="rule-description"></a>Kural Tanımı
 Kullanılmayan yerel değişkenler ve gereksiz atamaların derleme boyutunu artırır ve performansı düşürür.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için kaldırmak veya yerel değişken kullanın. C# Derleyici, birlikte olduğuna dikkat edin [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] kullanılmayan yerel değişkenler kaldırır zaman `optimize` seçeneği etkinleşir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Değişkeni yayılan derleyici ise bir uyarı bu kuraldan engelleyin. Performans ve kod bakımı birincil sorunları değilse de bu kuraldan bir uyarı bastırma veya kuralı devre dışı bırakmak için güvenli değildir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, birkaç kullanılmayan yerel değişkenleri gösterir.

 [!code-vb[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/VisualBasic/ca1804-remove-unused-locals_1.vb)]
 [!code-csharp[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/CSharp/ca1804-remove-unused-locals_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1809: Aşırı yerel öğelerden kaçın](../code-quality/ca1809-avoid-excessive-locals.md)

 [CA1811: Çağrılmayan özel kodlardan kaçının](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: Örneklendirilmemiş iç sınıflardan kaçının](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: Kullanılmayan parametreleri gözden geçir](../code-quality/ca1801-review-unused-parameters.md)