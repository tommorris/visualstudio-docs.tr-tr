---
title: "Visual Studio'da Python uygulamaları için projeleri yönetme | Microsoft Docs"
description: "Visual Studio projelerinde amacını açıklayan, Python kodu için proje oluşturma ve yönetme gösterir ve Python için kullanılabilen farklı proje şablonları özetler."
ms.custom: 
ms.date: 03/05/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: d996c99104e0a5d6b2e1acdb44273679a3998658
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="python-projects"></a>Python projeleri

Python uygulamaları, genellikle yalnızca klasörleri ve dosyaları kullanılarak tanımlanır, ancak uygulamalar daha büyük hale ve belki de JavaScript web uygulamaları için otomatik olarak oluşturulan dosyaları içeren vb. gibi bu yapı karmaşık olabilir. Visual Studio projesi bu karışıklığı yönetmenize yardımcı olur. Proje (bir `.pyproj` dosyası) kaynak ve projenizi ile ilişkili içerik dosyalarını tanımlar, her dosya için yapı bilgileri içerir, kaynak denetimi sistemleriyle tümleştirmeyi bilgilerini korur ve uygulamanızı düzenlemenize yardımcı olur mantıksal bileşenlerine.

![Çözüm Gezgini'nde Python projesi](media/projects-solution-explorer.png)

Ayrıca, proje bir Visual Studio içinde her zaman yönetilir *çözüm*, birbirine başvurabilir projeleri herhangi bir sayıda içerebilir. Örneğin, Python proje uzantısı modülü uygulayan C++ projesi başvuruda bulunabilir. Python projenin hata ayıklamasını başlattığınızda bu ilişki ile Visual Studio C++ projesi (gerekirse) otomatik olarak oluşturur. (Bir genel tartışma için bkz: [çözümler ve projeler Visual Studio'da](../ide/solutions-and-projects-in-visual-studio.md).)

Visual Studio Python proje şablonları varolan bir klasör ağacında bir proje oluşturmak için bir şablon ve temiz, boş bir proje oluşturmak için bir şablon dahil olmak üzere uygulama yapıların bir numarası hızlı bir şekilde ayarlamak için çeşitli sağlar. Bkz: [proje şablonlarını](#project-templates) bir dizin için.

<a name="lightweight-usage-project-free"></a>

> [!Tip]
> Proje bile, Visual Studio iyi Python kodu ile çalışır. Örneğin, bir Python tek başına dosya ve otomatik tamamlama keyfini açık, IntelliSense ve hata ayıklama (Düzenleyicisi'nde sağ tıklatıp seçerek **Başlat [ile | olmadan] hata ayıklama**). Bu kodu her zaman varsayılan genel ortam kullandığından, kodu farklı bir ortamı için tasarlanmıştır ancak, yanlış tamamlamalar veya hatalar görebilirsiniz. Ayrıca, Visual Studio, tüm dosyaları ve önemli ölçüde CPU süresi tüketebilir içinden tek dosya açıldığında, klasöründe paketleri analiz eder.
>
> Bölümünde açıklandığı gibi basit sağlasa da var olan koddan bir Visual Studio projesi oluşturmak için olan [var olan dosyalarından proje oluşturma](#creating-a-project-from-existing-files).

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | [(Microsoft Virtual Academy) bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Getting-Python-Code-iLAv23LWE_3905918567) giriş Python projeleri (2 m 17s) için. |
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | Ayrıca bkz. [derinlemesine: kaynak denetimi ile Python projeleri kullanarak](https://youtu.be/Aq8eqApnugM) (youtube.com, 8 m 55s). |

## <a name="adding-files-assigning-a-startup-file-and-setting-environments"></a>Dosya ekleme, bir başlatma dosyası atama ve ortamları ayarlama

Uygulamanızı geliştirirken, genellikle farklı türdeki yeni dosyaları projeye eklemeniz gerekir. Bu tür dosyaları ekleyerek yapılır projeye sağ tıklayıp seçerek **Ekle > varolan öğeyi...** . bir dosya eklemek, Gözat ile veya **Ekle > Yeni öğe...** , öğe şablonları, çeşitli ile iletişim kurma getirir. Boş python dosyaları, python sınıfı, birim testi ve web uygulamaları için ilgili çeşitli dosya şablonları içerir. Hangi sürümü Visual Studio'nun kullanılabilir olduğunu öğrenmek için bir test projesi bu seçeneklerle keşfedebilirsiniz.

Çözüm Gezgini'nde kalın gösterilen bir atanan başlangıç dosyasını her Python projenin vardır. Başlangıç dosyası hata ayıklama başlattığınızda çalıştırılan dosyasıdır (F5 veya **hata ayıklama > hata ayıklamayı Başlat**) veya etkileşimli pencerede projenizi çalıştırdığınızda (Shift + Alt + F5 veya **hata ayıklama > Python yürütme projesinde Etkileşimli**). Değiştirmek için yeni dosyasını sağ tıklatın ve seçin **başlangıç dosyası olarak ayarlamak**.

> [!Tip]
> Seçilen başlangıç dosyası bir projeden kaldırmak ve yeni bir tane seçmezseniz, Visual Studio Proje çalıştırmayı denediğinizde ne Python aşağıdaki başlamak dosya bilemezsiniz. Bu durumda, Visual Studio 2017 15.6 ve sonraki sürümleri bir hata gösterir; önceki sürümlerinde, bir çıktı penceresi ya da çalışan Python yorumlayıcı ile açın. veya çıktı penceresini görünür ancak hemen kayboluyor bakın. Bu davranışların karşılaşırsanız, atanan başlangıç dosya olup olmadığını denetleyin.
>
> Herhangi bir nedenle çıktı penceresi açık tutmak istiyorsanız, projenize sağ tıklayın, seçin **özellikleri**seçin **hata ayıklama** sekmesinde, ardından ekleyin `-i` için **yorumlayıcı bağımsız değişkenler**  alan. Bu bağımsız değişken, böylece Ctrl + Z, çıkmak için Enter girene kadar penceresi açık tutarak bir program tamamlandıktan sonra etkileşimli moduna geçmesi yorumlayıcı neden olur.

Yeni bir proje her zaman varsayılan genel Python ortamı ile ilişkilidir. Proje (sanal ortamlar dahil) için farklı bir ortam ilişkilendirmek için sağ **Python ortamları** seçin proje düğümüne **Ekle/Kaldır Python ortamları**, ve istediğiniz şablonu seçin. Etkin ortam değiştirmek için istenen ortama sağ tıklatın ve seçin **etkinleştirme ortamı** aşağıda gösterildiği gibi. Daha fazla bilgi için bkz: [bir proje için bir ortam seçerek](selecting-a-python-environment-for-a-project.md).

![Python proje için bir ortam etkinleştirme](media/projects-activate-environment.png)

<a name="project-types"></a>

## <a name="project-templates"></a>Proje şablonları

Visual Studio bir Python proje, sıfırdan veya var olan koddan ayarlamak için çeşitli yöntemler sağlar. Bir şablonu kullanmak için **Dosya > Yeni > Proje...**  menü komutu ya da çözüm Çözüm Gezgini seçip sağ **Ekle > Yeni proje...** , her ikisi de Getir **yeni proje** aşağıdaki iletişim. Python özel şablonları görmek için arama "Python" ya da seçin **yüklü > Python** düğümü:

![Python şablonlarla yeni proje iletişim kutusu](media/projects-new-project-dialog.png)

Aşağıdaki tabloda, Visual Studio (tüm şablonları tüm önceki sürümlerinde kullanılabilir) 2017 kullanılabilir şablonlar özetlenmektedir:

| Şablon | Açıklama |
| --- | --- |
| [Varolan Python koddan](#creating-a-project-from-existing-files) | Visual Studio projesi klasörü yapısı içinde varolan Python kodu oluşturur.  |
| Python uygulama | Tek ve boş kaynak dosyası içeren yeni bir Python uygulaması için bir temel Proje yapısı. Varsayılan olarak, projeyi tarafından değiştirebileceğiniz varsayılan genel ortamının konsol yorumlayıcı çalışır [farklı bir ortam atama](selecting-a-python-environment-for-a-project.md). |
| [Azure bulut hizmeti](python-azure-cloud-service-project-template.md) | Python içinde yazılmış bir Azure bulut hizmeti için bir proje. |
| [Web projeleri](python-web-application-project-templates.md) | Proje Bottle, Django, Flask ve Flask/Jade dahil olmak üzere çeşitli çerçevesinde bağlı web sunucuları için. |
| IronPython uygulama | Benzer şekilde kullanır ancak Python uygulama şablonu tarafından IronPython varsayılan etkinleştirme .NET birlikte çalışabilirlik ve karma mod .NET dilleri ile hata ayıklama. |
| IronPython WPF uygulaması | Uygulamanın kullanıcı arabirimi için Windows Presentation Foundation XAML dosyalarla IronPython kullanarak proje yapısı. Visual Studio XAML kullanıcı Arabirimi Tasarımcısı sağlar, arka plan kodu Python içinde yazılmış ve bir konsol görüntülemeden uygulamayı çalıştırır. |
| IronPython Silverlight Web sayfası | Silverlight kullanarak bir tarayıcıda çalışan IronPython projesi. Uygulamanın Python kodu web sayfasındaki komut dosyası olarak dahil edilir. Python kodunuzu DOM ile etkileşim kurabilen Silverlight içinde çalışan IronPython başlatır bazı JavaScript kodları aşağı Demirbaş komut dosyası etiketinin çeker |
| Uygulama IronPython Windows Forms | Windows Forms ile kod kullanılarak oluşturulan IronPython withUI kullanarak proje yapısı. Uygulama, bir konsol görüntülemeden çalışır. |
| Arka planda (IOT) | Arka plan Hizmetleri cihazlarda çalıştırmak için Python projeleri dağıtılmasını destekler. Ziyaret [Windows IOT Geliştirme Merkezi](https://dev.windows.com/en-us/iot) daha fazla bilgi için. |
| Python Uzantısı Modülü | Bu şablon yüklediğiniz Visual C++ altında görünür **Python yerel geliştirme araçları** Visual Studio 2017 Python yükündeki ile (bkz [yükleme](installing-python-support-in-visual-studio.md)). C++ uzantı DLL'si, ne üzerinde açıklanan için benzer için çekirdek yapısı sağlar [Python için C++ uzantısı oluşturma](working-with-c-cpp-python-in-visual-studio.md). |

> [!Note]
> Python yorumlanan dil olduğundan, Visual Studio'da Python projeleri tek başına yürütülebilir dosya gibi diğer derlenmiş dili projeler (C#, örneğin) üretmediği. Daha fazla bilgi için bkz: [sorular ve yanıtlar](overview-of-python-tools-for-visual-studio.md#questions-and-answers).

< a name = "Oluştur-proje--varolan-dosyaları"</a>

### <a name="creating-a-project-from-existing-files"></a>Var olan dosyalarından proje oluşturma

> [!Important]
> Burada anlatılan işlemine taşımayın veya özgün kaynak dosyalarını kopyalayın. Bir kopya ile çalışmak isterseniz, klasörü ilk çoğaltma.

[!INCLUDE[project-from-existing](includes/project-from-existing.md)]

## <a name="linked-files"></a>Bağlantılı dosyaları

Bir projeye duruma getirilir ancak genellikle uygulamanın proje klasörleri dışında bulunan dosyaları bağlantılı dosyalarıdır. Çözüm Gezgini'nde Kaplanmış kısayol simge normal dosyaları olarak göründükleri: ![Bağlı dosya simgesi](media/projects-linked-file-icon.png)

Bağlantılı dosyaları belirtilir `.pyproj` kullanarak dosya `<Compile Include="...">` öğesi. Bağlantılı dosyaları dizin yapısı dışında göreli bir yol kullanırsanız, açık veya kapalı Çözüm Gezgini içindeki yollara kullanıyorsanız:

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

Eklemeniz gerekebilir bir [arama yolu](search-paths.md) modülü içeren klasör için.

### <a name="net-projects"></a>.NET projeleri

IronPython ile çalışırken, IntelliSense etkinleştirmek için .NET derleme başvurularını ekleyebilirsiniz. Çözümünüzdeki .NET projeleri için sağ **başvuruları** düğümünü seçin, Python projenizdeki **Başvuru Ekle**seçin **projeleri** sekmesini tıklatın ve göz atın İstenen projesi. Ayrı ayrı indirdiğiniz DLL'leri seçin **Gözat** yerine sekmesinde ve istenen DLL göz atın.

IronPython başvurularında yapılan bir çağrı kadar kullanılabilir olmadığından `clr.AddReference('AssemblyName')` olan yapılan, ayrıca eklemeniz gerekir bir `clr.AddReference` derlemeye çağırın.

### <a name="webpi-projects"></a>Webpı projeleri

Microsoft Azure bulut hizmetlerine, akış Webpı üzerinden ek bileşenleri yükleyebileceğiniz Webpı ürün girdileri dağıtımı için başvurular ekleyin. Varsayılan olarak, görüntülenen akış Python özeldir ve Django, CPython ve diğer temel bileşenleri içerir. Ayrıca, aşağıda gösterildiği gibi kendi akış seçebilirsiniz. Microsoft Azure yayımlama sırasında Kurulum görev tüm başvurulan ürünleri yükler.

![Webpı başvuruları](media/projects-webPI-components.png)