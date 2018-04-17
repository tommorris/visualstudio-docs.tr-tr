---
title: Seçenekler, metin düzenleyici, JavaScript, IntelliSense | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Intellisense.References
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Intellisense.General
ms.assetid: b4a9816d-cf87-4dc6-a8d4-1591d6a48103
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fe387287b9b46e6fdd2972ce1a3f77e4f5349414
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="options-text-editor-javascript-intellisense"></a>Seçenekler, Metin Düzenleyici, JavaScript, IntelliSense
Kullanım **IntelliSense** sayfasında **seçenekleri** için JavaScript IntelliSense davranışını etkileyen ayarları değiştirmek için iletişim kutusu. Erişebileceğiniz **IntelliSense** seçerek sayfa **Araçları**, **seçenekleri** menü çubuğunda, ve ardından genişletme **Metin Düzenleyicisi**,  **JavaScript**, **IntelliSense.**  
  
[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  
  
**IntelliSense** sayfası aşağıdaki bölümleri içerir:  
  
## <a name="validation"></a>Doğrulama  
 JavaScript düzenleyicisinin belgenizdeki sözdizimini doğrulama şekline ilişkin tercihleri ayarlamak için bu seçenekleri kullanabilirsiniz.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Sözdizimi hataları göster**  
 Bu onay kutusu seçili olmadığında, JavaScript kod düzenleyicisi sözdizimi hatalarını göstermez. Kendi yazmadığınız kodla çalışıyorsanız ve sözdizimi hatalarını düzeltmeyi amaçlamıyorsanız, bu özellik kullanışlıdır.  
  
 Bu onay kutusu seçildiğinde seçin seçeneğine sahip **hatalarla uyarı olarak göster** onay kutusu.  
  
 **Hata uyarıları göster**  
 Bu onay kutusu seçildiğinde, JavaScript hataları uyarı olarak gösterilir (hata listesindeki hatalar olarak değil).  
  
 **Çeşitli dosyalar projedeki dosyaları için Uzak başvuruları (örneğin http://) yükle**  
 Bu onay kutusu seçiliyken ve bir projenin bağlamı dışında açılmış bir JavaScript dosyanız varsa, Visual Studio IntelliSense bilgilerini sağlamak amacıyla dosyada başvurulan uzak JavaScript dosyalarını indirir. Bu seçenek işaretliyse, JavaScript dosyanıza bir başvuru olarak eklediğiniz dosyalar indirilir.  
  
> [!NOTE]
>  Web projeleri için, projenizde başvurulan uzak dosyalar varsayılan olarak indirilir.  
  
## <a name="statement-completion"></a>Deyim Tamamlama  
 IntelliSense deyim tamamlama davranışını değiştirmek için bu seçenekleri kullanabilirsiniz.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Yalnızca sekmesini kullanın veya tamamlamaya girin**  
 Bu onay kutusu seçildiğinde, JavaScript kod düzenleyicisi deyimlere tamamlama listesinde seçilen öğeleri ancak siz Sekme veya Enter tuşuna bastıktan sonra ekler. Bu onay kutusu seçili olmadığında nokta, virgül, iki nokta üst üste, açılış parantezi ve açılış ayracı ({) da deyimlere seçili öğeleri ekleyebilir.  
  
## <a name="references"></a>Referanslar  
 Farklı JavaScript projesi türleri için kapsamda olan IntelliSense .js türlerini belirtmek için bu seçenekleri kullanabilirsiniz. IntelliSense başvuruları normalde, genel nesneler için IntelliSense desteği sağlamak amacıyla kullanılır. Bu sayfayı, çalışma zamanında yüklenmesi gereken komut dosyalarının yüklenme sırasını ayarlamak ve IntelliSense uzantı dosyalarını eklemek için de kullanabilirsiniz.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Başvuru grupları**  
 Bu seçenek başvuru grubu türünü belirtir. Üç başvuru grubu desteklenir:  
  
 Belirli IntelliSense .js dosyalarının farklı JavaScript projeleri için kapsamda olduğunu belirtmek için önceden tanımlı başvuru gruplarını kullanabilirsiniz. Dört başvuru grubu mevcuttur:  
  
-   Örtük (Windows *sürüm*), için [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] JavaScript kullanarak uygulamaları. Bu gruba dahil dosyalarıdır Kod düzenleyicisinde için için açılan her .js dosya kapsamına [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] JavaScript kullanarak uygulamaları.  
  
-   Örtük (Web); HTML5 projeleri için. Bu grupta yer alan dosyalar, bu proje türleri için Kod Düzenleyicisi'nde açılan her .js dosyası için kapsama girer.  
  
-   Adanmış çalışan başvuru grupları; HTML5 Web Çalışanları için. Bu grupta belirtilen dosyalar, bir adanmış çalışan başvuru grubuna dair açık başvuru içeren .js dosyaları için kapsama girer.  
  
-   Genel; diğer JavaScript proje türleri için.  
  
**Eklenen dosyalar**  
Bu seçenek, dil hizmetinin bağlamına dosyaların yüklendiği sırayı belirtir. Kullanarak sırayı yapılandırabilirsiniz **kaldırmak**, **Yukarı Taşı**, ve **Aşağı Taşı** düğmeler. IntelliSense'in düzgün çalışması için, bir diğer dosyaya bağımlı olan dosya söz konusu bu diğer dosyadan sonra yüklenmelidir.  
  
> [!CAUTION]
>  Bir nesne iki veya daha fazla örtük başvuruda koşulsuz olarak tanımlanırsa, nesneyi tanımlamak için bu listedeki son başvuru kullanılır.  
  
**Grup için bir başvuru ekleyin**  
Bu seçenek, uygun dosyaların bulunduğu yere giderek ek IntelliSense .js dosyalarını eklemek için bir yol sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[JavaScript IntelliSense](../../ide/javascript-intellisense.md)