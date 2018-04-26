---
title: 'CA2103: Kesinlik temelli güvenliği gözden geçirin'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2103
- ReviewImperativeSecurity
helpviewer_keywords:
- CA2103
- ReviewImperativeSecurity
ms.assetid: d24fde71-bdf6-46c0-8965-9a73dc33c1aa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9a20dc939b305e3ec917f57bcd9f7cc8f8aa735f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2103-review-imperative-security"></a>CA2103: Kesinlik temelli güvenliği gözden geçirin
|||
|-|-|
|TypeName|ReviewImperativeSecurity|
|CheckId|CA2103|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir yöntem zorunlu güvenliği kullanır ve durum bilgileri veya dönüş değerlerini kullanarak izin oluşturursa, izin talebi etkin durumdayken değişebilir.

## <a name="rule-description"></a>Kural Tanımı
 Kesinlik temelli güvenliği yönetilen nesneleri öznitelikleri Eylemler ve izinler meta verilerini depolamak için kullandığı bildirimsel güvenliği karşılaştırılan kodu yürütme sırasında izinleri ve güvenlik eylemleri belirlemek için kullanır. Çünkü izin nesnesi durumunu ayarlamak ve çalışma zamanına kadar kullanılamaz bilgileri kullanarak güvenlik eylemleri seçin, kesinlik temelli güvenliği çok esnektir. İle birlikte, eylem etkin olduğu sürece, bir izin durumu durumda belirlemek için çalışma zamanı bilgileri değişmeden risk esneklik birlikte gelir.

 Bildirime dayanan güvenliği mümkün olduğunca kullanın. Bildirim temelli talepleri anlamak daha kolay.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 İzin durumu izni kullanılan sürece değiştirebilirsiniz bilgileri kalmaz emin olmak için kesinlik temelli güvenlik taleplerini gözden geçirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Verileri değiştirme izni bağlı değildir, bu kural bir uyarıdan gizlemek güvenlidir. Ancak, kesinlik temelli isteğe bağlı bildirim temelli eşdeğerine değiştirmek iyidir.

## <a name="see-also"></a>Ayrıca Bkz.
 [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines) [veri ve modelleme](/dotnet/framework/data/index)