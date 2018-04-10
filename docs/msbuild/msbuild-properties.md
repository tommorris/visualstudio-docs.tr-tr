---
title: MSBuild özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, properties
ms.assetid: 962912ac-8931-49bf-a88c-0200b6e37362
caps.latest.revision: 32
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7bb81e7c65a8ca9b941f3b12ed77e16ab880e449
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="msbuild-properties"></a>MSBuild Özellikleri
Özellikler, yapıları yapılandırmak için kullanılabilen ad-değer çiftleridir. Özellikler, değerlerin görevlere geçirilmesinde, koşulların değerlendirilmesinde ve proje dosyası boyunca başvurulacak olan değerlerin depolanmasında yararlıdır.  
  
## <a name="defining-and-referencing-properties-in-a-project-file"></a>Bir Proje Dosyasındaki Özellikleri Tanımlama ve Başvurma  
 Özellikler, bir alt öğesi olarak özelliğinin adı olan bir öğeyi oluşturarak bildirildiğinde bir [PropertyGroup](../msbuild/propertygroup-element-msbuild.md) öğesi. Örneğin aşağıdaki XML, bir `BuildDir` değerine sahip olan `Build` adında bir özellik oluşturur.  
  
```xml  
<PropertyGroup>  
    <BuildDir>Build</BuildDir>  
</PropertyGroup>  
```  
  
 Proje dosyası boyunca özelliklere $(`PropertyName`) söz dizimi kullanılarak başvurulur. Örneğin, önceki örnekteki özellik $(BuildDir) kullanılarak başvurulur.  
  
 Özelliği yeniden tanımlayarak özellik değerlerini değiştirebilirsiniz. Aşağıdaki XML kullanılarak `BuildDir` özelliğine yeni bir değer verilebilir:  
  
```xml  
<PropertyGroup>  
    <BuildDir>Alternate</BuildDir>  
</PropertyGroup>  
```  
  
 Özellikler, proje dosyasında göründükleri sırayla değerlendirilir. `BuildDir` öğesine ait yeni değerin, eski değer atandıktan sonra bildirilmesi gerekir.  
  
## <a name="reserved-properties"></a>Ayrılmış Özellikler  
 MSBuild, proje dosyası ve MSBuild ikili dosyaları hakkındaki bilgileri depolamak için bazı özellik adlarını saklar. Bu özellikler, diğer özelliklere benzer şekilde $ simgesi kullanılarak başvurulur. Örneğin $(MSBuildProjectFile), dosya adı uzantısı dahil olmak üzere proje dosyasının tüm dosya adını döndürür.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: Proje dosyasının konumunu veya adını başvuru](../msbuild/how-to-reference-the-name-or-location-of-the-project-file.md) ve [MSBuild ayrılmış ve tanınmış özellikleri](../msbuild/msbuild-reserved-and-well-known-properties.md).  
  
## <a name="environment-properties"></a>Ortam Özellikleri  
 Proje dosyalarındaki ortam değişkenlerine, ayrılmış özelliklere başvurduğunuz şekilde başvurabilirsiniz. Örneğin, proje dosyanızda `PATH` ortam değişkenini kullanmak için, $(Yol) işaretini kullanın. Proje, ortam özelliği ile aynı ada sahip bir özellik tanımı içeriyorsa projedeki özellik, ortam değişkeninin değerini geçersiz kılar.  
  
 Her MSBuild projesi bir yalıtılmış ortam bloğuna sahiptir; yalnızca kendi bloğundaki okumaları ve yazmaları görür.  Proje dosyası değerlendirilmeden veya oluşturulmadan önce MSBuild, özellik koleksiyonunu başlattığında yalnızca ortam değişkenlerini okur. Bunun ardından bu ortam özellikleri statiktir, yani her bir araç aynı adlar ve değerler ile başlar.  
  
 Ortam değişkenlerinin oluşturulan araç içinde geçerli değerini almak için kullanmak [özellik işlevleri](../msbuild/property-functions.md) System.Environment.GetEnvironmentVariable. Ancak tercih edilen yöntem, <xref:Microsoft.Build.Utilities.ToolTask.EnvironmentVariables%2A> görev parametresinin kullanılmasıdır. Bu dize dizisinde ayarlanan ortam özellikleri, sistem ortamı değişkenlerini etkilemeden oluşturulan araca gönderilebilir.  
  
> [!TIP]
>  Tüm ortam değişkenleri, başlangıç özellikleri olması için okunmaz. Adı "386" gibi geçersiz bir MSBuild özellik adı olan tüm ortam değişkenleri göz ardı edilir.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: bir derleme kullanma ortam değişkenleri](../msbuild/how-to-use-environment-variables-in-a-build.md).  
  
## <a name="registry-properties"></a>Kayıt Defteri Özellikleri  
 `Hive` öğesinin kayıt defteri kovanı olduğu (örneğin, HKEY_LOCAL_MACHINE), `Key` öğesinin anahtar adı olduğu, `SubKey` öğesinin alt anahtar adı olduğu ve `Value` öğesinin alt anahtarın değeri olduğu aşağıdaki söz dizimini kullanarak sistem kayıt defteri değerlerini okuyabilirsiniz.  
  
```  
$(registry:Hive\MyKey\MySubKey@Value)  
```  
  
 Varsayılan alt anahtar değerini almak için `Value` öğesini atın.  
  
```  
$(registry:Hive\MyKey\MySubKey)  
```  
  
 Bu kayıt defteri değeri, bir yapı özelliğini başlatmak için kullanılabilir. Örneğin, Visual Studio web tarayıcısı giriş sayfasını temsil eden bir yapı özelliği oluşturmak için şu kodu kullanın:  
  
```xml  
<PropertyGroup>  
  <VisualStudioWebBrowserHomePage>  
    $(registry:HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0\WebBrowser@HomePage)  
  </VisualStudioWebBrowserHomePage>  
<PropertyGroup>  
```  
  
## <a name="global-properties"></a>Genel Özellikler  
 MSBuild kullanarak komut satırında özelliklerini ayarlamanıza olanak tanır **/property** (veya **/p**) geçin. Bu genel özellik değerleri proje dosyasında ayarlanan özellik değerlerini geçersiz kılar. Bu ortam özellikleri içerir, ancak değiştirilemeyen ayrılmış özellikleri içermez.  
  
 Aşağıdaki örnek genel `Configuration` özelliğini `DEBUG` olarak ayarlar.  
  
```  
msbuild.exe MyProj.proj /p:Configuration=DEBUG  
```  
  
 Genel özellikler, MSBuild görevinin `Properties` özniteliğini kullanarak aynı zamanda çoklu bir proje yapısındaki alt projeler için ayarlanabilir veya değiştirilebilir. Genel özellikleri de iletilir alt projelerine sürece `RemoveProperties` MSBuild görevi özniteliği değil iletmek için özellikler listesini belirtmek için kullanılır. Daha fazla bilgi için bkz: [MSBuild görevi](../msbuild/msbuild-task.md).
  
 Bir proje etiketinde `TreatAsLocalProperty` özniteliğini kullanarak bir özellik belirtirseniz bu genel özellik değeri, proje dosyasında ayarlanan özellik değerini geçersiz kılmaz. Daha fazla bilgi için bkz: [proje öğesi (MSBuild)](../msbuild/project-element-msbuild.md) ve [nasıl yapılır: farklı seçeneklerle aynı kaynak dosyaları derleme](../msbuild/how-to-build-the-same-source-files-with-different-options.md).  
  
## <a name="property-functions"></a>Özellik İşlevleri  
 .NET Framework sürüm 4'ten başlayarak, MSBuild komut dosyalarınızı değerlendirmek için özellik işlevlerini kullanabilirsiniz. MSBuild görevlerini kullanmadan, yapı komut dosyanızdaki sistem saatini okuyabilir, dizeleri karşılaştırabilir, normal ifadeleri eşleştirebilir ve başka birçok eylemi gerçekleştirebilirsiniz.  
  
 Herhangi bir özelliğin üzerinde gerçekleştirmek için dize (örnek) yöntemlerini kullanabilirsiniz ve birçok sistem sınıfının statik yöntemlerini çağırabilirsiniz. Örneğin, bir yapı özelliğini bugünün tarihine aşağıdaki gibi ayarlayabilirsiniz.  
  
```xml  
<Today>$([System.DateTime]::Now.ToString("yyyy.MM.dd"))</Today>  
```  
  
 Daha fazla bilgi ve özellik işlevlerin bir listesi için bkz [özellik işlevleri](../msbuild/property-functions.md).  
  
## <a name="creating-properties-during-execution"></a>Çalıştırma Sırasında Özellik Oluşturma  
 `Target` öğeleri dışında konumlanan özelliklere, bir yapının değerlendirme aşamasında değerler atanır. Sonraki yürütme aşamasında özellikler aşağıdaki şekilde oluşturulabilir veya değiştirilebilir:  
  
-   Bir özellik herhangi bir görev tarafından yayılabilir. Bir özellik yaymak üzere [görev](../msbuild/task-element-msbuild.md) öğesinin bir alt olmalı [çıkış](../msbuild/output-element-msbuild.md) sahip öğe bir `PropertyName` özniteliği.  
  
-   Bir özellik tarafından gösterilen [CreateProperty](../msbuild/createproperty-task.md) görev. Bu kullanım önerilmiyor.  
  
-   .NET Framework 3.5'de başlayarak `Target` öğeleri, özellik bildirimlerini içerebilen `PropertyGroup` öğelerini içerebilir.  
  
## <a name="storing-xml-in-properties"></a>Özellikler'de XML Depolama  
 Özellikler, değerlerin görevlere geçirilmesini veya günlük bilgilerin görüntülenmesini sağlayabilecek rastgele bir XML içerebilir. Aşağıdaki örnek, XML ve diğer özellik başvurularını içeren bir değere sahip olan `ConfigTemplate` özelliğini gösterir. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], ilgili özellik değerlerini kullanarak özellik başvurularını değiştirir. Özellik değerleri göründükleri sırayla atanır. Bu nedenle bu örnekte, `$(MySupportedVersion)`, `$(MyRequiredVersion)` ve `$(MySafeMode)` öğelerinin önceden tanımlanmış olması gerekir.  
  
```xml  
  
<PropertyGroup>  
    <ConfigTemplate>  
        <Configuration>  
            <Startup>  
                <SupportedRuntime  
                    ImageVersion="$(MySupportedVersion)"  
                    Version="$(MySupportedVersion)"/>  
                <RequiredRuntime  
                    ImageVersion="$(MyRequiredVersion)"  
                    Version="$(MyRequiredVersion)"  
                    SafeMode="$(MySafeMode)"/>  
            </Startup>  
        </Configuration>  
    </ConfigTemplate>  
</PropertyGroup>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild Kavramları](../msbuild/msbuild-concepts.md)  
 [MSBuild](../msbuild/msbuild.md)  
 [Nasıl yapılır: derlemede ortam değişkenlerini kullanma](../msbuild/how-to-use-environment-variables-in-a-build.md)   
 [Nasıl yapılır: Proje dosyasının konumunu veya adını başvurusu](../msbuild/how-to-reference-the-name-or-location-of-the-project-file.md)   
 [Nasıl yapılır: farklı seçeneklerle aynı kaynak dosyaları derleme](../msbuild/how-to-build-the-same-source-files-with-different-options.md)   
 [MSBuild ayrılmış ve tanınmış özellikleri](../msbuild/msbuild-reserved-and-well-known-properties.md)   
 [Özellik Öğesi (MSBuild)](../msbuild/property-element-msbuild.md)
