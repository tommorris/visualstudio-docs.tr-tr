---
title: Visual Studio'da EditorConfig ayarlarını kullanma
ms.date: 12/13/2017
ms.topic: conceptual
helpviewer_keywords:
- editorconfig [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.openlocfilehash: 3ace523bd68b9d96916c23ebdbc93eaadd339da6
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34446507"
---
# <a name="create-portable-custom-editor-settings-with-editorconfig"></a>Taşınabilir, özel düzenleyici ayarları EditorConfig ile oluşturma

Visual Studio 2017 içinde ekleyebileceğiniz bir [EditorConfig](http://editorconfig.org/) dosyası projeye ya da tutarlı kodlama zorlamak için codebase stiller herkesin codebase çalışır. EditorConfig ayarları genel Visual Studio Metin Düzenleyici ayarları göre önceliklidir. Bu, her kod temelini o projeye özel metin düzenleyici ayarlarını kullanmak üzere uyarlayabileceğiniz anlamına gelir. Visual Studio'da kendi kişisel Düzenleyicisi tercihleri hala ayarlayabilirsiniz **seçenekleri** iletişim kutusu. Codebase içinde çalışırken sürekli bu ayarları uygulamak bir *.editorconfig* dosyası veya ne zaman *.editorconfig* dosya belirli bir ayarı geçersiz kılma değil. Bu tür bir tercih girinti stili örneğidir&mdash;sekme veya boşluk.

EditorConfig ayarlar, çok sayıda kod düzenleyicileri ve Visual Studio dahil olmak üzere IDE tarafından desteklenir. Bu, kodunuzu seyahat ediyor ve Visual Studio dışında bile kodlama stillerini zorunlu kılabilir taşınabilir bir bileşenidir.

> [!NOTE]
> Projeniz Visual Studio'da bir EditorConfig dosya eklediğinizde, belgenin biçimlendirme sürece var olan kod biçimlendirme değiştirilmez (**Düzenle** > **Gelişmiş**  >  **Biçimlendirmek belge** veya **Ctrl**+**K**, **Ctrl**+**D**). Ancak, herhangi bir yeni satırları kod göre EditorConfig ayarları biçimlendirilir.

## <a name="coding-consistency"></a>Tutarlılık kodlama

EditorConfig dosyalarında ayarlar tutarlı kodlama stillerini ve girinti stili, sekme genişliği, satır sonu karakterleri, gibi bir codebase kodlama, ayarlarında sağlamanıza olanak tanıyan ve daha fazlasını Düzenleyicisi veya IDE bağımsız olarak kullanılır. Örneğin, kod temeliniz girintileri her zaman beş boşluk karakterlerinden oluşamaz tercih için bir kuralı varsa, C# ' ta kodlama, UTF-8 kodlaması, belgeleri kullanın ve her satırın her zaman CR/LF ile biten, yapılandırabileceğiniz bir *.editorconfig* Bunu yapmak için dosya.

Kodlama kuralları kişisel projelerinizi kullandığınız ekibinizin projelerde kullanılanlardan farklı. Örneğin, kodlama zaman girintileme sekme karakteri ekler tercih edebilirsiniz. Ancak, ekibinizin girintileme sekme karakteri yerine dört boşluk karakterleri ekler tercih edebilirsiniz. EditorConfig dosyaları, her senaryo için bir yapılandırma olmasını sağlayarak bu sorunu giderin.

Codebase dosyasında ayarları içerdiğinden bu codebase birlikte seyahat. Kod dosyası EditorConfig uyumlu bir düzenleyicide açın sürece, metin düzenleyici ayarları uygulanır. EditorConfig dosyaları hakkında daha fazla bilgi için bkz: [EditorConfig.org](http://editorconfig.org/) Web sitesi.

## <a name="supported-settings"></a>Desteklenen ayarları

Visual Studio düzenleyicisinde çekirdek kümesini destekler [EditorConfig özellikleri](http://editorconfig.org/#supported-properties):

- indent_style
- indent_size
- tab_width
- Son\_of_line
- karakter kümesi
- Trim\_trailing_whitespace
- INSERT\_final_newline
- kök

EditorConfig Düzenleyici ayarları XML dışında Visual Studio tarafından desteklenen tüm dillerde desteklenir. Ayrıca, EditorConfig destekleyen [kod stili](../ide/editorconfig-code-style-settings-reference.md) ve [adlandırma](../ide/editorconfig-naming-conventions.md) C# ve Visual Basic için kuralları.

## <a name="adding-and-removing-editorconfig-files"></a>Ekleme ve EditorConfig dosyaları kaldırılıyor

Bir EditorConfig ekleyerek dosya projenize veya codebase varolan stilleri yenilerini dönüştürmez. Örneğin, sekmelerle biçimlendirilmiş girintileri dosyanızdaki varsa ve alanları ile girintileri bir EditorConfig dosyası ekleyin, girinti karakterleri otomatik olarak boşlukları dönüştürülmez. Ancak, herhangi bir yeni satırları kod EditorConfig dosyanın göre biçimlendirilir. Ayrıca, belgenin biçimlendirme varsa (**Düzenle** > **Gelişmiş** > **belgeyi Biçimlendir** veya **Ctrl** + **K**, **Ctrl**+**D**), varolan kod satırlarına EditorConfig dosyasındaki ayarları uygulanır.

Projenizden bir EditorConfig dosyayı kaldırın veya codebase kapatın ve yeni satır kod genel Düzenleyicisi ayarlarını geri dönmek için tüm açık kod dosyaları açın.

### <a name="to-add-an-editorconfig-file-to-a-project-or-solution"></a>Proje ya da çözüm EditorConfig dosya eklemek için

1. Proje ya da çözüm Visual Studio'da açın. Mı bağlı olarak proje ya da çözüm düğümünü seçin, *.editorconfig* ayarları, Çözümdeki tüm projeleri veya tek uygulamalısınız. Bir klasör proje ya da eklemek için çözüm seçebilirsiniz *.editorconfig* dosya.

1. Menü çubuğundan seçin **proje** > **Yeni Öğe Ekle...** , veya basın **Ctrl**+**Shift**+**A**.

   **Yeni Öğe Ekle** iletişim kutusu açılır.

1. Sol taraftaki kategorileri seçin **genel**ve ardından **metin dosyası** şablonu. İçinde **adı** metin kutusuna `.editorconfig` ve ardından **Ekle**.

   Bir *.editorconfig* dosya, Çözüm Gezgini'nde görünür ve Düzenleyicisi'nde açar.

   ![Çözüm Gezgini'nde .editorconfig dosyası](media/editorconfig-in-solution-explorer.png)

1. Örneğin dosyayı istediğiniz gibi düzenleyin:

   ```EditorConfig
   root = true

   [*.{cs,vb}]
   indent_size = 4
   trim_trailing_whitespace = true

   [*.cs]
   csharp_new_line_before_open_brace = methods
   ```

Alternatif olarak, yükleme [EditorConfig dil hizmeti uzantı](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig). Bu uzantıyı yükledikten sonra seçmeniz yeterlidir **Ekle** > **.editorconfig dosya** çözüm düğüm, proje düğümüne ya da Çözüm Gezgini'nde herhangi bir klasörü sağ tıklatın veya bağlam menüsünden.

![.Editorconfig dosya uzantısı Ekle](media/editorconfig-extension-add.png)

## <a name="override-editorconfig-settings"></a>EditorConfig ayarları geçersiz kılar

Eklediğinizde bir *.editorconfig* dosya, dosya hiyerarşinizdeki bir klasöre ayarlarına tüm geçerli o düzeyde ve aşağısındaki dosyalara. Codebase diğer bölümleri daha farklı kuralları kullanır, belirli bir projede, codebase veya bir codebase parçası EditorConfig ayarlarını geçersiz kılabilirsiniz. Başka bir yere koddan birleştirme ve onun kuralları değiştirmek istemiyorsanız bu kullanışlı olabilir.

Bazı veya tüm EditorConfig ayarlarını geçersiz kılmak için ekleyin bir *.editorconfig* dosya düzeyinde geçersiz kılınan bu ayarların uygulanmasını istediğiniz dosya hiyerarşisi. Aynı düzeyinde ve alt dizinlerdeki dosyalara yeni EditorConfig dosyası ayarlarını uygulayın.

![EditorConfig hiyerarşisi](../ide/media/vside_editorconfig_hierarchy.png)

Bazı geçersiz kılmak istiyorsanız, ancak yalnızca bu ayarlarında ayarlarının tümünü belirtin *.editorconfig* dosya. Alt düzey dosyasında açıkça listeleyen özellikleri geçersiz kılınır. Üst düzey'nden diğer ayarlar *.editorconfig* dosyaları devam uygulamak. Emin olmak istiyorsanız _hiçbir_ ayarlarından _herhangi_ üst düzey *.editorconfig* dosyaları, bu codebase kısmına uygulanır, ekleme ```root=true``` özelliğine alt düzey *.editorconfig* dosyası:

```EditorConfig
# top-most EditorConfig file
root = true
```

EditorConfig dosyaları yukarıdan aşağıya okunur ve en yakın EditorConfig dosyaları son okuyun. Kuralları daha yakından dosyalarında önceliklidir şekilde EditorConfig bölümleri eşleşen gelen kuralları okundu, sırayla uygulanır.

## <a name="editing-editorconfig-files"></a>EditorConfig dosyalarını düzenleme

Visual Studio düzenlemenize yardımcı *.editorconfig* IntelliSense tamamlanma listeleri sağlayarak dosyaları.

![Bir .editorconfig dosyasında IntelliSense](media/editorconfig-intellisense-no-extension.png)

EditorConfig dosyanızı düzenlenebilir sonra yeni ayarların etkili olması için kod dosyaları yeniden yüklemeniz gerekir.

Çok sayıda düzenlerseniz *.editorconfig* dosyaları, fark edebilirsiniz [EditorConfig dil hizmeti uzantı](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) yararlıdır. Bu uzantı özelliklerinden bazıları, sözdizimi vurgulama, geliştirilmiş IntelliSense, doğrulama ve biçimlendirme kodu içerir.

![IntelliSense EditorConfig dil hizmeti uzantı ile](media/editorconfig-intellisense.png)

## <a name="example"></a>Örnek

Aşağıdaki örnek bir C# kod parçacığı girinti durumunu, önce ve ekledikten sonra gösterir. bir *.editorconfig* projesine dosyasını. **Sekmeleri** ayarı **seçenekleri** Visual Studio Metin Düzenleyici iletişim kutusunu bastığınızda boşluk karakterleri üretmek için ayarlanmış **sekmesini** anahtarı.

![Metin Düzenleyici sekme ayarı](../ide/media/vside_editorconfig_tabsetting.png)

Beklendiği gibi tuşuna basarak **sekmesini** sonraki satıra anahtar dört ek boşluk karakterleri ekleyerek satır girintileri.

![EditorConfig kullanmadan önce kod](../ide/media/vside_editorconfig_before.png)

Adlı yeni bir dosya ekleme *.editorconfig* projeye aşağıdaki içeriğe sahip. `[*.cs]` Ayarlama, bu değişikliği yalnızca C# kod dosyaları proje uygulandığı anlamına gelir.

```EditorConfig
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

Bu olması durumunda tüm Düzenleyicisi ayarlarında anlamına gelir **Araçları** > **seçenekleri** > **metin düzenleyici** (örneğin, girinti boyut ve stil, sekme boyutu veya kodlama kuralları) veya üstü dizin yapısını projesinde EditorConfig dosyasındaki belirtilirse, kuralları EditorConfig dosyasındaki ayarları geçersiz kılan **seçenekleri**. Bu davranışı değiştirerek denetleyebilirsiniz **kodlama kuralları izleyin proje** seçeneğini **Araçları** > **seçenekleri**  >  **Metin düzenleyici**. Seçeneğini işaretleyerek Visual Studio EditorConfig desteği kapatır.

![Araçlar Seçenekler - izleyin proje kodlama kuralları](media/coding_conventions_option.png)

Herhangi bir bulabilirsiniz *.editorconfig* bir komut istemi açıp projenizi içeren disk kökünden aşağıdaki komutu çalıştırarak üst dizinlerdeki dosyaları:

```Shell
dir .editorconfig /s
```

Ayarlayarak EditorConfig kuralları kapsamını denetleyebilirsiniz ```root=true``` özelliğinde *.editorconfig* , depodaki veya projenizin bulunduğu dizin kökündeki dosya. Visual Studio arar adlı bir dosya için *.editorconfig* açılan dosyayı dizin ve her üst dizini. Kök filepath ulaştığında veya arama biten bir *.editorconfig* ile dosya ```root=true``` bulunur.

## <a name="see-also"></a>Ayrıca bkz.

- [.NET kodu stil kuralları](../ide/editorconfig-code-style-settings-reference.md)
- [.NET adlandırma kuralları](../ide/editorconfig-naming-conventions.md)
- [İçin bir dil hizmeti EditorConfig destekleme](../extensibility/supporting-editorconfig.md)
- [EditorConfig.org](http://editorconfig.org/)
- [Kod Düzenleyicisi özellikleri](writing-code-in-the-code-and-text-editor.md)