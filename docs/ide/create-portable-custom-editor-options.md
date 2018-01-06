---
title: Visual Studio'da EditorConfig ayarlarla | Microsoft Docs
ms.custom: 
ms.date: 12/13/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editorconfig [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.workload: multiple
ms.openlocfilehash: 0219ff704e22ab1c27d47e312825a66cb3a15166
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>Taşınabilir, özel düzenleyici ayarları EditorConfig ile oluşturma

Visual Studio 2017 içinde ekleyebileceğiniz bir [EditorConfig](http://editorconfig.org/) dosyası projeye ya da tutarlı kodlama zorlamak için codebase stiller herkesin codebase çalışır. EditorConfig ayarları genel Visual Studio Metin Düzenleyici ayarları göre önceliklidir. Bunun anlamı, uyarlayabileceğiniz her codebase bu projeye özel metin düzenleyici ayarları kullanmak için. Visual Studio'da kendi kişisel Düzenleyicisi tercihleri hala ayarlayabilirsiniz **seçenekleri** iletişim kutusu. Bu ayarlar bir codebase .editorconfig dosyası olmadan içinde çalışırken sürekli ya da .editorconfig dosya belirli bir ayarı geçersiz kılmaz uygulanır. Bu tür bir tercih girinti stili örneğidir&mdash;sekme veya boşluk.

EditorConfig ayarlar, çok sayıda kod düzenleyicileri ve Visual Studio dahil olmak üzere IDE tarafından desteklenir. Bu, kodunuzu seyahat ediyor ve Visual Studio dışında bile kodlama stillerini zorunlu kılabilir taşınabilir bir bileşenidir.

## <a name="coding-consistency"></a>Tutarlılık kodlama

EditorConfig dosyalarında ayarlar tutarlı kodlama stillerini ve girinti stili, sekme genişliği, satır sonu karakterleri, gibi bir codebase kodlama, ayarlarında sağlamanıza olanak tanıyan ve daha fazlasını Düzenleyicisi veya IDE bağımsız olarak kullanılır. Örneğin, C# ' ta temelinizde girintileri her zaman beş boşluk karakterlerinden oluşamaz, UTF-8 kodlaması belgeleri kullanın ve her satırın her zaman CR/LF ile biten tercih için bir kuralı varsa kodlama, bunu yapmak için bir .editorconfig dosyası yapılandırabilirsiniz.

Kodlama kuralları kişisel projelerinizi kullandığınız ekibinizin projelerde kullanılanlardan farklı. Örneğin, kodlama zaman girintileme sekme karakteri ekler tercih edebilirsiniz. Ancak, ekibinizin girintileme sekme karakteri yerine dört boşluk karakterleri ekler tercih edebilirsiniz. EditorConfig dosyaları, her senaryo için bir yapılandırma olmasını sağlayarak bu sorunu giderin.

Codebase dosyasında ayarları içerdiğinden bu codebase birlikte seyahat. Kod dosyası EditorConfig uyumlu bir düzenleyicide açın sürece, metin düzenleyici ayarları uygulanır. EditorConfig dosyaları hakkında daha fazla bilgi için bkz: [EditorConfig.org](http://editorconfig.org/) Web sitesi.

## <a name="override-editorconfig-settings"></a>EditorConfig ayarları geçersiz kılar

Dosya hiyerarşinizdeki bir klasöre bir .editorconfig dosya eklediğinizde, tüm dosyalara uygulanabilir o düzeyde ve aşağıda ayarlarını uygulayın. Belirli bir projenin EditorConfig ayarları geçersiz kılabilir veya üst düzey EditorConfig dosya farklı kuralları kullanır, codebase için bir .editorconfig dosyası temelinizde 's depoyu veya proje dizininin kökü için eklemeniz yeterlidir. Yerleştirdiğinizden emin olun ```root=true``` Visual Studio .editorconfig dosyaları için dizin yapısını daha fazla görünmüyor şekilde dosyasında özellik. Aynı düzeydeki ve tüm alt dizinlerdeki dosyalara yeni EditorConfig dosyası ayarlarını uygulayın.

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
- Son\_of_line
- karakter kümesi
- kök

EditorConfig Düzenleyici ayarları XML dışında Visual Studio tarafından desteklenen tüm dillerde desteklenir. Ayrıca, EditorConfig destekleyen [kod stili](../ide/editorconfig-code-style-settings-reference.md) ve [adlandırma](../ide/editorconfig-naming-conventions.md) C# ve Visual Basic için kuralları.

## <a name="editing-editorconfig-files"></a>EditorConfig dosyalarını düzenleme

Visual Studio .editorconfig dosyalarını düzenlemek için bazı IntelliSense sağlar. Çok sayıda .editorconfig dosya düzenlerseniz, bulabilirsiniz [EditorConfig dil hizmeti](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) uzantısı yararlıdır.

EditorConfig dosyanızı düzenlenebilir sonra yeni ayarların etkili olması için kod dosyaları yeniden yüklemeniz gerekir.

## <a name="adding-and-removing-editorconfig-files"></a>Ekleme ve EditorConfig dosyaları kaldırılıyor

Bir EditorConfig ekleyerek dosya projenize veya codebase varolan stilleri yenilerini dönüştürmez. Örneğin, sekmelerle biçimlendirilmiş girintileri dosyanızdaki varsa ve alanları ile girintileri bir EditorConfig dosyası ekleyin, girinti karakter boşlukları dönüştürülmez. Ancak, herhangi bir yeni satırları kod EditorConfig dosyanın göre biçimlendirilir.

Projenizden bir EditorConfig dosyayı kaldırın veya codebase kapatın ve yeni satır kod genel Düzenleyicisi ayarlarını geri dönmek için tüm açık kod dosyaları açın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, önce ve bir .editorconfig dosyası projeye ekledikten sonra bir C# kod parçacığı girinti durumunu gösterir. **Sekmeleri** ayarı **seçenekleri** Visual Studio Metin Düzenleyici iletişim kutusunu bastığınızda boşluk karakterleri üretmek için ayarlanmış **sekmesini** anahtarı.

![Metin Düzenleyici sekme ayarı](../ide/media/vside_editorconfig_tabsetting.png)

Beklendiği gibi tuşuna basarak **sekmesini** sonraki satıra anahtar dört ek boşluk karakterleri ekleyerek satır girintileri.

![EditorConfig kullanmadan önce kod](../ide/media/vside_editorconfig_before.png)

Aşağıdaki içeriğe sahip projesine .editorconfig adlı yeni bir dosya ekleyeceğiz. `[*.cs]` Ayarlama, bu değişikliği yalnızca C# kod dosyaları proje uygulandığı anlamına gelir.

```
# Top-most EditorConfig file
root = true

# Tab indentation
[*.cs]
indent_style = tab
```

Bastığınızda şimdi **sekmesini** anahtar, sekme karakterleri yerine boşluk alırsınız.

![SEKME tuşu sekme karakteri ekler](../ide/media/vside_editorconfig_tab.png)

## <a name="troubleshooting-editorconfig-settings"></a>Sorun giderme EditorConfig ayarları

Varsa bir EditorConfig dosyası herhangi bir yere veya üstü projenizin konumunu dizin yapısına, Visual Studio Düzenleyici ayarları bu dosya, editöre uygular. Bu durumda, durum çubuğunda aşağıdaki iletiyi görebilirsiniz:

   **"Bu dosya türü için kullanıcı tercihlerini bu projenin kodlama kuralları tarafından geçersiz kılınır."**

Bu olması durumunda tüm Düzenleyicisi ayarlarında anlamına gelir **Araçları**, **seçenekleri**, **metin düzenleyici** (örneğin, girinti boyutu ve stili, sekme boyutu veya kodlama kuralları) içinde belirtilen bir EditorConfig dosya veya dizin yapısını projesinde, kuralları EditorConfig dosyasında üstü seçeneklerinde ayarları geçersiz kılar. Değiştirerek bu davranışı denetleyebilirsiniz **kodlama kuralları izleyin proje** seçeneğini **Araçları**, **seçenekleri**, **metin düzenleyici**. Seçeneğini işaretleyerek Visual Studio EditorConfig desteği kapatır.

![Araçlar Seçenekler - izleyin proje kodlama kuralları](media/coding_conventions_option.png)

Bir komut istemi açıp projenizi içeren disk kökünden aşağıdaki komutu çalıştırarak yararlı dizinleri üst .editorconfig dosyalarla bulabilirsiniz:

```
dir .editorconfig /s
```

Ayarlayarak EditorConfig kuralları kapsamını denetleyebilirsiniz ```root=true``` özelliği, depo kökündeki .editorconfig dosyasında veya projenizin bulunduğu dizini. Visual Studio .editorconfig açılan dosyayı dizin ve her üst dizini adlı bir dosyayı arar. Arama kök filepath ulaştığında ya da bir .editorconfig dosya ile biten ```root=true``` bulunur.

## <a name="see-also"></a>Ayrıca bkz.

[.NET kodu stil kuralları](../ide/editorconfig-code-style-settings-reference.md)  
[İçin bir dil hizmeti EditorConfig destekleme](../extensibility/supporting-editorconfig.md)  
[EditorConfig.org](http://editorconfig.org/)  
[Kod Düzenleyicisi'nde yazma](writing-code-in-the-code-and-text-editor.md)