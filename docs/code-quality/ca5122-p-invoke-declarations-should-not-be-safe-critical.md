---
title: CA5122 P-Invoke bildirimleri güvenli olmamalıdır kritik
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: f2581a6d-2a0e-40c1-b600-f5dc70909200
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e73af173dd7e82a139c204051c72480a50e38fa
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31920763"
---
# <a name="ca5122-pinvoke-declarations-should-not-be-safe-critical"></a>CA5122 P/Invoke bildirimleri güvenli kritik olmamalıdır
|||
|-|-|
|TypeName|PInvokesShouldNotBeSafeCriticalFxCopRule|
|CheckId|CA5122|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 P/Invoke bildirimi ile işaretlenmiş bir <xref:System.Security.SecuritySafeCriticalAttribute>:

```csharp
[assembly: AllowPartiallyTrustedCallers]

// ...
public class C
{
    [SecuritySafeCritical]
    [DllImport("kernel32.dll")]
    public static extern bool Beep(int frequency, int duration); // CA5122 - safe critical p/invoke
   }

```

 Bu örnekte, `C.Beep(...)` güvenlik güvenli kritik yöntemi olarak işaretlendi.

## <a name="rule-description"></a>Kural Tanımı
 Güvenlik duyarlı işlem gerçekleştirildiğinde yöntemler SecuritySafeCritical olarak işaretlenir ancak saydam mod kullanılarak da güvenli olur. Güvenlik saydamlık modelinin temel kurallarından biri saydam kod P/Invoke aracılığıyla yerel koda hiçbir zaman doğrudan çağırmaz. Bu nedenle, P/Invoke güvenlik güvenli kritik olarak işaretleme çağırmak için saydam kodu etkinleştirmez ve güvenlik çözümlemesi için yanıltıcıdır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 P/Invoke saydam kodu kullanılabilir yapmak için güvenlik güvenli kritik sarmalayıcı yöntemini kullanır:

```csharp
[assembly: AllowPartiallyTrustedCallers

class C
{
   [SecurityCritical]
   [DllImport("kernel32.dll", EntryPoint="Beep")]
   private static extern bool BeepPinvoke(int frequency, int duration); // Security Critical P/Invoke

   [SecuritySafeCritical]
   public static bool Beep(int frequency, int duration)
   {
      return BeepPInvoke(frequency, duration);
   }
}

```

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.