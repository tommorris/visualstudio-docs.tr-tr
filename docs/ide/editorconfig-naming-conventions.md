---
title: ".NET adlandırma kurallarına EditorConfig | Microsoft Docs"
ms.custom: 
ms.date: 11/20/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- naming conventions [EditorConfig]
- EditorConfig naming conventions
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: b14f0b98651f0a76d9a9a67bd429673e41e7d319
ms.sourcegitcommit: 1e08318a8a684b21609af7a5e48b56abcc3239e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/13/2017
---
# <a name="naming-conventions-for-editorconfig"></a>EditorConfig için adlandırma kuralları

Adlandırma kuralları kod öğeleri sınıfları, özellikleri ve yöntemleri gibi adlandırma ilgilendiren. Örneğin, Genel üyeler büyük harfle yazılmalıdır veya zaman uyumsuz yöntemleri "Zaman uyumsuz" bitmelidir belirtebilirsiniz. Bunları belirterek bu kuralları zorunlu kılabilir bir [.editorconfig dosya](../ide/create-portable-custom-editor-options.md). Kural ihlallerinin adlandırma ya da hata listesi görüntülenir veya adı altında bir öneri olarak önem derecesine bağlı olarak, kuralınız için seçin. İhlalleri görmek için projeyi derlemek için gerek yoktur.

Adlandırma kuralları en belirgin sıralı çok az özgü .editorconfig dosyasında. Uygulanabilir ilk kural karşılaştı uygulanan yalnızca kuralıdır.

Her adlandırma kuralı için aşağıda açıklanan özelliklerini kullanarak uygulandığı sembolleri, adlandırma bir tarzını ve kural zorlama bir önem derecesi belirtmelisiniz. Özelliklerin sırası önemli değildir.

Başlamak için kullanacağınız adlandırma kuralınız için bir başlık her kural tam olarak açıklamak için gerekli özellikleri seçin. Örneğin, `public_members_must_be_capitalized` bir adlandırma kuralı için iyi ve açıklayıcı bir ad değil. Seçtiğiniz olarak başlık biz başvurmak **< namingRuleTitle\>**  bölümlerde içinde.

## <a name="symbols"></a>Simgeleri

İlk olarak, bir grup için adlandırma kuralı uygulamak için simge tanımlayın. Bu özellik aşağıdaki biçime sahiptir:

`dotnet_naming_rule.<namingRuleTitle>.symbols = <symbolTitle>`

Değiştirerek simgeleri grup için bir ad verin **< symbolTitle\>**  ile açıklayıcı bir başlık, örneğin değeri `public_symbols`. Kullanacağınız **< symbolTitle\>**  kural simgeleri değeri açıklamak üç özellik adlarını (simge, Erişilebilirlik düzeyleri ve değiştiricileri türleri için) uygulanır.

### <a name="kinds-of-symbols"></a>Simge türü

Adlandırma kuralı uygulamak için simgelerini türünü tanımlamak için bir özelliği şu biçimde belirtin:

`dotnet_naming_symbols.<symbolTitle>.applicable_kinds = <values>`

Aşağıdaki liste, izin verilen değerler gösterir ve virgül ile ayırarak birden çok değer belirtebilirsiniz.

- \*(tüm sembolleri belirtmek için bu değeri kullanın)
- sınıf
- struct 
- arabirim
- enum
- özellik
- yöntemi
- alan
- olay
- temsilci
- parametre

### <a name="accessibility-levels-of-symbols"></a>Simgelerin erişilebilirlik düzeyleri

Erişilebilirlik düzeyleri uygulamak için adlandırma kuralı istediğiniz simgelerin tanımlamak için bir özellik adı şu biçimde belirtin:

`dotnet_naming_symbols.<symbolTitle>.applicable_accessibilities = <values>`

Aşağıdaki liste, izin verilen değerler gösterir ve virgül ile ayırarak birden çok değer belirtebilirsiniz.

- \*(tüm erişilebilirlik düzeyleri belirtmek için bu değeri kullanın)
- public
- iç veya arkadaş
- private
- protected
- korumalı\_iç ya da protected_friend

> [!NOTE]
> Erişilebilirlik düzeyi adlandırma kuralınızın yoksayıldı, adlandırma kuralı, başka bir parçası olarak belirtmeniz gerekir.

### <a name="symbol-modifiers"></a>Sembol değiştiricileri

Değiştiriciler uygulamak için adlandırma kuralı istediğiniz simgelerin tanımlamak için bir özellik adı şu biçimde belirtin:

`dotnet_naming_symbols.<symbolTitle>.required_modifiers = <values>`

Aşağıdaki liste, izin verilen değerler gösterir ve virgül ile ayırarak birden çok değer belirtebilirsiniz.

- soyut veya must_inherit
- async
- const
- readonly
- statik veya paylaşılan

`required_modifiers`İsteğe bağlı bir özelliktir. Bu özelliği atarsanız, adlandırma kuralınızın tüm değiştiricileri uygulanır.

## <a name="style"></a>Stil

Grup için adlandırma kuralı uygulamak için simge belirledik, biz adlandırma stili açıklamak gerekir. Stil adı belirli bir önek veya belirli bir soneki olmasını ya da ayrı sözcükleri adında belirli bir karakterle ayrılır olabilir. Büyük harf stili de belirtebilirsiniz. Stil özelliği aşağıdaki biçime sahiptir:

`dotnet_naming_rule.<namingRuleTitle>.style = <styleTitle>`

Stilini değiştirerek bir ad verin **< styleTitle\>**  ile açıklayıcı bir başlık, örneğin değeri `first_word_upper_case_style`. Kullanacağınız **< styleTitle\>**  adlandırma stili (önek, sonek, sözcük ayırıcı karakteri ve büyük/küçük harf) açıklayan özellik adları değeri. Stil kodunuzu açıklamak için bir veya daha fazla bu özellikleri kullanın.

### <a name="require-a-prefix"></a>Bir önek gerektirir

Sembol adları belirli karakter ile başlamalıdır belirtmek için bu özelliği kullanın:

`dotnet_naming_style.<styleTitle>.required_prefix = <prefix>`

### <a name="require-a-suffix"></a>Sonek gerektirir

Sembol adları belirli karakterler ile bitmelidir belirtmek için bu özelliği kullanın:

`dotnet_naming_style.<styleTitle>.required_suffix = <suffix>`

### <a name="require-a-certain-word-separator"></a>Belirli bir sözcük ayırıcı gerektirir

Sembol adları içindeki ayrı sözcükleri belirli bir karakteri ile ayrılmalıdır belirtmek için bu özelliği kullanın:

`dotnet_naming_style.<styleTitle>.word_separator = <separator character>`

### <a name="require-a-capitalization-style"></a>Büyük harf stili gerektirir

Sembol adları belirli büyük/küçük harf stilini belirlemek için bu özelliği kullanın:

`dotnet_naming_style.<styleTitle>.capitalization = <value>`

Bu özellik için izin verilen değerler:

- pascal_case
- camel_case
- İlk\_word_upper
- tüm\_üst
- all_lower

> [!NOTE]
> Adlandırma stili yoksayıldı, adlandırma stili, aksi takdirde bir parçası olarak bir büyük harf stili belirtmeniz gerekir.

## <a name="severity"></a>Önem Derecesi

Adlandırma kuralınızın ihlal önemini açıklamak için aşağıdaki biçimde bir özellik belirtin:

`dotnet_naming_rule.<namingRuleTitle>.severity = <value>`

Aşağıdaki tabloda, izin verilen önem derecesi değerlerini ve ne anlama geldiklerini gösterilmektedir:

Önem Derecesi | Efekt
------------ | -------------
None veya Sessiz | Bu stili ardından, herhangi bir şey kullanıcıya gösterme; Ancak, otomatik olarak oluşturulan kod bu stili izler.
Öneri | Bu stili ardından, kullanıcıya ilk iki karakter üzerinde temel alınan noktaların bir öneri olarak göster. Derleme zamanında hiçbir etkisi yoktur.
uyarı | Bu stili ardından, derleyici uyarısı hata listesinde göster.
Hata | Bu stili ardından, bir derleyici hatası hata listesinde göster.

> [!NOTE]
> Kural ihlallerinin adlandırma görmeniz için projenizi derleme gerekmez. Hata listesi veya bir öneri olarak kod düzenlendikten olarak görünürler.

## <a name="example"></a>Örnek

Aşağıdaki .editorconfig dosya ortak özellikleri, yöntemleri, alanları, olaylar ve temsilciler büyük harfle yazılmalıdır olduğunu belirten bir adlandırma kuralı içerir. Bu adlandırma kuralını değerleri ayırmak için virgül kullanarak, kuralın uygulanacağı simge birden çok türde belirtir dikkat edin.

```
# Public members must be capitalized (public_members_must_be_capitalized)
[*.{cs,vb}]
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

Aşağıdaki ekran görüntüsünde Düzenleyicisi'nde bu adlandırma kuralını etkisini gösterir. İki ortak değişken ilk harfini büyük harf adlı. Biridir bir `const`, ve `readonly`. Adlandırma kuralı yalnızca uygular beri *readonly* simge, yalnızca `readonly` değişkeni, bir adlandırma kuralı öneri gösterir.

![Adlandırma kuralı önerisi](media/editorconfig-naming-rule-suggestion.png)

Şimdi ihlali önem değiştirelim `warning`:

```
dotnet_naming_rule.public_members_must_be_capitalized.severity = warning
```

Öneri adı ihlali altında görmesini yerine kod dosyasını kapatıp varsa dalgalı yeşil ve bir uyarı hata listesinde bakın:

![Adlandırma kuralı uyarı](media/editorconfig-naming-rule-warning.png)

## <a name="see-also"></a>Ayrıca bkz.

[.NET dil ve kuralları biçimlendirme](../ide/editorconfig-code-style-settings-reference.md)  
[Taşınabilir özel düzenleyici seçenekleri oluşturma](../ide/create-portable-custom-editor-options.md)