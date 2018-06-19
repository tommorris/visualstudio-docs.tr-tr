---
title: 'CA2228: Yayımlanmamış kaynak biçimlerini yollamayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f444779fc5db725c090f96ec51a86d8427a14d17
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919187"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: Yayımlanmamış kaynak biçimlerini yollamayın
|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Kaynak dosyası bir sürümü kullanılarak oluşturuldu [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , şu anda desteklenmiyor.

## <a name="rule-description"></a>Kural Tanımı
 Yayın öncesi sürümleri kullanılarak oluşturulan kaynak dosyaların [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] .NET Framework'ün desteklenen sürümleri tarafından kullanılamayabilir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için desteklenen bir sürümünü kullanarak kaynak yapı [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]k.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.