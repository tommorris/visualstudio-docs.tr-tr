---
title: Visual Studio'da Python projeleri | Microsoft Docs
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 44065522229a1661efc41e79905d9650f7949ac3
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2017
---
# <a name="python-projects"></a>Python projeleri

Python uygulamaları, genellikle yalnızca klasörleri ve dosyaları kullanılarak tanımlanır, ancak uygulamalar daha büyük hale ve belki de JavaScript web uygulamaları için otomatik olarak oluşturulan dosyaları içeren vb. gibi bu yapı karmaşık olabilir. Bu karışıklığı yönetmenize yardımcı olmak için Python uygulamalar için Visual Studio projeleri oluşturabilirsiniz. Python proje (bir `.pyproj` dosyası) kaynak ve projenizi ile ilişkili içerik dosyalarını tanımlar, her dosya için yapı bilgileri içerir, kaynak denetimi sistemleriyle tümleştirmeyi bilgilerini korur ve düzenlemenize yardımcı olur, mantıksal bileşenlerin uygulamasına.

Ayrıca, proje bir Visual Studio içinde her zaman yönetilir *çözüm*, birbirine başvurabilir projeleri herhangi bir sayıda içerebilir. Örneğin, Python projenin hata ayıklamasını başlattığınızda derlemeler Visual Studio otomatik olarak C++ projesi (gerekiyorsa), bir Python proje uzantısı modülü için C++ projesi başvuruda bulunabilir. (Bir genel tartışma için bkz: [çözümler ve projeler Visual Studio'da](../ide/solutions-and-projects-in-visual-studio.md).)

![Çözüm Gezgini'nde Python projesi](media/projects-solution-explorer.png)

Visual Studio Python proje şablonları varolan bir klasör ağacında bir proje oluşturmak için bir şablon ve temiz, boş bir proje oluşturmak için bir şablon dahil olmak üzere uygulama yapıların bir numarası hızlı bir şekilde ayarlamak için çeşitli sağlar. Bkz: [proje şablonlarını](#project-templates) altındaki bir dizin için.

Bu konuda:

- [Dosya ekleme, bir başlatma dosyası atama ve ortamları ayarlama](#adding-files-assigning-a-startup-file-and-setting-environments)
- [Proje şablonları](#project-templates)
- [Bağlantılı dosyaları](#linked-files)
- [Başvuruları](#references)

< a name = "Basit-kullanım-proje-boş"</a>
> [!Tip]
> Yaptığınız gibi bir projeyi bile olmadan Visual Studio Python kodu ile de çalışır. bir Python tek başına dosya ve otomatik tamamlama keyfini açık, IntellSense ve hata ayıklama (Düzenleyicisi'nde sağ tıklatıp seçerek **Başlat [ile | olmadan]hataayıklama**). Bu kodu her zaman varsayılan genel ortam kullandığından, kodu farklı bir ortamı için tasarlanmıştır ancak, yanlış tamamlamalar veya hatalar görebilirsiniz. Ayrıca, Visual Studio, tüm dosyaları ve önemli ölçüde CPU süresi tüketebilir içinden tek dosya açıldığında, klasöründe paketleri analiz eder.
>
> Aşağıda açıklandığı gibi basit sağlasa da var olan koddan bir Visual Studio projesi oluşturmak için olan [var olan dosyalarından proje oluşturma](#creating-a-project-from-existing-files).

Video Visual Studio'da Python projeleri giriş için bkz [alma Python kodu](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=iLAv23LWE_3905918567) (Microsoft Virtual Academy, 2m17s).

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Getting-Python-Code-iLAv23LWE_3905918567]

Ayrıca bkz. eski video [derinlemesine: Python projeleri ile kaynak denetimi kullanarak](https://youtu.be/Aq8eqApnugM) (youtube.com, 8m55s).

## <a name="adding-files-assigning-a-startup-file-and-setting-environments"></a>Dosya ekleme, bir başlatma dosyası atama ve ortamları ayarlama

Uygulamanızı geliştirirken, genellikle farklı türdeki yeni dosyaları projeye eklemeniz gerekir. Bu tür dosyaları ekleme kolayca yapılır projeye sağ tıklayıp seçerek **Ekle > varolan öğeyi...** , bir dosya eklemek, Gözat ile veya **Ekle > Yeni öğe...** çeşitli dosyaları ilgili web uygulamaları ve öğe şablonları boş python dosyaları, python sınıfı bir birim testi dahil olmak üzere çeşitli iletişim kutusunu getirir. Hangi sürümü Visual Studio'nun kullanılabilir olduğunu öğrenmek için bir test projesi bu seçeneklerle keşfetmek için öneririz.

Çözüm Gezgini'nde kalın gösterilen bir atanan başlangıç dosyasını her Python projenin vardır. Başlangıç dosyası hata ayıklama başlattığınızda çalıştırılan dosyasıdır (F5 veya **hata ayıklama > hata ayıklamayı Başlat**) veya etkileşimli pencerede projenizi çalıştırma (Shift + Alt + F5 veya **hata ayıklama > Execute projesinde Python etkileşimli**). Değiştirmek için yeni dosyasını sağ tıklatın ve seçin **başlangıç dosyası olarak ayarlamak**.

> [!Tip]
> Seçilen başlangıç dosyası bir projeden kaldırmak ve yeni bir tane seçmezseniz, proje sonuçlarınızı bir Python çalıştırma denemesi ancak sonra görünen ve hemen kayboluyor penceresi çıktı. Bu davranış karşılaşırsanız, atanan başlangıç dosya olup olmadığını denetleyin. Ayrıca, çıktı penceresinde bu gibi durumlarda açık tutmak için projenize sağ tıklayın, seçin **özellikleri**seçin **hata ayıklama** sekmesinde, ardından ekleyin `-i` için **yorumlayıcı bağımsız değişkenleri** alan. Bu bağımsız değişken, böylece Ctrl + Z, çıkmak için Enter girene kadar penceresi açık tutarak bir program tamamlandıktan sonra etkileşimli moduna geçmesi yorumlayıcı neden olur.

Yeni bir proje her zaman varsayılan genel Python ortamı ile ilişkilidir. Proje (sanal ortamlar dahil) için farklı bir ortam ilişkilendirmek için ile sağ **Python ortamları** seçin proje düğümüne **Ekle/Kaldır Python ortamları**, ve istediğiniz şablonu seçin. Etkin ortam değiştirmek için istenen ortama sağ tıklatın ve seçin **etkinleştirme ortamı** aşağıda gösterildiği gibi. Daha fazla ayrıntı için bkz: [Python ortamları](python-environments.md#project-specific-environments).

![Python proje için bir ortam etkinleştirme](media/projects-activate-environment.png)

< a name = "proje türleri"</a>
## <a name="project-templates"></a>Proje şablonları

Visual Studio bir Python proje, sıfırdan veya var olan koddan ayarlamak için çeşitli yöntemler sağlar. Bir şablonu kullanmak için **Dosya > Yeni > Proje...**  menü komutu ya da çözüm Çözüm Gezgini seçip sağ **Ekle > Yeni proje...** , her ikisi de Getir **yeni proje** aşağıdaki iletişim. Python özel şablonları görmek için arama "Python" ya da seçin **şablonları > Diğer diller > Python** düğümü:

![Python şablonlarla yeni proje iletişim kutusu](media/projects-new-project-dialog.png)

Aşağıdaki tabloda, Visual Studio (tüm şablonları tüm önceki sürümlerinde kullanılabilir) 2017 kullanılabilir şablonlar özetlenmektedir:

| Şablon | Açıklama | 
| --- | --- |
| [Varolan Python koddan](#creating-a-project-from-existing-files) | Visual Studio projesi klasörü yapısı içinde varolan Python kodu oluşturur.  |
| Python uygulama | Tek ve boş kaynak dosyası içeren yeni bir Python uygulaması için bir temel Proje yapısı. Varsayılan olarak, projeyi tarafından değiştirebileceğiniz varsayılan genel ortamının konsol yorumlayıcı çalışır [farklı bir ortam atama](python-environments.md#project-specific-environments). |
| [Azure bulut hizmeti](template-azure-cloud-service.md) | Python içinde yazılmış bir Azure bulut hizmeti için bir proje. |
| [Web projeleri](template-web.md) | Proje Bottle, Django, Flask ve Flask/Jade dahil olmak üzere çeşitli çerçevesinde bağlı web sunucuları için. |
| IronPython uygulama | Benzer şekilde kullanır ancak Python uygulama şablonu tarafından IronPython varsayılan etkinleştirme .NET birlikte çalışabilirlik ve karma mod .NET dilleri ile hata ayıklama. |
| IronPython WPF uygulaması | Uygulamanın kullanıcı arabirimi için Windows Presentation Foundation XAML dosyalarla IronPython kullanarak proje yapısı. Visual Studio XAML kullanıcı Arabirimi Tasarımcısı sağlar, arka plan kodu Python içinde yazılmış ve bir konsol görüntülemeden uygulamayı çalıştırır. |
| IronPython Silverlight Web sayfası | Silverlight kullanarak bir tarayıcıda çalışan IronPython projesi. Uygulamanın Python kodu web sayfasındaki komut dosyası olarak dahil edilir. Python kodunuzu DOM ile etkileşim kurabilen Silverlight içinde çalışan IronPython başlatır bazı JavaScript kodları aşağı Demirbaş komut dosyası etiketinin çeker |
| Uygulama IronPython Windows Forms | Windows Forms ile kod kullanılarak oluşturulan IronPython withUI kullanarak proje yapısı. Uygulama, bir konsol görüntülemeden çalışır. |
| Arka planda (IOT) | Arka plan Hizmetleri cihazlarda çalıştırmak için Python projeleri dağıtılmasını destekler. Ziyaret [Windows IOT Geliştirme Merkezi](https://dev.windows.com/en-us/iot) daha fazla bilgi için. |
| Python Uzantısı Modülü | Bu şablon yüklediğiniz Visual C++ altında görünür **Python yerel geliştirme araçları** Visual Studio 2017 Python yükündeki ile (bkz [yükleme](installation.md)). C++ uzantı DLL'si, ne üzerinde açıklanan için benzer için çekirdek yapısı sağlar [Python için C++ uzantısı oluşturma](cpp-and-python.md). |

< a name = "Oluştur-proje--varolan-dosyaları"</a>

### <a name="creating-a-project-from-existing-files"></a>Var olan dosyalarından proje oluşturma

> [!Important]
> Burada anlatılan işlemine taşımayın veya özgün kaynak dosyalarını kopyalayın. Bir kopya ile çalışmak isterseniz, klasörü ilk çoğaltma.

[!INCLUDE[project-from-existing](includes/project-from-existing.md)]

## <a name="linked-files"></a>Bağlantılı dosyaları

Bir projeye ancak genellikle duruma dosyaları uygulamanın proje klasörleri dışında bulunan bağlantılı dosyalarıdır. Çözüm Gezgini'nde Kaplanmış kısayol simge normal dosyaları olarak göründükleri: ![Bağlı dosya simgesi](media/projects-linked-file-icon.png)

Bağlantılı dosyaları belirtilir `.pyproj` normal kullanarak dosya `<Compile Include="...">` öğesi. Dizin yapısı dışında göreli bir yol kullanın veya açık bağlantı dosyalarını Solution Explorer içinde kendi yolunu belirterek olabilirler bunlar örtük bağlantılı dosyaları olabilir:

```xml
<Compile Include="..\test2.py">
    <Link>MyProject\test2.py</Link>
</Compile>
```

Bağlantılı dosyaları aşağıdaki koşullardan herhangi biri altında göz ardı edilir:

- Bağlantı meta verileri ve INCLUDE özniteliği yaşamlarını proje dizininin içinde belirtilen yola bağlı dosya içerir
- Proje hiyerarşisi içinde varolan bir dosyayı bağlı dosya yineleme
- Bağlı dosya bağlantı meta verileri içeren ve bağlantı yolu göreli bir yol proje hiyerarşisi dışında olan
- Bağlantı yolu kökü belirtilmiş

### <a name="working-with-linked-files"></a>Bağlantılı dosyalarıyla çalışma

Varolan bir bağlantı olarak eklemek için proje dosyası ekleyin, ardından seçin istediğiniz yere klasörü sağ tıklatın **Ekle > öğesi çıkılıyor...** . Görüntülenen iletişim kutusunda, bir dosya seçin ve Seç **bağlantı olarak Ekle** açılan gelen **Ekle** düğmesi. Koşuluyla çakışan dosya yok, bu komut seçilen klasörde bir bağlantı oluşturur. Ancak, bağlantı zaten aynı ada sahip bir dosya veya bu dosyaya bir bağlantı projede zaten eklenmez.

Proje klasörlerde zaten bir dosyaya bağlantı çalışırsanız, bir bağlantı değil de, normal bir dosya olarak eklenir. Bir dosyayı bir bağlantıya dönüştürülecek seçin **Dosya > Kaydet** proje hiyerarşisi; dışındaki bir konuma dosyayı kaydetmek için Visual Studio otomatik olarak bir bağlantıya dönüştürür. Benzer şekilde, bir bağlantı geri kullanarak dönüştürülebilir **Dosya > Kaydet** dosyayı proje hiyerarşi içinde herhangi bir yerde kaydetmek için. 

Çözüm Gezgini'nde bağlı bir dosya taşırsanız, bağlantıyı taşınır, ancak gerçek dosya etkilenmez. Benzer şekilde, bir bağlantının silinmesi bağlantıyı dosyasını etkilemeden kaldırır.

Bağlantılı dosyaları yeniden adlandırılamaz.

## <a name="references"></a>Referanslar

Visual Studio projeleri projeleri ve altında göründüğünü uzantıları başvuruları ekleme desteği **başvuruları** Çözüm Gezgini'nde düğümü:

![Python projeleri uzantısı başvuruları](media/projects-extension-references.png)

Uzantı Başvurular genellikle projeleri arasındaki bağımlılıkları belirtmek ve tasarım zamanı ya da derleme zamanında bağlama IntelliSense sağlamak için kullanılır. Python projeleri başvuruları benzer bir şekilde kullanır, ancak Python dinamik yapısı nedeniyle, öncelikle tasarım zamanında geliştirilmiş IntelliSense sağlamak için kullanılır. Bunlar aynı zamanda Microsoft Azure dağıtımı için ek bağımlılıklar yüklemek için kullanılabilir.

### <a name="extension-modules"></a>Uzantı modülleri

Bir başvuru bir `.pyd` dosyası için oluşturulan modülü IntelliSense sağlar. Visual Studio yükler `.pyd` dosya Python yorumlayıcı yüklenir ve onun türler ve İşlevler introspects. İmza Yardım sağlamak üzere işlevleri için belge dizeleri ayrıştırmak de çalışır.

Herhangi bir zamanda diskte uzantısı modülü güncelleştirilirse, Visual Studio arka planda modülü çözümlemeden. Bu eylem çalışma zamanı davranışı üzerinde hiçbir etkisi yoktur, ancak çözümleme işlemi tamamlanana kadar bazı tamamlamalar kullanılamaz.

Eklemeniz gerekebilir bir [arama yolu](python-environments.md#search-paths) modülü içeren klasör için.

### <a name="net-projects"></a>.NET projeleri

IronPython ile çalışırken, IntelliSense etkinleştirmek için .NET derleme başvurularını ekleyebilirsiniz. Çözümünüzdeki .NET projeleri için sağ **başvuruları** düğümünü seçin, Python projenizdeki **Başvuru Ekle**seçin **projeleri** sekmesini tıklatın ve göz atın İstenen projesi. Ayrı ayrı indirdiğiniz DLL'leri seçin **Gözat** yerine sekmesinde ve istenen DLL göz atın.

IronPython başvurularında yapılan bir çağrı kadar kullanılabilir olmadığından `clr.AddReference('AssemblyName')` olan yapılan, ayrıca eklemeniz gerekir bir `clr.AddReference` derlemeye çağırın.

### <a name="webpi-projects"></a>Webpı projeleri

Microsoft Azure bulut hizmeti, akış Webpı üzerinden ek bileşenleri yükleyebileceğiniz Webpı ürün girdileri dağıtımı için başvurular ekleyin. Varsayılan olarak, görüntülenen akış Python özeldir ve Django, CPython ve diğer temel bileşenleri içerir. Ayrıca, aşağıda gösterildiği gibi kendi akış seçebilirsiniz. Microsoft Azure yayımlama sırasında Kurulum görev tüm başvurulan ürünleri yükler.

![Webpı başvuruları](media/projects-webPI-components.png)