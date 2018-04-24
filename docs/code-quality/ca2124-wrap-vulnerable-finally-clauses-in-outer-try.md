---
title: 'CA2124: Savunmasız sonunda yan tümcelerini dış deneme içine sarmalayın'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d46bc7bcfa8c1918091fabbbd759172259ea9ba6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124: Savunmasız sonunda yan tümcelerini dış deneme içine sarmalayın
|||
|-|-|
|TypeName|WrapVulnerableFinallyClausesInOuterTry|
|CheckId|CA2124|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 1.0 ve 1.1 sürümlerinde [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], bir ortak veya korumalı yöntemi içeren bir `try` / `catch` / `finally` bloğu. `finally` Blok güvenlik durumunu sıfırlamak için görünür ve içinde içine alınmamış bir `finally` bloğu.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural bulur `try` / `finally` 1.0 ve 1.1 sürümleri hedefleyen kodda engeller [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] çağrı yığınında mevcut kötü amaçlı bir özel durum filtreleri karşı savunmasız olun. Kimliğe bürünme gibi hassas işlemler try bloğunda oluşur ve bir özel durum, filtre önce yürütebilir `finally` bloğu. Kimliğe bürünme örneği için bu filtre Kimliğine bürünülen kullanıcı yürütmesine anlamına gelir. Filtreler yalnızca Visual Basic'te şu anda implementable.

> [!WARNING]
>  **Not** 2.0 ve sonraki sürümlerde [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], çalışma zamanı otomatik olarak koruyan bir `try` / `catch` /  `finally` sıfırlama oluşursa kötü amaçlı bir özel durum filtreleri, engelle doğrudan içinde yöntemi özel durum bloğu içerir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Sarmalanmamış yerleştirin `try` / `finally` bir dış try bloğundaki. Aşağıdaki ikinci örneğe bakın. Bu zorlar `finally` filtre kodundan önce yürütülecek.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="pseudo-code-example"></a>Sözde kod örneği

### <a name="description"></a>Açıklama
 Bu kural tarafından algılanan desen aşağıdaki sözde kodu gösterilmektedir.

### <a name="code"></a>Kod

```
try {
   // Do some work.
   Impersonator imp = new Impersonator("John Doe");
   imp.AddToCreditCardBalance(100);
}
finally {
   // Reset security state.
   imp.Revert();
}
```

## <a name="example"></a>Örnek
 Aşağıdaki sözde kod kodunuzu korumak ve bu kural karşılamak için kullanabileceğiniz düzeni gösterir.

```
try {
     try {
        // Do some work.
     }
     finally {
        // Reset security state.
     }
}
catch()
{
    throw;
}
```