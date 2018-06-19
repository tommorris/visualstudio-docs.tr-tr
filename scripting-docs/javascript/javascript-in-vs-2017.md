---
title: Visual Studio'da JavaScript | Microsoft Docs
ms.custom: ''
ms.date: 04/10/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 74dca14c-5071-416f-a92b-d09f95e3dfb8
caps.latest.revision: 1
author: bowdenk7
ms.author: wilkelly
manager: ghogen
ms.openlocfilehash: 5b13f01a1a5ba13503932c73aef3a4825115497e
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
ms.locfileid: "29753303"
---
# <a name="javascript-in-visual-studio-2017"></a>Visual Studio 2017 JavaScript'te

JavaScript, Visual Studio birinci sınıf bir dildir. Visual Studio IDE'de JavaScript kodu yazarken standart düzenleme yardımlarının (kod parçacıkları, IntelliSense, vb.) çoğunu veya tümünü kullanabilirsiniz. Birçok uygulama türleri ve Hizmetleri için JavaScript kodu yazabilirsiniz.

## <a name="ES6"></a> ECMAScript 2015 (açıklamalarıyla ES6) için ve ötesinde desteği

Visual Studio sözdizimi ECMAScript 2015/2016 gibi ECMAScript dil güncelleştirmeleri için artık desteklemektedir.

### <a name="what-is-ecmascript-2015"></a>ECMAScript 2015 nedir?

JavaScript bir programlama dili hala gelişen ve [TC39](http://www.ecma-international.org/memento/TC39.htm) komitesi güncelleştirmeler yapmak için sorumludur.
ECMAScript 2015 yararlı yeni sözdizimi ve işlevsellik getirir JavaScript dil için bir güncelleştirmedir. Açıklamalarıyla ES6 özellikleri derin Dalış için kullanıma [bu](http://es6-features.org) başvuru sitesi.

Ek destek ECMAScript 2015 için Visual Studio ayrıca ECMAScript 2016 destekler ve en ECMAScript gelecekteki sürümleri için destek gerekir. TC39 ve en son değişiklikleri ECMAScript'te karşılamak üzere, işlerini izleyin [github](https://github.com/tc39).

### <a name="transpile-javascript"></a>Transpile JavaScript

Bir ortak JavaScript ile en son açıklamalarıyla ES6 + dil özellikleri daha üretken olmanıza yardımcı olur, ancak çalışma zamanı ortamınızı (genellikle tarayıcıları) henüz bu yeni özellikleri desteklemeyen için kullanmak istediğiniz bir sorundur. Bu, ya da hangi tarayıcılar izlemek zorunda (can sıkıcı olabilir) hangi özellikleri desteklemek veya açıklamalarıyla ES6 + kodunuzu, hedef çalışma zamanları (genellikle ES5) anladığınızı sürümüne dönüştürmek için bir yönteme ihtiyacınız anlamına gelir. Çalışma zamanı genellikle "transpiling" adlandırılan anlar bir sürüme kodunuzu dönüştürülüyor.

Böylece en verimli hale getirir kod yazmayı ancak hala herhangi bir platformda kodunuzu çalıştırmak TypeScript anahtar özelliklerini özelliği transpile açıklamalarıyla ES6 + kodunu ES5 veya ES3 biridir. Çünkü JavaScript'te [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] kullandığı aynı dilde hizmet TypeScript, çok ES5 transpilation açıklamalarıyla ES6 + özelliklerden yararlanabilirsiniz.

Transpilation ayarlanabilir önce bazı yapılandırma seçenekleri anlayış gereklidir.
TypeScript ile yapılandırılmış bir `tsconfig.json` dosyası.
Böyle bir dosya olmaması durumunda bazı varsayılan değerler kullanılır.
Bu varsayılan uyumluluk açısından farklı bir bağlamda yalnızca burada JavaScript dosyaları (ve isteğe bağlı olarak `.d.ts` dosyaları) yok.
JavaScript dosyalarını derlemek için bir `tsconfig.json` dosya eklenmelidir ve bu seçeneklerden bazısı açıkça ayarlanmış olmalıdır.

Tsconfig dosyası için gereken ayarlar aşağıdaki gibidir:

 - `allowJs`: Bu değer ayarlamak `true` JavaScript dosyaları tanınmıyor. Varsayılan değer `false`, çünkü TypeScript JavaScript derler ve derleyici sadece derlenmiş dosyalar içermemesi gerekir.
 - `outDir`: Bu değer verilmiş JavaScript dosyaları algılanmaz ve projeye dahil edebilmesi projesinde yer almayan bir konuma ayarlamanız gerekir (bkz: `exclude`).
 - `module`: Modüller kullanıyorsanız, bu ayar derleyici verilmiş kod kullanması gereken hangi modül biçimi söyler. (örneğin `commonjs` düğümü veya paketleyicileri Browserify gibi).
 - `exclude`: Bu ayar projede içermeyecek şekilde klasörleri belirtir.
 Proje olmayan klasörleri gibi yanı sıra çıkış konumu `node_modules` veya `temp`, bu ayar eklenmelidir.
 - `enableAutoDiscovery`: Bu ayar, daha önce özetlendiği gibi otomatik algılama ve tanım dosyalarını indirme sağlar.
 - `compileOnSave`: Bu ayar, Visual Studio'da herhangi bir kaynak dosyası kaydedildiğinde derlenir, derleyici söyler.
 - `typeAcquisition`: Bu ayarları kümesini otomatik türü alma davranışını denetleyen (daha ayrıntılı olarak açıklayın [Bu bölümde](https://docs.microsoft.com/en-us/visualstudio/ide/javascript-intellisense#Auto))

JavaScript dosyaları CommonJS modüllerle dönüştürmek ve bunları yerleştirmek için bir `./out` klasörü, aşağıdakileri kullanabilirsiniz `tsconfig.json` dosyası:

```json
{
  "compilerOptions": {
    "module": "commonjs",
    "allowJs": true,
    "outDir": "out"
  },
  "exclude": [
    "node_modules",
    "wwwroot",
    "out"
  ],
  "compileOnSave": true,
  "typeAcquisition": {
    "enable": true
  }
}
```

Yerinde, bir kaynak dosya ayarlarıyla (`./app.js`) var ve birkaç ECMAScript 2015 dil özellikleri gibi yer:

```js
import {Subscription} from 'rxjs/Subscription';  // ES6 import

class Foo {  // ES6 Class
    sayHi(name) {
        return `Hi ${name}, welcome to Salsa!`;  // ES6 template string
    }
}

export let sqr = x => x * x;  //ES6 export, let, and arrow function
export default Subscription;  //ES6 default export
```

Bir dosya yayılan sonra `./out/app.js` hedefleme ECMAScript aşağıdaki gibi görünen 5 (varsayılan):

```js
"use strict";
var Subscription_1 = require('rxjs/Subscription');
var Foo = (function () {
    function Foo() {
    }
    Foo.prototype.sayHi = function (name) {
        return "Hi " + name + ", welcome to Salsa!";
    };
    return Foo;
}());
exports.sqr = function (x) { return x * x; };
Object.defineProperty(exports, "__esModule", { value: true });
exports.default = Subscription_1.Subscription;
```

## <a name="better-intellisense"></a>Daha iyi IntelliSense

JavaScript IntelliSense içinde [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] şimdi görüntü parametreleri ve üye listelerini çok daha fazla bilgi sağlar. Bu yeni bilgiler kodunuzu daha iyi anlamak için arka planda statik çözümlemesini kullanır TypeScript dil hizmeti tarafından sağlanır. Yeni IntelliSense deneyimi hakkında daha fazla bilgi ve nasıl çalıştığı okuyabilirsiniz [burada](/visualstudio/ide/javascript-intellisense/).

## <a name="JSX"></a> JSX sözdizimi desteği

JavaScript'te [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] JSX söz dizimi zengin desteğe sahiptir. JSX içinde JavaScript dosyaları HTML etiketleri izin veren bir sözdizimi kümesidir.

Tanımlanan bir tepki bileşeni aşağıda gösterilmiştir `comps.tsx` TypeScript dosya ve ardından gelen kullanılan bu bileşen `app.jsx` dosya, IntelliSense ile tam tamamlamalar ve JSX ifadeleri içindeki belgelerde.
TypeScript gerekmeyen Burada, belirli Bu örnek yalnızca bazı TypeScript kod de içerecek şekilde gerçekleşir.

<img src="./media/react.png" height="500" width="640"/>

> [!NOTE]
> JSX söz dizimini tepki vermek için dönüştürmek için çağrıları, ayar `"jsx": "react"` eklenmeli `compilerOptions` içinde `tsconfig.json` dosya.

Öğesinde oluşturulan JavaScript dosyası '. / out/app.js derleme sırasında kodunun içerebilir:

```js
"use strict";
var comps_1 = require('./comps');
var x = React.createElement(comps_1.RepoDisplay, {description: "test"});
```

## <a name="configure-your-javascript-project"></a>JavaScript projenizi yapılandırın

Dil hizmeti, IntelliSense sonuçlar döndürecek ve diğer düzenleme özellikleri sağlamak için gerçekten çalıştırmadan kaynak kodunuzu çözümler anlamına gelir statik çözümleme tarafından desteklenir.
Bu nedenle, daha büyük miktar ve dosyaların boyutunu proje içeriğiniz, daha fazla bellek dahil ve CPU Çözümleme sırasında kullanılır.
Bu nedenle, projeyi şekliniz hakkında yapılan birkaç varsayılan varsayımlar vardır:

- `package.json` ve `bower.json` varsayılan ve projeniz tarafından kullanılan liste bağımlılıkları otomatik türü edinme (ATA) dahil
- Üst düzey `node_modules` klasörü kitaplık kaynak kodunu içerir ve içeriğini varsayılan proje bağlamdan edilmez
- Tüm diğer `.js`, `.jsx`, `.ts`, ve `.tsx` dosya biridir büyük olasılıkla *kendi* kaynak dosyaları ve proje bağlamında eklenmelidir

Çoğu durumda, yalnızca projenizi açın ve varsayılan proje Yapılandırması'nı kullanarak harika deneyim sahibi mümkün olacaktır. Ancak, büyük veya farklı bir klasör yapıları projelerinde daha iyi odaklanmak dil hizmeti yalnızca kendi kaynak dosyaları üzerinde daha fazla yapılandırmak için tercih edilebilir.

### <a name="override-defaults"></a>Varsayılanlarını geçersiz kıl

Ekleyerek varsayılan yapılandırmayı geçersiz kılabilir bir `tsconfig.json` proje kök dosyaya.
A `tsconfig.json` proje içeriğiniz işleyebileceğiniz birkaç farklı seçenekler vardır.
Birkaç tanesi tüm seçenekleri, tam bir dizi yanı sıra, aşağıda listelenen [deposunun şeması bkz](http://json.schemastore.org/tsconfig).

## <a name="important-tsconfigjson-options"></a>Önemli `tsconfig.json` seçenekleri

```json
{
  "compilerOptions": {
    "allowJs": true,          // include .js and .jsx in project context (defaults to only .ts and .tsx)
    "noEmit": true            // turns off downlevel compiler
  },
  "files": [],                // list of explicit files to include in the project context. Highest priority.
  "include": [],              // list of folders or glob patterns to include in the project context.
  "exclude": [],              // list of folders or glob patterns to exclude. Overridden by files array.
  "typeAcquisition": {
    "enable": true,           // Defaulted to "false" with a tsconfig. Enables better IntelliSense in JS.
    "include": [ "jquery" ],  // Specific libs to fetch .d.ts files that weren't picked up by ATA
    "exclude": [ "node" ]     // Specific libs to not fetch .d.ts files for
  }
}
```

### <a name="example-project-configuration"></a>Örnek proje yapılandırma

Aşağıdaki Kurulum projeyle verilen:

- Projenin kaynak dosyaları `wwwroot/js`
- Projenin lib dosyaları `wwwrrot/lib`
- `bootstrap`, `jquery`, `jquery-validation`, ve `jquery-validation-unobtrusive` listelenir `bower.json`
- `kendo-ui` LIB klasörüne el ile eklendi

![Klasör yapısı](./media/folderStructure.png)

Aşağıdaki kullanabilirsiniz `tsconfig.json` dil emin olmak için hizmet yalnızca Kaynak dosyalarınız çözümler `js` klasörü, ancak yine getirir ve kullanır `.d.ts` kitaplıkları için dosyaları, `lib` klasörü.

```json
{
  "compilerOptions": {
    "allowJs": true,
    "noEmit": true
  },
  "exclude": ["wwwroot/lib"],  //ignore lib folders, we will get IntelliSense via ATA
  "typeAcquisition": {
    "enable": true,
    "include": [ "kendo-ui" ]  //kendo-ui wasn't added via bower, so we need to list it here
  }
}
```
# <a name="troubleshooting-the-javascript-language-service-has-been-disabled-for-the-following-projects"></a>JavaScript dil hizmetinin sorun giderme için aşağıdaki proje devre dışı bırakıldı.
İçeriği çok büyük miktarda sahip bir JavaScript projeyi açtığınızda, "JavaScript dil hizmetinin aşağıdaki proje için devre dışı bırakıldı" okuyan bir ileti alabilirsiniz. JavaScript kaynak çok büyük miktarda olması için en yaygın nedeni, 20 MB proje sınırını aşıyor kaynak kodu kitaplıklarıyla dahil olmak üzere nedeniyle olmasıdır.

Projeniz en iyi duruma getirmek için basit bir yol eklemektir bir `tsconfig.json` hangi dosyaların yoksaymak güvenli olduğunu bildiğiniz dil hizmeti izin vermek için proje kök dosyasında. Kitaplıkları depolandığı en yaygın dizinleri dışarıda bırakmak için aşağıdaki örneği kullanın:

```json
{
  "compilerOptions": {
    "allowJs": true,
    "allowSyntheticDefaultImports": true,
    "maxNodeModuleJsDepth": 2,
    "noEmit": true,
    "skipLibCheck": true
  },
  "exclude": [
    "**/bin",
    "**/bower_components",
    "**/jspm_packages",
    "**/node_modules",
    "**/obj",
    "**/platforms"
  ]
}
```

Uygun gördüğünüz şekilde dizin ekleyin. Diğer bir örnek, "Satıcı" veya "wwwroot/lib" dizinler verilebilir. 

> [!NOTE]
> Derleyici özelliği `disableSizeLimit` 20 MB onay sınırını devre dışı bırakmak için de kullanılabilir. Sınır devre dışı bırakma dil hizmeti çökebilir çünkü bu özelliğini kullanırken özel önlemleri alın.

## <a name="notable-changes-from-visual-studio-2015"></a>Visual Studio 2015 önemli değişiklikler

Olarak [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] tamamen yeni bir dil hizmeti özellikleri farklı olacaktır birkaç davranışları vardır veya belirtilmemelidir önceki deneyiminde.
VSDoc JSDoc, özel kaldırılmasını ile değiştirilmesi en dikkat çekici değişikliklerdir `.intellisense.js` uzantıları ve belirli kod düzenleri için sınırlı IntelliSense.

### <a name="no-more-references-or-referencesjs"></a>Daha fazla `///<references/>` veya `_references.js`

Daha önce IntelliSense kapsamınızı dosyaları olan verilen bir zamanda anlamak için oldukça karmaşık. Bazen tüm dosyalarınız kapsamdaki ve bazen ancak değildi arzu ve bu el ile başvuru yönetim içeren karmaşık yapılandırmalar için kılavuzluk. Artık başvuru yönetimi hakkında düşünmek gerekir ve gerekmeyen şekilde Üçlü eğik çizgi açıklamaları başvurur ileride veya `_references.js` dosyaları.

Bkz: [JavaScript IntelliSense](/visualstudio/ide/javascript-intellisense/) IntelliSense nasıl çalıştığı hakkında daha fazla bilgi için sayfa.

### <a name="vsdoc"></a>VSDoc

XML belgeleri yorumları, bazen VSDocs da adlandırılır daha önce kaynak kodunuzu IntelliSense sonuçlarını buff için kullanılacak olan ek veri ile işaretleme kullanılabiliyordu.
Şunun için artık VSDoc desteklenmeyen [JSDoc](http://usejsdoc.org/about-getting-started.html) olduğu yazma ve JavaScript için kabul edilen standart daha kolay.

### <a name="intellisensejs-extensions"></a>`.intellisense.js` Uzantıları

Daha önce yazabilirsiniz [IntelliSense uzantıları](https://msdn.microsoft.com/en-us/library/hh874692.aspx) olanak, üçüncü taraf kitaplıklar için özel tamamlama sonuçları eklemek.
Bu uzantılar yazma ve yükleme için oldukça zor ve yeni dil hizmetini ileride bu destek dosyalarının olmaz için bunlara başvurma sıkıcı.
Daha kolay bir alternatif olarak, eski olarak aynı IntelliSense faydalar sağlamak için TypeScript tanım dosyası yazabilirsiniz `.intellisense.js` uzantıları.
Bildirimi hakkında daha fazla bilgi edinin (`.d.ts`) dosyası yazma [burada](http://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html).

### <a name="unsupported-patterns"></a>Desteklenmeyen desenleri

Yeni dil hizmetini yürütme alt yapısı yerine statik çözümleme tarafından destekleniyor olduğundan (okuma [bu sorunu](https://github.com/Microsoft/TypeScript/issues/4789) bilgi farklar için), artık algılanabilir birkaç JavaScript desenleri vardır.
En yaygın düzeni "expando" Düzeni ' dir.
Şu anda dil hizmeti sabitlenmiş sonra bildirimi özelliklerine sahip nesneler üzerinde IntelliSense sağlayamaz.
Örneğin:

```js
var obj = {};
obj.a = 10;
obj.b = "hello world";
obj. // IntelliSense won't show properties a or b
```

Bu sorunu nesne oluşturma sırasında özellikleri bildirerek alabilirsiniz:

```js
var obj = {
    "a": 10,
    "b": "hello world"
}
obj. // IntelliSense shows properties a and b
```

JSDoc açıklama aşağıdaki gibi ekleyebilirsiniz:

```js
/**
 * @type {{a: number, b: string}}
 */
var obj = {};
obj.a = 10;
obj.b = "hello world";
obj. // IntelliSense shows properties a and b
```
