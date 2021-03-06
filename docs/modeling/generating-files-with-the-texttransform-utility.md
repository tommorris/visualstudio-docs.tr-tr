---
title: Visual Studio'da TextTransform yardımcı programı ile dosyalar oluşturma
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- text templates, TextTransform utility
- TextTransform.exe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 152f8d656bf83a6ad46770e695cd64c508dcc3bb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31951485"
---
# <a name="generate-files-with-the-texttransform-utility"></a>TextTransform yardımcı programı ile dosya oluştur

TextTransform.exe metin şablonu dönüştürme için kullanabileceğiniz bir komut satırı aracıdır. TextTransform.exe çağırdığınızda, bağımsız değişken olarak metin şablonu dosyasının adını belirtin. TextTransform.exe metin dönüştürme altyapısı çağırır ve metin şablonu işler. TextTransform.exe genellikle komut dosyaları tarafından çağrılır. Metin dönüştürmeyi Visual Studio veya yapı işlemi gerçekleştirebilir ancak bu genelde gerekli olmadığından.

> [!NOTE]
> Derleme işleminin parçası olarak metin dönüştürme gerçekleştirmek istiyorsanız, MSBuild metin dönüştürmeyi görevi kullanmayı düşünün. Daha fazla bilgi için bkz: [derleme sürecinde kod oluşturma](../modeling/code-generation-in-a-build-process.md). Bir makinede içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , ayrıca bir uygulama yazabilirsiniz yüklenir veya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] metin şablonları dönüştürebilirsiniz uzantısı. Daha fazla bilgi için bkz: [özel konak kullanarak metin şablonlarını işleme](../modeling/processing-text-templates-by-using-a-custom-host.md).

 TextTransform.exe şu dizinde bulunur:

 **\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE**

Professional Edition veya

 **\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE**

 için Enterprise edition.

Visual Studio'nun önceki sürümleri dosyası şu konumda bulunur:

**\Program Files (x86)\Common Files\Microsoft Shared\TextTemplating\{version}**

Hangi önceki bir sürümünün yüklü olduğu {version} bağlıdır.

## <a name="syntax"></a>Sözdizimi

```
TextTransform [<options>] <templateName>
```

### <a name="parameters"></a>Parametreler

|**Bağımsız değişken**|**Açıklama**|
|------------------|---------------------|
|`templateName`|Dönüştürmek istediğiniz şablon dosyası adını tanımlar.|

|**Seçeneği**|**Açıklama**|
|----------------|---------------------|
|**-out** \<dosya adı >|Dönüşümün çıktısını yazıldığı dosya.|
|**-r** \<derleme >|Derleme ve metin şablonu çalıştıran için kullanılan bir derleme.|
|**-u** \<ad alanı >|Şablon derlemek için kullanılan ad.|
|**-I** \<includedirectory >|Belirtilen metni şablona dahil metin şablonlarını içeren bir dizin.|
|**-P** \<referencepath >|Metin şablonu içinde belirtilen derlemeler için veya kullanarak aramak için bir dizin **- r** seçeneği.<br /><br /> Örneğin, Visual Studio API için kullanılan derlemeleri eklemek için kullanın<br /><br /> `-P "%VSSHELLFOLDER%\Common7\IDE\PublicAssemblies"`|
|**-dp** \<processorName >!\< className >! \<assemblyName&#124;codeBase >|Adı, tam tür adı ve metin şablonu içinde özel yönergeleri işlemek için kullanılan bir yönerge işlemcisi derleme.|
|**-a** [processorName]! [ directiveName]! \<parameterName >! \<parameterValue >|Bir yönerge işlemcisi için parametre değeri belirtin. Yalnızca parametre adı ve değeri belirtirseniz, tüm yönerge işlemcileri için parametresi kullanılabilir. Bir yönerge işlemcisi belirtirseniz, yalnızca belirtilen işlemciyi kullanılabilir bir parametredir. Bir yönerge adı belirtirseniz, yalnızca belirtilen yönergesi işlenirken parametresi kullanılabilir.<br /><br /> Bir yönerge işlemcisi veya metin şablonu parametre değerlerini erişmek için [ITextTemplatingEngineHost.ResolveParameterValue](https://msdn.microsoft.com/library/microsoft.visualstudio.texttemplating.itexttemplatingenginehost.resolveparametervalue.aspx). Bir metin şablonuna eklemek `hostspecific` şablon yönergesi ve ileti üzerinde çağırma `this.Host`. Örneğin:<br /><br /> `<#@template language="c#" hostspecific="true"#> [<#= this.Host.ResolveParameterValue("", "", "parameterName") #>]`.<br /><br /> Türü her zaman '!' yönerge adları ve isteğe bağlı işlemci bile atlarsanız, işaretler. Örneğin:<br /><br /> `-a !!param!value`|
|**-h**|Yardım sağlar.|

## <a name="related-topics"></a>İlgili konular

|Görev|Konu|
|----------|-----------|
|Dosyaları oluşturmak bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü.|[T4 Metin Şablonları Kullanarak Tasarım Zamanı Kodu Oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md)|
|Kendi veri kaynaklarını dönüştürmek için yönerge işlemcileri yazma.|[T4 Metin Dönüştürmeyi Özelleştirme](../modeling/customizing-t4-text-transformation.md)|
|Metin şablonları kendi uygulamasından çağrılacak izin veren bir metin şablon konak yazma.|[Bir Özel Konak kullanarak Metin Şablonlarını İşleme](../modeling/processing-text-templates-by-using-a-custom-host.md)|