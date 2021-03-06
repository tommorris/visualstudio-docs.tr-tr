---
title: TextTransform yardımcı programı ile dosya oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, TextTransform utility
- TextTransform.exe
ms.assetid: 06a48235-fe02-403e-a1cf-2ae70b4db62f
caps.latest.revision: 43
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 069f7f5ef2c579c10c1ee7c19989c79ce3ad63bf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687596"
---
# <a name="generating-files-with-the-texttransform-utility"></a>TextTransform Yardımcı Programı ile Dosya Oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [TextTransform yardımcı programı ile dosya oluşturma](https://docs.microsoft.com/visualstudio/modeling/generating-files-with-the-texttransform-utility).  
  
TextTransform.exe bir metin şablonu dönüştürmek için kullanabileceğiniz bir komut satırı aracıdır. TextTransform.exe çağırdığınızda, bağımsız değişken olarak bir metin şablonu dosyasının adını belirtin. TextTransform.exe metin dönüştürme motoru çağırır ve metin şablonu işler. TextTransform.exe genellikle betiklerin çağrılır. Visual Studio'da ya da yapı işleminde metin dönüştürme gerçekleştirmek için ancak, bu genellikle gerekli değildir.  
  
> [!NOTE]
>  Bir yapı işleminin parçası olarak metin dönüştürme gerçekleştirmek istiyorsanız, MSBuild metin dönüştürme görevi kullanılarak göz önünde bulundurun. Daha fazla bilgi için [derleme sürecinde kod oluşturma](../modeling/code-generation-in-a-build-process.md). İçindeki bir makineye [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , ayrıca bir uygulama yazabilirsiniz yüklenir veya [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] metin şablonlarını dönüştürmek uzantı. Daha fazla bilgi için [özel konak kullanarak metin şablonlarını işleme](../modeling/processing-text-templates-by-using-a-custom-host.md).  
  
 TextTransform.exe şu dizinde bulunur:  
  
 **\Program Files\Microsoft Shared\TextTemplating\11.0**  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
TextTransform [<options>] <templateName>  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|**Bağımsız değişken**|**Açıklama**|  
|------------------|---------------------|  
|`templateName`|Dönüştürmek istediğiniz şablon dosyasının adını tanımlar.|  
  
|**Seçeneği**|**Açıklama**|  
|----------------|---------------------|  
|**-out** \<dosya adı >|Dönüşümün çıkış yazıldığı dosya.|  
|**-r** \<derleme >|Derleme ve metin şablonu çalıştırmak için kullanılan derleme.|  
|**-u** \<ad alanı >|Şablon derlemek için kullanılan bir ad alanı.|  
|**-I** \<includedirectory >|Belirtilen metin şablonuna dahil metin şablonlarını içeren bir dizin.|  
|**-P** \<referencepath >|Metin şablonu içinde belirtilen derlemeler için ya da kullanarak aramak için bir dizin **- r** seçeneği.<br /><br /> Örneğin, Visual Studio API için kullanılan derlemeler eklemek için kullanın<br /><br /> `-P "%VSSHELLFOLDER%\Common7\IDE\PublicAssemblies"`|  
|**-dp** \<processorName >!\< SınıfAdı >! \<assemblyName&#124;codeBase >|Adı, tam tür adı ve özel yönergeler metin şablonu içinde işlemek için kullanılan bir yönerge işlemcisi derlemenin.|  
|**-bir** [processorName]! [ directiveName]! \<parameterName >! \<parameterValue >|Bir yönerge işlemcisi için bir parametre değeri belirtin. Yalnızca parametre adı ve değeri belirtirseniz, tüm yönerge işlemcileri için parametre kullanılabilir. Bir yönerge işlemcisi belirtirseniz, yalnızca belirtilen işlemci için kullanılabilir bir parametredir. Bir yönerge adı belirtirseniz, yalnızca belirtilen yönerge işlenirken parametresi kullanılabilir.<br /><br />  Bir metin şablonunda dahil `hostspecific` şablon yönergesinde ve ileti üzerinde çağırmak `this.Host`. Örneğin:<br /><br /> `<#@template language="c#" hostspecific="true"#> [<#= this.Host.ResolveParameterValue("", "", "parameterName") #>]`.<br /><br /> Türü her zaman '!' yönergesi adı ve isteğe bağlı işlemci bile atlarsanız işaretler. Örneğin:<br /><br /> `-a !!param!value`|  
|**-h**|Yardım sağlar.|  
  
## <a name="related-topics"></a>İlgili konular  
  
|Görev|Konu|  
|----------|-----------|  
|Dosyalarında bir [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] çözüm.|[T4 Metin Şablonları Kullanarak Tasarım Zamanı Kodu Oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md)|  
|Kendi veri kaynaklarınızı dönüştürmek için yönerge işlemcileri yazın.|[T4 Metin Dönüştürmeyi Özelleştirme](../modeling/customizing-t4-text-transformation.md)|  
|Kendi uygulamanızı metin şablonlarını çağırmak izin veren bir metin şablonu oluşturma barındırıcısı yazın.|[Bir Özel Konak kullanarak Metin Şablonlarını İşleme](../modeling/processing-text-templates-by-using-a-custom-host.md)|



