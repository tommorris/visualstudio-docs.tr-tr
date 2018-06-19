---
title: JavaScript IntelliSense
ms.date: 06/28/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [JavaScript]
- <reference> JavaScript XML tag
- JavaScript Code Editor
- XML code comments, JavaScript IntelliSense
- reference JavaScript XML tag
- JavaScript, IntelliSense
- code comments, JavaScript IntelliSense
- JavaScript, reference groups
- JavaScript Editor
- reference directives [JavaScript]
- JavaScript, XML documentation comments
- reference groups [JavaScript]
- JavaScript, reference directives
- IntelliSense [JavaScript], about
- IntelliSense extensibility [JavaScript]
- XML documentation comments [JavaScript]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 16e0efd8393d6324321a505247a3dad171a81a57
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103482"
---
# <a name="javascript-intellisense"></a>JavaScript IntelliSense

[!include[vs_dev15](../misc/includes/vs_dev15_md.md)] düzenleme deneyimi kutunun sağ dışında güçlü bir JavaScript sağlar. Bir temel TypeScript dil hizmeti tarafından açık, Visual Studio'nun daha zengin IntelliSense, modern JavaScript özellikleri için destek sağlar ve verimliliğin yeniden düzenleme, Tanıma Git gibi özellikleri ve daha fazlası.

> [!NOTE]
> JavaScript dil hizmetinde [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] dil hizmeti (çağrılan "Salsa") için yeni bir altyapısı kullanır. Ayrıntılar bu konuda yer alan ve bu da okuyabilirsiniz [blog gönderisi](https://blogs.msdn.microsoft.com/visualstudio/2016/11/28/more-productive-javascript-in-visual-studio-2017-rc). Yeni düzenleme deneyimi de çoğunlukla Visual Studio Code için geçerlidir. Bkz: [VS Code belgeleri](https://code.visualstudio.com/docs/languages/javascript) daha fazla bilgi için.

Visual Studio genel IntelliSense işlevselliği hakkında daha fazla bilgi için bkz: [kullanarak IntelliSense](../ide/using-intellisense.md).

## <a name="whats-new-in-the-javascript-language-service-in-includevsdev15miscincludesvsdev15mdmd"></a>' Deki JavaScript dil hizmetinin yenilikler nelerdir? [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

İtibariyle [!include[vs_dev15](../misc/includes/vs_dev15_md.md)], JavaScript IntelliSense, parametre ve üye listelerde çok daha fazla bilgi görüntüler.
Bu yeni bilgiler kodunuzu daha iyi anlamak için arka planda statik çözümlemesini kullanır TypeScript dil hizmeti tarafından sağlanır.
Bu bilgileri oluşturmak için çeşitli kaynaklardan typeScript kullanır:

- [Tür çıkarımı dayalı IntelliSense](#TypeInference)
- [JSDoc üzerinde temel IntelliSense](#JsDoc)
- [TypeScript bildirimi dosyalarını temel IntelliSense](#TsDeclFiles)
- [Tür tanımları otomatik alımını](#Auto)

<a name="TypeInference"></a>
### <a name="intellisense-based-on-type-inference"></a>Tür çıkarımı dayalı IntelliSense

JavaScript'te, çoğu zaman hiçbir açık tür bilgisi mevcut değil. Genellikle çevresindeki kodu bağlamı verilen bir türü bulmak oldukça kolaydır.
Bu işlem tür çıkarımı adı verilir.

Değişken veya özellik için genellikle, veya en son değer atama başlatmak için kullanılan değer türü türüdür.

```js
var nextItem = 10;
nextItem; // here we know nextItem is a number

nextItem = "box";
nextItem; // now we know nextItem is a string
```

Bir işlev için dönüş türü return deyimlerinde çıkarsanabileceği.

İşlev parametreleri için şu anda hiçbir çıkarım olmakla birlikte, bu sorunu çözmek için yolla JSDoc veya TypeScript kullanarak *. d.ts* dosyaları (sonraki bölümlere bakın).

Ayrıca, aşağıdakiler için özel çıkarım vardır:

- Yapıcı işlevi ve prototype özelliği atamaları kullanarak belirtilen "ES3-stil" sınıfları.
- Özelliği atamaları belirtilen CommonJS stili modülü düzenleri `exports` nesne veya atamaları `module.exports` özelliği.

```js
function Foo(param1) {
    this.prop = param1;
}
Foo.prototype.getIt = function () { return this.prop; };
// Foo will appear as a class, and instances will have a 'prop' property and a 'getIt' method.

exports.Foo = Foo;
// This file will appear as an external module with a 'Foo' export.
// Note that assigning a value to "module.exports" is also supported.
```

<a name="JsDoc"></a>
### <a name="intellisense-based-on-jsdoc"></a>JSDoc üzerinde temel IntelliSense

Burada tür çıkarımı sağlamaz istenen türü bilgileri (veya belgeleri desteklemek için), tür bilgilerini sağlanmalı açıkça JSDoc ek açıklamaları.  Örneğin, belirli bir tür kısmen bildirilen nesne vermek için kullanabileceğiniz `@type` etiketi aşağıda gösterildiği gibi:

```js
/**
 * @type {{a: boolean, b: boolean, c: number}}
 */
var x = {a: true};
x.b = false;
x. // <- "x" is shown as having properties a, b, and c of the types specified
```

İşlev parametreleri belirtildiği gibi hiçbir zaman algılanır. Ancak, JSDoc kullanarak `@param` ekleyebilirsiniz etiket türleri de işlev parametreleri.

```js
/**
 * @param {string} param1 - The first argument to this function
 */
function Foo(param1) {
    this.prop = param1; // "param1" (and thus "this.prop") are now of type "string".
}
```

Bkz: [JavaScript JSDoc desteği](https://github.com/Microsoft/TypeScript/wiki/JsDoc-support-in-JavaScript) şu anda desteklenen JsDoc ek açıklamaları.

<a name="TsDeclFiles"></a>
### <a name="intellisense-based-on-typescript-declaration-files"></a>TypeScript bildirimi dosyalarını temel IntelliSense

JavaScript ve TypeScript aynı dil hizmette şimdi tabanlı olduğundan, bunlar daha zengin bir biçimde etkileşemeyebilirsiniz. Bildirilen değerler için JavaScript IntelliSense gibi sağlanabilir bir *. d.ts* dosyası (bkz [TypeScript belgelerine](https://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html)), ve arabirimleri ve TypeScript içinde bildirilen sınıflar gibi türleri JsDoc açıklamaları türü olarak kullanmak için kullanılabilir.

Aşağıda, bir TypeScript tanım dosyası (üzerinden bir arayüzü) gibi türü bilgileri sağlayan basit bir örneği aynı projede JavaScript dosyaya gösteriyoruz (kullanarak bir `JsDoc` etiketi).

<img src="https://raw.githubusercontent.com/wiki/Microsoft/TypeScript/images/decl1.png" height="400" width="640" alt="TypeScript definition file" />

<a name="Auto"></a>
### <a name="automatic-acquisition-of-type-definitions"></a>Tür tanımları otomatik alımını

TypeScript dünyanın en popüler JavaScript kitaplıklarını tarafından açıklanan kendi API sahip *. d.ts* dosyaları ve bu tür tanımları için en yaygın depo açıktır [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped).

Varsayılan olarak, hangi JavaScript kitaplıklarını kullanın ve otomatik olarak karşıdan yüklenir ve buna karşılık gelen başvuru saptamak amacıyla Salsa dil hizmeti deneyecek *. d.ts* daha zengin sağlamak amacıyla kitaplığını açıklar dosyası IntelliSense. Kullanıcı klasörünün altındaki bir önbelleğine indirilen dosyaları *%LOCALAPPDATA%\Microsoft\TypeScript*.

> [!NOTE]
> Bu özellik **devre dışı** kullanıyorsanız, varsayılan olarak bir *tsconfig.json* yapılandırma dosyası, ancak Anahatlı olarak daha çok etkin aşağıda ayarlanabilir.

Şu anda npm indirilen bağımlılıklar için otomatik algılama çalışır (okuyarak *package.json* dosyası), Bower (okuyarak *bower.json* dosyası) ve bir listesiyle eşleşen gevşek dosyalarında projeniz için kabaca üst 400 en popüler JavaScript kitaplıklarını. Örneğin, *jquery 1.10.min.js* dosyayı projenize *jquery.d.ts* getirildi ve daha iyi düzenleme deneyimi sağlamak için yüklenir. Bu *. d.ts* dosya projeniz üzerinde olumsuz bir etkisi olacaktır.

Otomatik edinme kullanmak istemiyorsanız, aşağıda özetlendiği gibi bir yapılandırma dosyası ekleyerek devre dışı bırakın. Hala tanım dosyalarını kullanmak için doğrudan projenize içinde el ile yerleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [IntelliSense Kullanma](../ide/using-intellisense.md)