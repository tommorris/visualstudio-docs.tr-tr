---
title: "CA1308: dizeleri büyük harfe normalleştirin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9064ca9861f609499971b9f5188f5b0006458c15
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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