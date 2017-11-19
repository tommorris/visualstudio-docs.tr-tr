---
title: "CA2109: Görünen olay işleyicileri gözden geçirin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2109
- ReviewVisibleEventHandlers
helpviewer_keywords:
- ReviewVisibleEventHandlers
- CA2109
ms.assetid: 8f8fa0ee-e94e-400e-b516-24d8727725d7
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d558526f89b96c01e8bc7aba593d9c2b7f2654b0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2109-review-visible-event-handlers"></a>CA2109: Görünen olay işleyicileri gözden geçirin
|||  
|-|-|  
|TypeName|ReviewVisibleEventHandlers|  
|CheckId|CA2109|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Ortak veya korunan olay işleme yöntemi algılandı.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Dışarıdan görünür bir olay işleme yöntemi gözden geçirme gerektiren bir güvenlik sorunu gösterir.  
  
 Olay işleme yöntemleri kesinlikle gerekli olmadığı sürece maruz bırakılmamalıdır. İşleyici ve olay imzaları eşleştiği sürece gösterilen yöntemini çağıran bir temsilci türü, bir olay işleyicisi için herhangi bir olay eklenebilir. Olaylar, olası tüm kodu tarafından gerçekleştirilen ve yüksek oranda güvenilir bir sistem kodu yanıt olarak bir düğmeye tıklanması gibi kullanıcı eylemleri tarafından sık gerçekleştirilen. Güvenlik denetimi için bir olay işleme yöntemi ekleme, kod yöntemini çağıran bir olay işleyicisi kaydetme engellemez.  
  
 İsteğe bağlı bir olay işleyici tarafından başlatılan bir yöntem güvenilir bir şekilde koruyamaz. Güvenlik Yardım talep çağrı yığınında arayanlar inceleyerek güvenilmeyen arayanlar kod koruma. Olay işleyicinin yöntemleri çalıştırdığınızda, olay işleyicisi olaya ekleyen kod çağrı yığınındaki mutlaka mevcut değil. Bu nedenle, olay işleyicisi yöntemi çağrıldığında çağrı yığını arayanlar yalnızca yüksek oranda güvenilir. Bu, başarılı olması için olay işleyici yöntemiyle yapılan talepleri neden olur. Ayrıca, yöntemi çağrıldığında talep edilen izni uygulanan. Bu nedenlerle, olay işleme yöntemi gözden geçirdikten sonra bu kural ihlal düzelttikten değil riskini yalnızca belirlenebilir. Kodunuzu gözden geçirin, aşağıdaki noktaları dikkate alın:  
  
-   Olay işleyicisi tehlikeli veya Etkilenme izinleri sunduğundan veya yönetilmeyen kod izni gizleme gibi herhangi bir işlem yapıyor mu?  
  
-   İle herhangi bir zamanda yalnızca yüksek oranda çalışması için hangi güvenlik tehditleri için ve kodunuzdan yığında arayanlar güvenilir?  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için yöntem gözden geçirin ve aşağıdakileri değerlendirin:  
  
-   Genel olay işleme yöntemi yapabilirsiniz?  
  
-   Olay işleyicisi dışında tüm tehlikeli işlevselliği taşıyabilir miyim?  
  
-   Güvenlik isteğe uygulanan varsa, bu diğer herhangi bir biçimde gerçekleştirilebilir?  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Kodunuzu bir güvenlik tehdidi yol açmaz emin olmak için bu kural bir uyarıdan dikkatli güvenlik incelemesi sonra yalnızca engelleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, kötü amaçlı kod tarafından kötüye bir olay işleme yöntemini gösterir.  
  
 [!code-csharp[FxCop.Security.EventSecLib#1](../code-quality/codesnippet/CSharp/ca2109-review-visible-event-handlers_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName>   
 <xref:System.EventArgs?displayProperty=fullName>   
 [Güvenlik taleplerini](http://msdn.microsoft.com/en-us/324c14f8-54ff-494d-9fd1-bfd20962c8ba)