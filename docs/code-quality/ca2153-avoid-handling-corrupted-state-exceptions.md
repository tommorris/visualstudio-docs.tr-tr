---
title: 'CA2153: Bozuk durum özel durumları işleme kaçının'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3ca36093afa0915352c6c6d90995bde99fb655c8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31922860"
---
# <a name="ca2153-avoid-handling-corrupted-state-exceptions"></a>CA2153: Bozuk durum özel durumları işleme kaçının

|||
|-|-|
|TypeName|AvoidHandlingCorruptedStateExceptions|
|CheckId|CA2153|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep

[Bozuk durumu özel durumları (CSE)](https://msdn.microsoft.com/magazine/dd419661.aspx) belleğin belirtmek Bozulması işleminize bulunmaktadır. Bir saldırganın bir yararlanma bozuk bellek bölgeye yerleştirebilirsiniz işleminin çökmesine izin vermek yerine bu yakalama güvenlik açıklarına neden olabilir.

## <a name="rule-description"></a>Kural Tanımı
 CSE bir işlemin durumunu olduğundan bozuk ve sistem tarafından yakalandı olduğunu gösterir. Yönteminizi uygun ile işaretlerseniz bozuk durumda senaryosunda, genel işleyicisi özel durumu yalnızca yakalar. `HandleProcessCorruptedStateExceptions` özniteliği. Varsayılan olarak, [ortak dil çalışma zamanı (CLR)](/dotnet/standard/clr) catch işleyicileri için CSE'ler çağırma kullanılamaz.

 Bu tür özel durumları yakalama olmadan çökmesine işlem kodu dahi günlük olarak en güvenli seçenek izin veriyor Bellek Bozulması hatalar yararlanmaya saldırganlar izin verebilirsiniz.

 Bu uyarı catch(exception) veya catch (özel durum belirtimi) gibi tüm özel durumları yakalar genel bir işleyici ile CSE'ler yakalama zaman tetikler.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu uyarıyı çözümlemek için aşağıdakilerden birini yapmalısınız:

 1. Kaldırma `HandleProcessCorruptedStateExceptions` özniteliği. Burada CSE'ler catch işleyicileri geçirilecek değil varsayılan çalışma zamanı davranışı döner.

 2. Bir özel durum türleri catch işleyicileri in preference of genel catch işleyicisi kaldırın.  Bu işleyici kodu bunları güvenli bir şekilde işleyebilir (çok nadir) varsayılarak CSE'ler içerebilir.

 3. CSE yeniden özel çağırana geçirilir ve çalışan işlemi bitiş sonuçlanacaktır sağlayan catch işleyicisinde atar.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="pseudo-code-example"></a>Sözde kod örneği

### <a name="violation"></a>İhlali
 Bu kural tarafından algılanan desen aşağıdaki sözde kodu gösterilmektedir.

```
[HandleProcessCorruptedStateExceptions]
//method to handle and log CSE exceptions
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (Exception e)
    {
        // Handle error
    }
}
```

### <a name="solution-1"></a>Çözüm 1
 HandleProcessCorruptedExceptions özniteliğini kaldırmadan özel durumları olmayan işlenmesi sağlar.

```
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (IOException e)
    {
        // Handle error
    }
    catch (UnauthorizedAccessException e)
    {
        // Handle error
    }
}
```

### <a name="solution-2"></a>Çözüm 2
 Genel catch işleyicisi kaldırın ve yalnızca bir özel durum türleri yakalayın.

```
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (IOException e)
    {
        // Handle error
    }
    catch (UnauthorizedAccessException e)
    {
        // Handle error
    }
}
```

### <a name="solution-3"></a>Çözüm 3
 Özel durum yeniden oluşturun.

```
void TestMethod1()
{
    try
    {
        FileStream fileStream = new FileStream("name", FileMode.Create);
    }
    catch (Exception e)
    {
        // Handle error
        throw;
    }
}
```