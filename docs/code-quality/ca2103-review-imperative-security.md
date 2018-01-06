---
title: "CA2103: Kesinlik temelli güvenliği gözden | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2103
- ReviewImperativeSecurity
helpviewer_keywords:
- CA2103
- ReviewImperativeSecurity
ms.assetid: d24fde71-bdf6-46c0-8965-9a73dc33c1aa
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 051c94905e8d62d39ef837b6ef2520f345b8ca56
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
 [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines)   
 [Veri ve Modelleme](/dotnet/framework/data/index)