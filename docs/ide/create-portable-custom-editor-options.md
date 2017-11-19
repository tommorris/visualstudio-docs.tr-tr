---
title: "Taşınabilir, özel düzenleyici ayarları ile EditorConfig oluştur | Microsoft Docs"
ms.custom: 
ms.date: 10/27/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editor
ms.assetid: 
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: 2c1df6f8e34d2b8e72486dd804ba57f0dcf2406b
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>Taşınabilir, özel düzenleyici ayarları EditorConfig ile oluşturma
Visual Studio'da metin düzenleyici ayarları belirli bir türde tüm projeler için geçerlidir. C# metin düzenleyici ayarı değiştirirseniz, bu nedenle, örneğin, bu ayar uygulanır *tüm* C# Visual Studio projelerinde. Ancak, bazı durumlarda, kendi kişisel Düzenleyicisi tercihleri farklı kuralları kullanmanız gerekebilir. [EditorConfig](http://editorconfig.org/) dosyaları, ortak metin düzenleyici seçenekleri proje başına temelinde sağlayarak bunu yapmanızı sağlar. Kod temeliniz eklenen bir .editorconfig dosyasında bulunan EditorConfig ayarları genel Visual Studio Metin Düzenleyici ayarları geçersiz kılar. Bunun anlamı, uyarlayabileceğiniz her codebase tercih ettiğiniz metin düzenleyici ayarları kullanmak için. Hayır eklenti Visual Studio'da bu işlevselliği kullanmak için gereklidir.

## <a name="coding-consistency"></a>Tutarlılık kodlama
EditorConfig dosyalarında ayarlar tutarlı kodlama stillerini ve girinti stili, sekme genişliği, satır sonu karakterleri, gibi bir dil için kodlama, ayarları sağlamanıza olanak tanıyan ve daha fazlasını codebase Düzenleyicisi veya IDE bağımsız olarak, kullanın. Örneğin, C# ' ta temelinizde girintileri her zaman beş boşluk karakterlerinden oluşamaz, UTF-8 kodlaması belgeleri kullanın ve her satırın her zaman CR/LF ile biten tercih için bir kuralı varsa kodlama, bunu yapmak için bir .editorconfig dosyası yapılandırabilirsiniz.

Kodlama kuralları kişisel projelerinizi kullandığınız ekibinizin projelerde kullanılanlardan farklı. Örneğin, kodlama zaman SEKME tuşuna basarak bir sekme karakteri ekler tercih edebilirsiniz. Ancak, ekibinizin girintileme sekme karakteri yerine dört boşluk karakterleri ekler tercih edebilirsiniz. EditorConfig dosyaları, her senaryo için bir yapılandırma olmasını sağlayarak bu sorunu giderin.

Codebase dosyasında ayarları içerdiğinden bu codebase birlikte seyahat. Kod dosyası EditorConfig uyumlu bir düzenleyicide açın sürece, metin düzenleyici ayarları uygulanır. EditorConfig dosyaları hakkında daha fazla bilgi için bkz: [EditorConfig.org](http://editorconfig.org/) Web sitesi.

## <a name="override-editorconfig-settings"></a>EditorConfig ayarları geçersiz kılar
Dosya hiyerarşinizdeki bir klasöre .editorconfig dosya eklediğinizde, tüm dosyalara uygulanabilir o düzeyde ve aşağıda ayarlarını uygulayın. Belirli bir projenin EditorConfig ayarları geçersiz kılabilir veya üst düzey .editorconfig dosya farklı kuralları kullanır, codebase için .editorconfig dosya temelinizde 's depoyu veya proje dizininde köküne eklemeniz yeterlidir. Yerleştirdiğinizden emin olun ```root=true``` Visual Studio için tüm .editorconfig görünmüyor dosyaya özelliğinde dizin yapısını başka dosyalar. Yeni .editorconfig dosya ayarlarını düzeyi içinde bulunur ve tüm alt dizinler dosyalarında uygulanır.

```
# top-most EditorConfig file
root = true
```

![EditorConfig hiyerarşisi](../ide/media/vside_editorconfig_hierarchy.png)

EditorConfig dosyaları yukarıdan aşağıya okunur ve en yakın EditorConfig dosyaları son okuyun. Kuralları daha yakından dosyalarında önceliklidir şekilde EditorConfig bölümleri eşleşen gelen kuralları okundu, sırayla uygulanır.

## <a name="supported-settings"></a>Desteklenen ayarları
Visual Studio düzenleyicisinde aşağıdaki çekirdek kümesinden destekleyen [EditorConfig özellikleri](http://editorconfig.org/#supported-properties):  

- indent_style
- indent_size
- tab_width
- end_of_line
- karakter kümesi
- kök

Ayrıca, desteklediği [.NET kod stil kuralları](../ide/editorconfig-code-style-settings-reference.md).  

EditorConfig ayarları XML dışında Visual Studio tarafından desteklenen tüm dillerde desteklenir.

## <a name="intellisense"></a>IntelliSense
Visual Studio .editorconfig dosyalarını düzenlemek için sınırlı IntelliSense sağlar. Çok sayıda .editorconfig dosyası düzenlerseniz, bulabilirsiniz [EditorConfig dil hizmeti](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) uzantısı yararlıdır.

## <a name="example"></a>Örnek
Burada, önce ve .editorconfig dosyası projeye ekledikten sonra bir C# kod parçacığı girinti durumunu gösteren bir örnek verilmiştir. **Sekmeleri** ayarı **seçenekleri** Visual Studio Metin Düzenleyici iletişim kutusunu bastığınızda boşluk karakterleri üretmek için ayarlanmış **sekmesini** kodunuzda anahtar.

![Metin Düzenleyici sekme ayarı](../ide/media/vside_editorconfig_tabsetting.png)

Beklendiği gibi tuşuna basarak **sekmesini** sonraki satıra anahtar dört ek boşluk karakterleri ekleyerek satır girintileri.

![EditorConfig kullanmadan önce kod](../ide/media/vside_editorconfig_before.png)

Aşağıdaki içeriğe sahip projesine .editorconfig adlı yeni bir dosya ekleyeceğiz. `[*.cs]` Ayarlama, bu değişikliği yalnızca bu projede .cs dosyaları uygulanacağı anlamına gelir.  

![Proje dosyasına eklenen .editorconfig](../ide/media/vside_editorconfig_addconfig.png)

Bastığınızda şimdi **sekmesini** anahtar, sekme karakterleri yerine boşluk alırsınız.

![Sekme karakteri SEKMESİ ekler](../ide/media/vside_editorconfig_tab.png)

> [!NOTE]
>  Bir .editorconfig ekleme projenize dosya, veya varolan yenilerini stiller dönüştürme codebase, yalnızca yeni eklenen satırlar için geçerli olacaktır. Projenizden bir .editorconfig dosyayı kaldırın veya codebase, küresel ayarlara dönmek Düzenleyici ayarları için kod dosyaları yeniden yüklemeniz gerekir. .Editorconfig dosyaları hatalarını Visual Studio'da hata listesi penceresini raporlanır.

## <a name="troubleshooting-editorconfig-settings"></a>Sorun giderme EditorConfig ayarları
Varsa bir EditorConfig dosyası herhangi bir yere veya üstü projenizin konumunu dizin yapısına, Visual Studio, düzenleyici bu dosyada Düzenleyicisi ayarlar geçerli olur. Bu durumda, durum çubuğunda aşağıdaki iletiyi görebilirsiniz:

**"Bu dosya türü için kullanıcı tercihlerini bu projenin kodlama kuralları tarafından geçersiz kılınır."**

Bu olması durumunda tüm Düzenleyicisi ayarlarında anlamına gelir **Araçları**, **seçenekleri**, **metin düzenleyici** (sekme boyutu girinti boyutu gibi stili girinti &mdash; sekme veya boşluk veya kodlama kullanımı gibi kuralları `var`) belirtilir bir EditorConfig dosya veya dizin yapısını projesinde üstü EditorConfig dosyasında kuralları Seçenekleri ayarları geçersiz kılar. Değiştirerek bu davranışı denetleyebilirsiniz **kodlama kuralları izleyin proje** seçeneğini **Araçları**, **seçenekleri**, **metin düzenleyici**. Seçeneğini işaretleyerek Visual Studio EditorConfig desteğini devre dışı.

![Araçlar Seçenekler - izleyin proje kodlama kuralları](media/coding_conventions_option.png)

Bir komut istemi'ni açarak üst dizinlerde .editorconfig dosyaları bulabilir ve disk kökünden aşağıdaki komutu çalıştırarak projenizi içerir:

```
dir .editorconfig /s
```

Ayarlayarak EditorConfig kuralları kapsamını denetleyebilirsiniz ```root=true``` özelliği, depo kökündeki .editorconfig dosyasında veya projenizin bulunduğu dizini. Visual Studio .editorconfig açılan dosyayı dizin ve her üst dizini adlı bir dosyayı arar. Visual Studio durdurur kök filepath ulaşıldığında veya .editorconfig dosya ile arama ```root=true``` bulunur.

## <a name="support-editorconfig-for-your-language-service"></a>EditorConfig dil hizmetiniz için destek
Visual Studio dil hizmet uyguladığınızda çoğu durumda EditorConfig Evrensel özellikleri desteklemek için ek bir iş gereklidir. Çekirdek Düzenleyicisi'ni otomatik olarak bulur ve kullanıcıların dosyaları açmak ve uygun bir metin arabelleği ve görünüm seçeneklerini ayarlar .editorconfig dosyasını okur. Ancak, bazı dil Hizmetleri kullanıcı düzenler veya metin biçimleri sekmeler ve alanları gibi öğeleri için genel ayarları kullanmak yerine uygun bağlamsal metin Görünüm seçeneğini kullanmayı tercih. Bu durumlarda, dil hizmeti EditorConfig dosyaları destekleyecek şekilde güncelleştirilmesi gerekir.

Bir genel değiştirerek EditorConfig dosyaları desteklemek için bir dil hizmeti güncelleştirmek için gereken değişiklikler şunlardır _dile özgü_ seçeneğini bir _bağlamsal_ seçeneği:  

### <a name="indent-style"></a>Girinti stili
Değiştirin:  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs  
_veya_  
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs  

İle:  

! textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)  
_veya_  
! textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)  

### <a name="indent-size"></a>Girinti boyutu
Değiştirin:  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize  
_veya_  
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize  

İle:  

textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)  
_veya_  
textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)  

### <a name="tab-size"></a>Sekme boyutu
Değiştirin:  

Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize  
_veya_  
Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize  

İle:  

textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)  
_veya_  
textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)  

## <a name="see-also"></a>Ayrıca bkz.
[.NET kodu stil kuralları](../ide/editorconfig-code-style-settings-reference.md)  
[EditorConfig.org](http://editorconfig.org/)  
[Kod Düzenleyicisi'nde yazma](writing-code-in-the-code-and-text-editor.md)