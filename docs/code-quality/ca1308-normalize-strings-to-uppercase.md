---
title: 'CA1308: Dizeleri büyük harfe normalleştirin'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ffdc7e52b056ac9ab4d06e29d29b8cd5a7b06358
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308: Dizeleri büyük harfe normalleştirin
|||
|-|-|
|TypeName|NormalizeStringsToUppercase|
|CheckId|CA1308|
|Kategori|Microsoft.Globalization|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir işlem, bir dizeyi küçük harfli normalleştirir.

## <a name="rule-description"></a>Kural Tanımı
 Dizeler büyük harfe normalleştirilmeli. Küçük harfe, gidiş dönüş yapamazsınız karakterleri, küçük bir grubudur. Gidiş dönüş yapmaya karakterlerini bir yerel ayarını karakter verileri farklı temsil eden başka bir yerel ayar ve ardından için doğru şekilde dönüştürmek için anlamına gelir özgün karakterlerin dönüştürülen karakterlerinden alın.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Değiştirme dizelerini küçük harfe dönüştürmek ve böylece bu dizeler dönüştürülür işlemleri bunun yerine büyük harfe. Örneğin, değiştirme `String.ToLower(CultureInfo.InvariantCulture)` için `String.ToUpper(CultureInfo.InvariantCulture)`.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Sonuç (örneğin, kullanıcı Arabiriminde görüntülenirken) bağlı güvenlik kararı vermeden değil olduğunda bir uyarı iletisi bastırmak güvenlidir.

## <a name="see-also"></a>Ayrıca Bkz.
 [Genelleştirme Uyarıları](../code-quality/globalization-warnings.md)