---
title: Python uygulaması projeleri yönetme
description: Visual Studio projelerinde amacı oluşturma ve Python için Python kodunda hata ayıklama ve farklı proje şablonları kullanılabilir projeleri yönetin.
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 7a4374a389176273f7ceaa63b680868fd546398e
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38778527"
---
# <a name="python-projects-in-visual-studio"></a>Visual Studio'da Python projeleri

Python uygulamaları, genellikle yalnızca klasörleri ve dosyaları kullanılarak tanımlanır, ancak uygulamalar daha büyük hale gelir ve belki de JavaScript web uygulamaları için otomatik olarak oluşturulan dosyaları içeren vb. gibi bu yapı karmaşık hale gelebilir. Visual Studio projesi Bu karmaşıklığı yönetmenize yardımcı olur. Proje (bir `.pyproj` dosyası) kaynak ve projenizle ilişkili içerik dosyalarını tanımlar, her dosyanın derleme bilgilerini içeren, kaynak denetimi sistemleriyle tümleştirmeyi bilgilerini korur ve uygulamanızı düzenlemenize yardımcı olur mantıksal bileşenlerine.

![Çözüm Gezgini'nde proje Python](media/projects-solution-explorer.png)

Projeleri Visual Studio'da her zaman ek olarak, yönetilen *çözüm*, herhangi bir sayıda birbirlerine başvurabilir projeleri içerebilir. Örneğin, bir Python projesi bir uzantı modülü uygulayan bir C++ projesi başvurabilir. Python projesi hata ayıklamaya başladığınızda bu ilişki ile Visual Studio C++ projesi (gerekirse) otomatik olarak oluşturur. (Genel tartışma için bkz: [Visual Studio'da projeler ve çözümler](../ide/solutions-and-projects-in-visual-studio.md).)

Visual Studio, çeşitli uygulama yapılarının bir projeden varolan bir klasör ağacı oluşturmak için bir şablon ve temiz, boş bir proje oluşturmak için bir şablon dahil olmak üzere, bir numarası hızlı bir şekilde ayarlamak için Python proje şablonları sağlar. Bkz: [proje şablonları](#project-templates) bir dizin için.

<a name="lightweight-usage-project-free"></a>

> [!Tip]
> Bir proje bile Visual Studio da Python kodu ile çalışır. Örneğin, bir Python dosyası kendisi tarafından ve otomatik tamamlama keyfini açık, IntelliSense ve hata ayıklama (Düzenleyicisi'nde sağ tıklatıp seçerek **Başlat [ile | olmadan] hata ayıklama**). Bu tür kod her zaman varsayılan genel ortam kullandığından, kodu farklı bir ortam için tasarlanmıştır ancak yanlış tamamlama veya hataları görebilirsiniz. Ayrıca, Visual Studio, tüm dosyaları ve paketleri içinden tek dosya açıldığında, klasörde önemli miktarda CPU süresi kullanabilecek analiz eder.
>
> Bölümünde anlatıldığı gibi varolan koddan bir Visual Studio projesi oluşturmak için birkaç basit olan [varolan dosyalarından proje oluşturma](#creating-a-project-from-existing-files).

|   |   |
|---|---|
| ![video kamera simgesini film](../install/media/video-icon.png "bir video izleyin") | [(Microsoft Virtual Academy) videoyu](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Getting-Python-Code-iLAv23LWE_3905918567) Python projeleri (2 dk. 17s) giriş. |
| ![video kamera simgesini film](../install/media/video-icon.png "bir video izleyin") | Ayrıca bkz: [yakından bakış: kaynak denetimi Python projeleri ile kullanma](https://youtu.be/Aq8eqApnugM) (youtube.com, 8 dk 55s). |

## <a name="adding-files-assigning-a-startup-file-and-setting-environments"></a>Dosya ekleme, bir başlangıç dosyası atama ve ortamları ayarlama

Uygulamanızı geliştirirken, genellikle farklı türdeki yeni dosyalar projeye eklemeniz gerekir. Bu tür dosyaları ekleyerek yapılır projeyi sağ tıklatıp seçerek **Ekle** > **var olan öğe** eklemek bir dosya için Gözat ile veya **Ekle**  >  **Yeni öğe**, öğe şablonları çeşitli olan bir iletişim getirir. Üzerinde açıklandığı [öğe şablonları](python-item-templates.md) başvuru seçenekleriniz boş python dosyaları, bir python sınıfı, bir birim testi ve web uygulamaları için ilgili çeşitli dosyaları. Visual Studio sürümünüz kullanılabilir öğrenmek için bu seçenekler bir test projesi ile keşfedebilirsiniz.

Her Python projesi kalın Çözüm Gezgini'nde gösterilen bir atanan başlangıç dosyası vardır. Başlangıç dosyası hata ayıklamaya başladığınızda çalıştırılan dosyasıdır (F5 veya **hata ayıklama** > **hata ayıklamayı Başlat**) veya projenize etkileşimli pencerede çalıştırdığınızda (Shift + Alt + F5 veya  **Hata ayıklama** > **proje Python etkileşimli içinde Yürüt**). Bunu değiştirmek için yeni dosyaya sağ tıklayın ve seçin **başlangıç dosyası olarak ayarla**.

> [!Tip]
> Seçilen başlangıç dosyasını projeden kaldırın ve yeni bir tane seçmeyin, Visual Studio projeyi çalıştırmak çalıştığınızda ne Python aşağıdaki başlamak dosya bilemezsiniz. Bu durumda, Visual Studio 2017 sürüm 15.6 ve daha sonra bir hata gösterir. önceki sürümlerinde, bir çıkış penceresine ya da çalışan bir Python yorumlayıcısı ile açın. veya çıkış penceresi görünür ancak hemen kaybolur görürsünüz. Bu davranışların karşılaşırsanız, bir atanan başlangıç dosyası olduğunu denetleyin.
>
> Çıkış penceresinde herhangi bir nedenle açık tutmak istiyorsanız, projenize sağ tıklayın, **özellikleri**seçin **hata ayıklama** sekmesine ve ardından eklemek `-i` için **yorumlayıcı bağımsız değişkenleri**  alan. Bu bağımsız değişken, böylece Ctrl + Z, çıkmak için Enter girene kadar penceresi açık tutulması bir program tamamlandıktan sonra etkileşimli moduna geçin yorumlayıcı neden olur.

Yeni bir proje her zaman varsayılan global Python ortamı ile ilişkilidir. Proje (sanal ortamlar dahil) için farklı bir ortam ilişkilendirin, sağ **Python ortamları** seçin proje düğümü **Ekle/Kaldır Python ortamları**, ve istediklerinizi seçin. Etkin ortamı değiştirmek için olduğu istenen ortama sağ tıklayıp **etkinleştirme ortam** aşağıda gösterildiği gibi. Daha fazla bilgi için [bir proje için bir ortam seçerek](selecting-a-python-environment-for-a-project.md).

![Python projesi için bir ortam etkinleştirme](media/projects-activate-environment.png)

<a name="project-types"></a>

## <a name="project-templates"></a>Proje şablonları

Visual Studio, bir Python projesi sıfırdan veya mevcut koddan ayarlamak için çeşitli yollarla sağlar. Bir şablonu kullanmak için **dosya** > **yeni** > **proje** menü komutu ya da çözüm Solution Explorer seçip sağ tıklayın. **Ekle** > **yeni proje**, ikisi için de Getir **yeni proje** aşağıdaki iletişim. Python özel şablonları görmek için "Python" üzerinde arayın veya seçin **yüklü** > **Python** düğüm:

![Python şablonlarla yeni proje iletişim kutusu](media/projects-new-project-dialog.png)

(Tüm şablonları tüm önceki sürümlerinde mevcuttur) Visual Studio 2017'de kullanılabilir şablonları aşağıdaki tabloda özetlenmiştir:

| Şablon | Açıklama |
| --- | --- |
| [Mevcut Python kodu](#creating-a-project-from-existing-files) | Visual Studio projesi klasörü yapısı içinde mevcut Python kodu oluşturur.  |
| Python uygulaması | Tek ve boş bir dosya ile yeni bir Python uygulaması için bir temel Proje yapısı. Varsayılan olarak, proje tarafından değiştirebileceğiniz varsayılan genel ortamın konsol yorumlayıcı çalışan [farklı bir ortama atama](selecting-a-python-environment-for-a-project.md). |
| [Azure bulut hizmeti](python-azure-cloud-service-project-template.md) | Python'da yazılmış bir Azure bulut hizmeti için bir proje. |
| [Web projeleri](python-web-application-project-templates.md) | Bottle, Django ve Flask gibi çeşitli çerçevelerini temel alan web apps için proje. |
| Aplikace v Ironpythonu | Benzer şekilde kullanır ancak Python uygulaması şablonu tarafından IronPython varsayılan etkinleştirme .NET birlikte çalışabilirlik ve karma mod .NET dilleri ile hata ayıklama. |
| Aplikace WPF v Ironpythonu | IronPython, Windows Presentation Foundation XAML dosyaları için uygulamanın kullanıcı arabirimini kullanarak bir proje yapısı. Visual Studio XAML Tasarımcısı sağlar, arka plan kod Python'da yazılabilir ve uygulama konsol görüntülemeden çalışır. |
| IronPython Silverlight Web sayfası | Silverlight'ı kullanarak bir tarayıcıda çalışan IronPython projesi. Uygulamanın Python kodu web sayfasına komut dosyası olarak dahil edilir. Ortak komut dosyası etiketi Python kodunuzu DOM ile etkileşim kurabilir Silverlight içinde çalışan IronPython başlatır miktar JavaScript kodu aşağı çeker |
| IronPython Windows Formları uygulaması | Windows Forms ile kod kullanılarak oluşturulan IronPython withUI kullanarak bir proje yapısı. Uygulama, bir konsolu görüntülemeden çalışır. |
| Arka plan uygulama (IOT) | Arka plan Hizmetleri cihazlarda çalıştırmak için Python projeleri dağıtılmasını destekler. Ziyaret [Windows IOT Geliştirme Merkezi](https://dev.windows.com/en-us/iot) daha fazla bilgi için. |
| Python uzantı Modülü | Bu şablon yüklediğiniz Visual C++ altında görünür **Python yerel geliştirme araçları** Python iş yüküyle Visual Studio 2017'de (bkz [yükleme](installing-python-support-in-visual-studio.md)). Çekirdek yapısı için C++ Uzantısı DLL, üzerinde açıklanana için benzer sağladığı [Python için C++ uzantısı oluşturma](working-with-c-cpp-python-in-visual-studio.md). |

> [!Note]
> Python yorumlanan bir dil olduğundan, Visual Studio'da Python projeleri bir tek başına yürütülebilir dosya gibi diğer derlenmiş dili projeler (C#, örneğin) üretmediği. Daha fazla bilgi için [sorularını ve yanıtlarını](overview-of-python-tools-for-visual-studio.md#questions-and-answers).

<a name="create-project-from-existing-files"></a>

### <a name="creating-a-project-from-existing-files"></a>Varolan dosyalarından proje oluşturma

> [!Important]
> Burada açıklanan işlemi taşıma veya kopyalama orijinal kaynak dosyalarına desteklemez. Bir kopya ile çalışmak istiyorsanız, klasörü ilk çoğaltma.

[!INCLUDE[project-from-existing](includes/project-from-existing.md)]

## <a name="linked-files"></a>Bağlantılı dosyaları

Bağlı dosyalar projeye kapsama alınır, ancak genellikle uygulamanın proje klasörleri dışında bulunan dosyalardır. Çözüm Gezgini'nde Kaplanmış kısayol simge normal dosyalarıyla olarak görünürler: ![Bağlı dosya simgesi](media/projects-linked-file-icon.png)

İçinde belirtilen bağlantılı dosyaları `.pyproj` kullanarak dosya `<Compile Include="...">` öğesi. Dizin yapısı dışında göreli bir yol kullanıyorlarsa örtük veya açık Çözüm Gezgini içindeki yollara kullanıyorlarsa bağlantılı dosyaları şunlardır:

```xml
<Compile Include="..\test2.py">
    <Link>MyProject\test2.py</Link>
</Compile>
```

Bağlantılı dosyaları aşağıdaki koşullardan herhangi biri altında göz ardı edilir:

- Bağlı dosya bağlantı meta verileri ve proje dizininden INCLUDE özniteliği olduğu belirtilen yolu içerir.
- Bağlı dosya proje hiyerarşisi içinde var olan bir dosya yineleme
- Bağlı dosya bağlantı meta verileri içeriyorsa ve bağlantı yolu göreli bir yol proje hiyerarşisi dışında
- Bağlantı yolunun kökü

### <a name="work-with-linked-files"></a>Bağlantılı dosyaları ile çalışma

Var olan bir öğeye bir bağlantı olarak eklemek istediğiniz dosyayı ekleyin, ardından seçin proje klasöre sağ tıklayın **Ekle > öğesi çıkılıyor...** . Görüntülenen iletişim kutusunda, bir dosya seçip **bağlantı olarak Ekle** açılır listeden **Ekle** düğmesi. Koşuluyla çakışan dosya yok, bu komut, seçili klasörde bulunan bir bağlantı oluşturur. Ancak, bu dosyanın bir bağlantısını projesinde zaten var veya aynı ada sahip bir dosya zaten var. bağlantı eklenmez.

Proje klasörleri zaten var olan bir bağlantı çalışırsanız, bir bağlantı değil de, normal bir dosya olarak eklenir. Bir dosya bir bağlantıya dönüştürülecek seçin **Dosya > Farklı Kaydet** dosyası; proje hiyerarşisi dışındaki bir konuma kaydetmek için Visual Studio otomatik olarak bağlantıya dönüştürür. Benzer şekilde, bir bağlantı geri kullanarak dönüştürülebilir **Dosya > Farklı Kaydet** dosyayı proje hiyerarşisi içinde herhangi bir yerde kaydetmek için. 

Çözüm Gezgini'nde bir dosyaya taşırsanız, bağlantıyı taşınır, ancak gerçek dosyayı etkilenmez. Benzer şekilde, bir bağlantının silinmesi bağlantı dosyasını etkilemeden kaldırır.

Bağlantılı dosyaları yeniden adlandırılamaz.

## <a name="references"></a>Referanslar

Visual Studio projeleri projeler ve altında görünen uzantıları başvuruları ekleme desteği **başvuruları** Çözüm Gezgininde:

![Python projeleri uzantısı başvuruları](media/projects-extension-references.png)

Uzantı başvuruları genellikle projeleri arasındaki bağımlılıkları göstermek ve tasarım zamanı veya derleme zamanında bağlama IntelliSense sağlamak için kullanılır. Python projeleri benzer şekilde başvuruları kullanın, ancak Python dinamik doğası nedeniyle öncelikle tasarım zamanında geliştirilmiş IntelliSense sağlamak için kullanılırlar. Bunlar ayrıca Microsoft Azure'a dağıtılacak Ek Bağımlılıklar'ı yüklemek için kullanılabilir.

### <a name="extension-modules"></a>Uzantı modüllerini

Bir başvuru bir `.pyd` dosyası oluşturulan modülü için IntelliSense sağlar. Visual Studio yükler `.pyd` dosya Python yorumlayıcısı yüklenir ve kendi türleri ve işlevleri içeriğini gözlemleyip. İmza Yardımı sağlamak işlevleri için belge dizelerini ayrıştırmak de çalışır.

Herhangi bir zamanda uzantı modülü diskte güncelleştirdiyseniz, Visual Studio arka planda modülü çözümlemeden. Bu eylem, çalışma zamanı davranışı üzerinde etkiye sahip değildir, ancak bazı tamamlamaları analiz tamamlanana kadar kullanılamaz.

Eklemeniz gerekebilir bir [arama yolu](search-paths.md) modülü içeren klasör.

### <a name="net-projects"></a>.NET projeleri

IronPython ile çalışırken, IntelliSense etkinleştirmek için .NET derlemelerine başvurular ekleyebilirsiniz. Çözümünüzdeki .NET projeleri için sağ **başvuruları** Python projenizin, seçme düğümünde **Başvuru Ekle**seçin **projeleri** sekmesini tıklatıp göz atın İstenen proje. Ayrı olarak yüklenen DLL'ler için seçin **Gözat** yerine sekmesini ve istenen DLL'ye göz atın.

IronPython başvuruları çağrısı kadar kullanılabilir değil çünkü `clr.AddReference('AssemblyName')` olan yapılan, sizin de eklemeniz gerekir bir `clr.AddReference` derlemeye çağırın.

### <a name="webpi-projects"></a>Webpı projeleri

Microsoft Azure bulut hizmetlerine Webpı aracılığıyla ek bileşenler yükleyebileceği dağıtım için Webpı ürün girişleri başvuruları ekleyebilirsiniz. Varsayılan olarak görüntülenen akış Python özgü olan ve Django CPython ve diğer temel bileşenleri içerir. Kendi akışınızı, aşağıda gösterildiği gibi de seçebilirsiniz. Microsoft Azure'a yayımlarken, Kurulum görev tüm başvurulan ürünleri yükler.

![Webpı başvuruları](media/projects-webPI-components.png)