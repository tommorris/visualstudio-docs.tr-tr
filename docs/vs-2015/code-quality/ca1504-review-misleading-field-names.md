---
title: 'CA1504: yanlış alan adlarını gözden geçirin | Microsoft Docs'
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
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 651d1897b06cd7d7d214fcfbfd25a3be13f60ed7
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42901107"
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504: Yanlış alan adlarını gözden geçirin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1504: yanlış alan adlarını gözden geçirin](https://docs.microsoft.com/visualstudio/code-quality/ca1504-review-misleading-field-names).

|||
|-|-|
|TypeName|ReviewMisleadingFieldNames|
|CheckId|CA1504|
|Kategori|Microsoft.Maintainability|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Örnek alan adı "kendisinin" ya da adı ile başlatılır bir `static` (`Shared` içinde [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) alanı "m_" ile başlar.

## <a name="rule-description"></a>Kural Tanımı
 "Kendisinin" ile başlayan alan adları ile statik verileri birden çok kullanıcı tarafından ilişkilendirilir. Benzer şekilde, "m_" ile başlayan alan adlarını, örneği (üye) verileri ile ilişkilidir. Daha kolay tutulan kodunu adları genel olarak kullanılan kuralları izlemelidir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için uygun önekle kullanarak alanı'nı yeniden adlandırın. Alternatif olarak, geçerli son eki ile ekleyerek veya kaldırarak kabul alan olun `static` değiştiricisi.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.



