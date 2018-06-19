---
title: 'CA1504: Yanlış alan adlarını gözden geçirin'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1457390b523af45b5e3b23a3420cba830f45cee5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915088"
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504: Yanlış alan adlarını gözden geçirin
|||
|-|-|
|TypeName|ReviewMisleadingFieldNames|
|CheckId|CA1504|
|Kategori|Microsoft.Maintainability|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir örnek alanın adını başlatır "s_" veya adı ile bir `static` (`Shared` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) alanı "m_" ile başlar.

## <a name="rule-description"></a>Kural Tanımı
 "S_" ile başlayan alan adları statik verilerle birden çok kullanıcı tarafından ilişkilendirilir. Benzer şekilde, "m_" ile başlayan alan adlarını örneği (üye) verileriyle ilişkilendirilir. Daha kolay tutulan kodunu adları genellikle kullanılan kuralları izlemelidir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için uygun önek kullanarak alanı'nı yeniden adlandırın. Alternatif olarak, geçerli sonekiyle ekleyerek veya kaldırarak kabul alan yapmak `static` değiştiricisi.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.