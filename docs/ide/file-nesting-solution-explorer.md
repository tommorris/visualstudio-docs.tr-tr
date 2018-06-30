---
title: İç içe geçmiş kuralları için Çözüm Gezgini dosya
ms.date: 05/25/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
helpviewer_keywords:
- file nesting
- Solution Explorer, file nesting
author: angelosp
ms.author: angelpe
manager: douge
ms.openlocfilehash: bc4ba4c019801c4461313149c0f3befacefa93d2
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118151"
---
# <a name="customize-file-nesting-in-solution-explorer"></a>Çözüm Gezgini’nde dosya iç içe yerleştirmeyi özelleştirme

İlgili dosyaların iç içe **Çözüm Gezgini** iç içe geçmiş kurallar üzerinde hiçbir denetimi vardı artık yeni, ancak kadar değil. Hazır arasında seçim yapabilirsiniz **kapalı**, **varsayılan** ve **Web**, ancak iç içe geçme, istediğiniz tam olarak özelleştirebilirsiniz. Çözüme özel bile oluşturabilirsiniz ve projeye özel ayarlar, ancak daha sonra tüm. İlk üzerinden edelim Giden kutusu görüntüleniyor.

> [!NOTE]
> Şu anda özelliktir yalnızca ASP.NET Core projeleri için desteklenir.

## <a name="file-nesting-options"></a>Dosya iç içe geçmiş seçenekleri

![Açık/kapalı iç içe geçme dosya kapatma düğmesi](media/filenesting_onoff.png)

Özelleştirilmiş olmayan dosya iç içe geçme için kullanılabilir seçenekler şunlardır:

* **Devre dışı**: Bu seçenek tüm iç içe geçmeyen dosyaların düz bir listesini sağlar.

* **Varsayılan**: Bu seçenek davranışını iç içe geçme varsayılan dosya verir **Çözüm Gezgini**. Belirtilen proje türü için hiçbir ayar bulunması durumunda hiçbir dosya projesinde yerleştirilir. İç içe geçme ayarlarını, örneğin, bir Web projesi için mevcutsa uygulanır.

* **Web**: Bu seçenek geçerlidir **Web** geçerli Çözümdeki tüm projeleri için iç içe geçmiş davranışı dosya. Çok sayıda kurallarına sahiptir ve gözden geçirin ve Bize düşüncelerinizi paylaşın geçirmenizi öneririz. Aşağıdaki ekran görüntüsünde dosya iç içe geçmiş davranışının bu seçenekle almak yalnızca birkaç örnek vurgular:

   ![Çözüm Gezgini'nde iç içe geçmiş dosyası](media/filenesting.png)

## <a name="customize-file-nesting"></a>Dosya iç içe geçme özelleştirme

Giden kutusu görüntüleniyor hoşlanmıyorsanız, istemeniz ayarları iç içe geçme, kendi özel dosya oluşturabilirsiniz **Çözüm Gezgini** dosyaları iç içe nasıl. İstediğiniz ve bunları istediğiniz gibi arasında geçiş yapabilirsiniz kadar çok sayıda özel dosya iç içe geçmiş ayar ekleyebilirsiniz. Yeni özel bir ayar oluşturmak için boş bir dosya ile başlatabilirsiniz veya kullanabilirsiniz **Web** , başlangıç noktası olarak ayarlar:

![Özel dosya iç içe geçmiş kuralları ekleme](media/filenesting_addcustom.png)

Şunu kullanmanızı öneririz **Web** noktası ile bir şey işlevleri zaten çalışmaya kolay olduğundan, başlangıç olarak ayarlar. Kullanırsanız **Web** ayarları, başlangıç noktası olarak *. filenesting.json* dosyası şu dosyaya benzer görünür:

![Özel ayarlar için temel olarak kuralları iç içe geçme varolan dosyayı kullan](media/filenesting_editcustom.png)

Şimdi düğümde odaklanmak **dependentFileProviders** ve alt düğümlerini. Her alt düğüm, Visual Studio dosyaları yerleştirmek için kullanabileceğiniz kural türüdür. Örneğin, **aynı dosya adı, ancak farklı bir uzantıya sahip** kuralı bir türüdür. Kullanılabilir kurallar şunlardır:

* **extensionToExtension**: iç içe için bu kural türünü kullanın *file.js* altında *file.ts*

* **fileSuffixToExtension**: iç içe için bu kural türünü kullanın *dosya vsdoc.js* altında *file.js*

* **addedExtension**: iç içe için bu kural türünü kullanın *file.html.css* altında *file.html*

* **pathSegment**: iç içe için bu kural türünü kullanın *jquery.min.js* altında *jquery.js*

* **allExtensions**: iç içe için bu kural türünü kullanın *dosya.* * altında *file.js*

* **fileToFile**: iç içe için bu kural türünü kullanın *bower.json* altında *.bowerrc*

### <a name="the-extensiontoextension-provider"></a>ExtensionToExtension sağlayıcısı

Bu sağlayıcı, belirli dosya uzantılarını kullanarak dosya iç içe geçmiş kuralları tanımlamanıza olanak sağlar. Aşağıdaki örnek göz önünde bulundurun:

![extentionToExtension örnek kuralları](media/filenesting_extensiontoextension.png) ![extentionToExtension örnek etkisi](media/filenesting_extensiontoextension_effect.png)

* *Cart.js* altında iç içe *cart.ts* ilk nedeniyle **extensionToExtension** kuralı

* *Cart.js* altında iç içe *cart.tsx* çünkü **.ts** önce gelen **.tsx** kuralları ve ayrıca bir üst yalnızca olabilir

* *Light.css* altında iç içe *light.sass* ikinci nedeniyle **extensionToExtension** kuralı

* *Home.HTML* altında iç içe *home.md* üçüncü nedeniyle **extensionToExtension** kuralı

### <a name="the-filesuffixtoextension-provider"></a>FileSuffixToExtension sağlayıcısı

Bu sağlayıcı olduğu gibi çalışır **extensionToExtension** tek farkı dosya uzantısı yerine soneki kuralı bakan olan ile sağlayıcısı. Aşağıdaki örnek göz önünde bulundurun:

![fileSuffixToExtension örnek kuralları](media/filenesting_filesuffixtoextension.png) ![fileSuffixToExtension örnek etkisi](media/filenesting_filesuffixtoextension_effect.png)

* *Portal vsdoc.js* altında iç içe *portal.js* nedeniyle **fileSuffixToExtension** kuralı

* Her bir kural yönünü aynı şekilde çalışır **extensionToExtension**

### <a name="the-addedextension-provider"></a>AddedExtension sağlayıcısı

Bu sağlayıcı ek uzantısı olmadan dosya altında ek uzantılı dosyalar içine alır. Ek uzantısı yalnızca tam dosya adının sonunda yer alabilir. Aşağıdaki örnek göz önünde bulundurun:

![addedExtension örnek kuralları](media/filenesting_addedextension.png) ![addedExtension örnek etkisi](media/filenesting_addedextension_effect.png)

* *File.HTML.css* altında iç içe *file.html* nedeniyle **addedExtension** kuralı

### <a name="the-pathsegment-provider"></a>PathSegment sağlayıcısı

Bu sağlayıcı bir dosya ek uzantısız altında ek uzantılı dosyalar içine alır. Ek uzantısı yalnızca tam dosya adı orta bulunabilir. Aşağıdaki örnek göz önünde bulundurun:

![pathSegment örnek kuralları](media/filenesting_pathsegment.png) ![pathSegment örnek etkisi](media/filenesting_pathsegment_effect.png)

* *JQuery.Min.js* altında iç içe *jquery.js* nedeniyle **pathSegment** kuralı

### <a name="the-allextensions-provider"></a>AllExtensions sağlayıcısı

Bu sağlayıcı, uzantıyı ancak aynı temel dosya adına sahip dosyalar için dosya iç içe geçmiş kuralları tanımlamanıza olanak sağlar. Aşağıdaki örnek göz önünde bulundurun:

![allExtensions örnek kuralları](media/filenesting_allextensions.png) ![allExtensions örnek etkisi](media/filenesting_allextensions_effect.png)

* *Template.cs* ve *template.doc* altında iç içe *template.tt* nedeniyle **allExtensions** kuralı.

### <a name="the-filetofile-provider"></a>FileToFile sağlayıcısı

Bu sağlayıcı, tüm dosya adları üzerinde tabanlı dosya iç içe geçmiş kuralları tanımlamanıza olanak sağlar. Aşağıdaki örnek göz önünde bulundurun:

![fileToFile örnek kuralları](media/filenesting_filetofile.png) ![fileToFile örnek etkisi](media/filenesting_filetofile_effect.png)

* *.bowerrc* altında iç içe *bower.json* nedeniyle **fileToFile** kuralı

### <a name="rule-order"></a>Kural sırası

Sıralama her özel ayarları dosyanız bölümünde önemlidir. İçinde kuralları çalıştırılır yukarı veya aşağı içine taşıyarak sırasını değiştirebilirsiniz **dependentFileProvider** düğümü. Örneğin yapan bir kuralı varsa **file.js** üst **file.ts** ve yapar başka bir kural **file.coffee** üst **file.ts**, tüm üç dosyaları mevcut olduğunda dosyasında göründükleri sırada iç içe geçmiş davranışını belirler. Bu yana **file.ts** yalnızca bir üst olabilir, hangi kural ilk WINS yürütür.

Sıralama da kuralı bölümler için kendilerini, yalnızca bir bölüm içindeki dosyalar için önemlidir. Dosyaların çifti dosya iç içe geçmiş kuralıyla eşleşen hemen diğer kurallardan daha aşağı dosyasında göz ardı edilir ve sonraki çifti dosyaların işlenir.

### <a name="file-nesting-button"></a>Dosya iç içe geçmiş düğmesi

Aynı düğmesini aracılığıyla kendi özel ayarlar dahil olmak üzere tüm ayarlarını yönetebilirsiniz **Çözüm Gezgini**:

![Özel dosya iç içe geçmiş kurallarını etkinleştirin](media/filenesting_activatecustom.png)

## <a name="create-solution-specific-and-project-specific-settings"></a>Çözüm ve proje özgü ayarları oluştur

Çözüm ve proje özgü ayarları her bir çözüm ve proje bağlam menüsü aracılığıyla oluşturabilirsiniz:

![Çözüm ve proje özgü iç içe geçmiş kurallar](media/filenesting_solutionprojectspecific.png)

Çözüm ve proje özgü ayarları etkin Visual Studio ayarlar ile birleştirilir. Örneğin, bir boş proje özgü ayarları dosyasına sahip, ancak **Çözüm Gezgini** dosyaları hala geçirme. İç içe geçmiş davranışı çözüm özgü ayarları veya Visual Studio ayarları geliyor. Dosya iç içe geçmiş ayarları birleştirmek için önceliği olan: Visual Studio > çözüm > Proje.

Dosyaları diske seçeneğini etkinleştirerek bulunsa bile, çözüm ve proje özgü ayarlarını yoksaymak için Visual Studio söyleyebilir **çözüm ve proje ayarlarını yoksaymak** altında **Araçları**  >  **Seçenekleri** > **ASP.NET Core** > **dosya iç içe geçme**.

Bunun tersini yapmak ve Visual Studio söyleyin *yalnızca* ayarlayarak çözüme özel veya projeye özgü ayarları kullanmak **kök** düğüme **doğru**. Visual Studio o düzeyde dosyaları birleştirme durdurur ve dosyaları hiyerarşisinde yukarı yüksek ile birleştirerek değil.

Çözüm ve proje özgü ayarları, kaynak denetimi ve kod temeli üzerinde çalışır bunları paylaşabilirsiniz tüm ekip denetlenebilir.

## <a name="disable-global-file-nesting-rules-for-a-particular-solution-or-project"></a>Genel dosya iç içe geçmiş kuralları belirli çözüm ya da proje için devre dışı bırak

Kullanarak özel çözümler veya projeler için mevcut genel dosya iç içe geçmiş kuralları devre dışı bırakabilirsiniz **kaldırmak** yerine bir sağlayıcı için eylem **eklemek**. Örneğin aşağıdaki ayarları kodu bir projeye ekleyin, tüm **pathSegment** bu belirli bir proje için genel bulunabilecek kuralları devre dışı bırakılır:

```json
"dependentFileProviders": {
  "remove": {
    "pathSegment": {}
  }
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md)
