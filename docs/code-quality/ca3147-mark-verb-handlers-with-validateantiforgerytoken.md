---
title: 'CA3147: fiil işleyicileri ValidateAntiForgeryToken ile işaretleyin'
ms.date: 08/08/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 4b4369cfd310be9322d17b8bdbfe79880f2aa579
ms.sourcegitcommit: 96a6d1f16d06ca28d309d05b6e9fbd52f628cdbc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40009054"
---
# <a name="ca3147-mark-verb-handlers-with-validateantiforgerytoken"></a>CA3147: fiil işleyicileri ValidateAntiForgeryToken ile işaretleyin

|||
|-|-|
|TypeName|MarkVerbHandlersWithValidateAntiForgeryToken|
|CheckId|CA3147|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Bozucu olmayan|

## <a name="cause"></a>Sebep

Bir ASP.NET MVC denetleyici eylem yöntemi ile işaretlenmemiş <xref:Microsoft.AspNetCore.Mvc.ValidateAntiForgeryTokenAttribute?displayProperty=fullName>, ya da HTTP fiili gibi belirten bir özniteliği <xref:Microsoft.AspNetCore.Mvc.HttpGetAttribute?displayProperty=fullName> veya <xref:Microsoft.AspNetCore.Mvc.AcceptVerbsAttribute?displayProperty=fullName>.

## <a name="rule-description"></a>Kural açıklaması

ASP.NET MVC denetleyicisi tasarlarken siteler arası istek sahteciliği saldırılarına oluşturduğunu unutmayın. Siteler arası istek Sahtekarlığı Saldırısı, kimliği doğrulanmış bir kullanıcıdan, ASP.NET MVC denetleyicisine kötü amaçlı istek gönderebilirsiniz. Daha fazla bilgi için [ASP.NET MVC ve web sayfalarında XSRF/CSRF önleme](/aspnet/mvc/overview/security/xsrfcsrf-prevention-in-aspnet-mvc-and-web-pages).

Bu kural denetler, ASP.NET MVC denetleyici eylem yöntemleri ya da:

- Sahip <xref:Microsoft.AspNetCore.Mvc.ValidateAntiForgeryTokenAttribute> ve HTTP GET içermeden, izin verilen HTTP fiilleri belirtin.

- HTTP GET, izin verilen bir fiili belirtin.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?

- HTTP GET isteklerini işleyen ve potansiyel olarak zararlı yan etkileri yoksa ASP.NET MVC denetleyici eylemleri için ekleme bir <xref:Microsoft.AspNetCore.Mvc.HttpGetAttribute> yöntemi.

   Bir ASP.NET MVC HTTP GET'ini işler denetleyici eylemi ister ve hassas verileri değiştirme gibi zararlı yan etkileri varsa, uygulamanızı siteler arası istek sahteciliği saldırılarına karşı savunmasız.  Hassas işlemleri yalnızca HTTP POST, PUT ve DELETE isteklerini gerçekleştirmek için uygulamanızı yeniden tasarlamanız gerekir.

- HTTP POST işleyen, ASP.NET MVC denetleyici eylemleri için PUT veya DELETE istekleri, ekleme <xref:Microsoft.AspNetCore.Mvc.ValidateAntiForgeryTokenAttribute> ve izin verilen HTTP fiilleri belirten öznitelikler (<xref:Microsoft.AspNetCore.Mvc.AcceptVerbsAttribute>, <xref:Microsoft.AspNetCore.Mvc.HttpPostAttribute>, <xref:Microsoft.AspNetCore.Mvc.HttpPutAttribute>, veya <xref:Microsoft.AspNetCore.Mvc.HttpDeleteAttribute>). Ayrıca, çağırmanız gerekir <xref:Microsoft.AspNetCore.Mvc.ViewFeatures.HtmlHelper.AntiForgeryToken%2A?displayProperty=nameWithType> MVC görünümü veya Razor web sayfası. Bir örnek için bkz. [düzenleme metotlarını inceleme ve düzenleme görünümü](/aspnet/mvc/overview/getting-started/introduction/examining-the-edit-methods-and-edit-view).

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında

Bu, bu kuraldan bir uyarıyı bastırmak güvenli değil:

- ASP.NET MVC denetleyicisi eylemi zararlı yan etkileri vardır.

- Uygulamayı farklı bir yolla antiforgery belirteci doğrular.

## <a name="validateantiforgerytoken-attribute-example"></a>ValidateAntiForgeryToken öznitelik örneği

### <a name="violation"></a>İhlali

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        public ActionResult TransferMoney(string toAccount, string amount)
        {
            // You don't want an attacker to specify to who and how much money to transfer.

            return null;
        }
    }
}
```

### <a name="solution"></a>Çözüm

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        [HttpPost]
        [ValidateAntiForgeryToken]
        public ActionResult TransferMoney(string toAccount, string amount)
        {
            return null;
        }
    }
}
```

## <a name="httpget-attribute-example"></a>HttpGet öznitelik örneği

### <a name="violation"></a>İhlali

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        public ActionResult Help(int topicId)
        {
            // This Help method is an example of a read-only operation with no harmful side effects.
            return null;
        }
    }
}
```

### <a name="solution"></a>Çözüm

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        [HttpGet]
        public ActionResult Help(int topicId)
        {
            return null;
        }
    }
}
```
