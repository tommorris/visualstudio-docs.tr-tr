---
title: 'CA1009: olay işleyicilerini doğru bildirin | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1009
- DeclareEventHandlersCorrectly
helpviewer_keywords:
- CA1009
- DeclareEventHandlersCorrectly
ms.assetid: ab65c471-1449-49d2-9896-7b9af74284b4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9d207bff88129cb9cc6769cc47ae6e70cbe74d1c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1009-declare-event-handlers-correctly"></a>CA1009: Olay işleyicilerini doğru bildirin
|||  
|-|-|  
|TypeName|DeclareEventHandlersCorrectly|  
|CheckId|CA1009|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Genel veya korumalı olayını işler bir temsilci türü ya da parametre adları dönüş doğru imza yok.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Olay işleyicisi yöntemleri iki parametre alır. İlk türünde <xref:System.Object?displayProperty=fullName> ve 'sender' olarak adlandırılır. Bu olayda oluşan nesnedir. İkinci parametre türünde <xref:System.EventArgs?displayProperty=fullName> ve 'e' olarak adlandırılır. Bu olay ile ilişkilendirilmiş olan verilerdir. Örneğin, her bir dosya açıldığında olay tetiklenir, olay verileri genellikle dosya adını içerir.  
  
 Olay işleyici yöntemleri bir değer vermemelidir. C# programlama dilini içinde bu dönüş türü tarafından belirtilir `void`. Olay işleyici birden fazla nesne birden çok yöntemleri çağırabilirsiniz. Yöntemleri bir değer döndürmesi izin verilmekteydi, birden çok dönüş değerleri her olay için ortaya çıkabilecek ve yalnızca son yönteminin çağrıldığı değeri kullanılabilir olacaktır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için imza, dönüş türü veya temsilci parametre adları düzeltin. Ayrıntılar için aşağıdaki örneğe bakın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, olayları işlemek için uygun bir temsilci gösterir. Bu olay işleyicisi tarafından çağrılan yöntemler tasarım yönergeleri belirtilen imza uyumlu. `AlarmEventHandler` temsilci türü adıdır. `AlarmEventArgs` Olay verileri için temel sınıfından türetilen <xref:System.EventArgs>, ve ayrı tutma alarm olay verileri.  
  
 [!code-cpp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CPP/ca1009-declare-event-handlers-correctly_1.cpp)]
 [!code-csharp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CSharp/ca1009-declare-event-handlers-correctly_1.cs)]
 [!code-vb[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/VisualBasic/ca1009-declare-event-handlers-correctly_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2109: Görünen olay işleyicileri gözden geçirin](../code-quality/ca2109-review-visible-event-handlers.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.EventArgs?displayProperty=fullName>   
 <xref:System.Object?displayProperty=fullName>   
 [Olaylar oluşturma ve işleme](/dotnet/standard/events/index)  