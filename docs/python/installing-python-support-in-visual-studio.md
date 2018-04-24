---
title: Python desteğini yükleme
description: İçin Visual Studio (PTVS) Visual Studio 2017, 2015, 2013, 2012 ve 2010 içinde Python Araçları'nı yükleme konusunda ayrıntılı yönergeler seçenekleri ve yükleme konumlarını dahil olmak üzere.
ms.date: 02/15/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: a998a2a62915d1ce998e30202f4b4fd0838975a3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="installing-python-support-in-visual-studio-on-windows"></a>Windows Visual Studio'da Python desteğini yükleme

Visual Studio (Visual Studio ya da PTVS için Python araçları olarak da bilinir) için Python desteği yüklemek için Visual Studio sürümünüzle eşleşen bölümünde yer alan yönergeleri izleyin:

- [Visual Studio 2017](#visual-studio-2017)
- [Visual Studio 2015](#visual-studio-2015)
- [Visual Studio 2013 ve önceki sürümleri](#visual-studio-2013-and-earlier)

Ve daha önceki Visual Studio 2015 için ayrı ayrı etmeniz [bir Python yorumlayıcısı yüklemek](installing-python-interpreters.md) tercih ettiğiniz (Python 3.5 ve daha önce; 3.6 desteklenmiyor ve ileti "desteklenmeyen Python sürümü 3.6" oluşturur). Aynı sayfada Ayrıca varolan bir Python yorumlayıcısı için Visual Studio 2017 eklemek için yönergeler içerir.

Hızlı yükleme adımlarını izleyerek sonra Python desteği test etmek için Alt tuşuna basarak Python etkileşimli penceresini açın-t ve girerek `2+2`. Çıktısını görmüyorsanız, `4`, adımlarınızı yeniden denetleyin.

> [!Tip]
> Python iş yükü şablonları bulmak, şablon seçenekleri giriş ve projeler ve dosyaları oluşturmak için bir grafik kullanıcı arabirimi sağlar yardımcı Cookiecutter uzantısını da içerir. Ayrıntılar için bkz [kullanarak Cookiecutter](using-python-cookiecutter-templates.md).

> [!Note]
> Python desteği Mac için Visual Studio şu anda kullanılabilir değil, ancak Mac ve Linux Visual Studio Code ile kullanılabilir. Bkz: [sorular ve yanıtlar](overview-of-python-tools-for-visual-studio.md#questions-and-answers).

## <a name="visual-studio-2017"></a>Visual Studio 2017

1. Karşıdan yükle ve en son Visual Studio 2017 yükleyiciyi çalıştırın. Visual Studio'nun zaten yüklü varsa, Visual Studio yükleyicisi, belirleyin **Değiştir** seçeneği (bkz [değiştirmek Visual Studio](../install/modify-visual-studio.md)) ve 2. adıma geçin.

    > [!div class="nextstepaction"]
    > <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_install">Visual Studio 2017 Community yükle</a>

    >[!Tip]
    > Community edition her bir geliştirici, sınıf öğrenme, akademik araştırma ve açık kaynak geliştirme içindir. Diğer kullanımlar için yükleme <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_install">Visual Studio 2017 Professional</a> veya <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&rid=34347&utm_source=docs&utm_medium=clickbutton&utm_campaign=python_install">Visual Studio 2017 Enterprise</a>.

1. Yükleyici belirli geliştirme alanlar için ilgili seçenekleri gruplarıdır iş yükleri listesini gösterir. Python için seçin **Python geliştirme** iş yükü.

    ![Visual Studio yükleyicisi Python geliştirme iş yükü](media/installation-python-workload.png)

    İsteğe bağlı: veri bilimi ile çalışıyorsanız, de dikkate **veri bilimi ve analitik uygulamaları** iş yükü. Bu iş yükü, Python ve bunun yanı sıra R ve F # dilleri için destek içerir. Daha fazla bilgi için bkz: [veri bilimi ve analitik uygulamaları iş yükü](../rtvs/data-science-and-analytical-applications-workload.md).

    > [!Note]
    > Python ve veri bilimi iş yükleri ve sonrasında yalnızca Visual Studio 2017 sürüm 15.2 ile kullanılabilir.

1. Yükleyici sağ tarafında isterseniz ek seçenekleri seçin. Varsayılan seçenekleri kabul etmek için bu adımı atlayın.

    ![Visual Studio yükleyicisinde Python geliştirme seçenekleri](media/installation-python-options.png)

    | Seçenek | Açıklama |
    | --- | --- |
    | Python dağıtımları | Herhangi bir bileşimini çalışmak için planlama Python 2, Python 3, Anaconda2 ve Anaconda3 dağıtımları 32-bit ve 64-bit çeşitlemelerini seçin. Her dağıtım 's Yorumlayıcı, çalışma zamanı ve kitaplıklarını içerir. Anaconda, özellikle çok çeşitli önceden yüklenen paketler içeren bir açık veri bilimi platformudur. (Visual Studio yükleyicisi eklemek veya kaldırmak dağıtımları için herhangi bir zamanda döndürebilir.)  **Not**: Visual Studio yükleyicisi dışında bir dağıtım yüklediyseniz, burada eşdeğer seçeneği denetlemek için gerek yoktur. Visual Studio varolan Python yüklemeleri otomatik olarak algılar. Bkz: [Python ortamları](managing-python-environments-in-visual-studio.md). |
    | Cookiecutter şablon desteği | Şablonları bulmak, şablon seçenekleri giriş ve projeler ve dosyaları oluşturmak için Cookiecutter grafik kullanıcı arabirimini yükler. Bkz: [Cookiecutter uzantısını kullanarak](using-python-cookiecutter-templates.md). |
    | Python web desteği | HTML, CSS ve JavaScript desteği, Bottle, Flask ve Django çerçeveleri kullanarak projeleri için şablonlar yanı sıra düzenleme dahil olmak üzere web geliştirme araçları'nı yükler. Bkz: [Python web projesi şablonları](python-web-application-project-templates.md). |
    | Python IOT desteği | Python kullanarak Windows IOT Core geliştirme destekler. |
    | Python yerel geliştirme araçları | C++ derleyicisi ve Python için yerel uzantılar geliştirmek üzere diğer gerekli bileşenleri yükler. Bkz: [Python için C++ uzantısı oluşturma](working-with-c-cpp-python-in-visual-studio.md). Ayrıca yükleme **C++ ile masaüstü geliştirme** tam C++ destek için iş yükü. |
    | Azure bulut Hizmetleri Çekirdek araçları | Geliştirici Python Azure bulut Hizmetleri için ek destek sağlar. Bkz: [Azure bulut hizmeti projeleri](python-azure-cloud-service-project-template.md). |

1. Yükleme sonrasında, yükleyici değiştirmek, başlatma, onarın veya Visual Studio'yu kaldırmak için seçenekler sağlar. **Değiştir** düğmesi değişiklikler **güncelleştirme** güncelleştirmeler için kullanılabilir güncelleştirmeler olduğunda Visual Studio bileşenleri yüklü olduğunda. (Değiştir seçeneği, ardından aşağı açılan menüsünde kullanılabilir.) Visual Studio ve Windows Başlat menüsünden yükleyici "Visual Studio" arayarak de başlatabilirsiniz.

    ![Başlatma, değiştirme, değiştirme veya Visual Studio Yükleyicisi'nden kaldırılıyor](media/installation-vs-launch.png)

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | [(Microsoft Virtual Academy) bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Installing-Visual-Studio-Python-Support-go1id3LWE_1705918567) Visual Studio'da Python desteği yükleme.|

### <a name="troubleshooting"></a>Sorun giderme

Yüklerken veya Visual Studio'da Python çalıştırırken sorunlarla karşılaşırsanız, aşağıdakileri deneyin:

- Aynı hata Python CLI kullanarak diğer bir deyişle, çalışan oluşup oluşmadığını belirleyin `python.exe` bir komut isteminden.
- Kullanım [onarım seçeneği Visual Studio yükleyicisinde](../install/repair-visual-studio.md).
- Onarım veya Python aracılığıyla yeniden **ayarlar > uygulamalar ve Özellikler** Windows.

**Örnek hata**: etkileşimli işlem başlatılamadı: System.ComponentModel.Win32Exception (0x80004005): Microsoft.PythonTools.Repl.PythonInteractiveEvaluator.d__43.MoveNext() sırasında bilinmeyen hata (0xc0000135).

## <a name="visual-studio-2015"></a>Visual Studio 2015

1. Visual Studio yükleyiciyi çalıştırmak **Denetim Masası > Programlar ve Özellikler**, seçme **Microsoft Visual Studio 2015** ve ardından **değişiklik**.

1. Yükleyicisi'nde seçin **Değiştir**.

1. Seçin **programlama dilleri > Visual Studio için Python Araçları** ve ardından **sonraki**:

    ![Visual Studio 2015 yükleyici PTVS seçeneği](media/installation-vs2015.png)

1. Visual Studio Kurulumu tamamlandıktan sonra [tercih ettiğiniz bir Python yorumlayıcısı yüklemek](installing-python-interpreters.md). Yüklü yorumlayıcı ve Visual Studio zaten varsa değil otomatik olarak algılamak için bkz: [el ile varolan bir ortama tanımlayan](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).

## <a name="visual-studio-2013-and-earlier"></a>Visual Studio 2013 ve önceki sürümleri

1. Visual Studio için Python Araçları'nün uygun sürümüne Visual Studio sürümünüze yükleyin:

    - Visual Studio 2013: [PTVS 2.2 Visual Studio 2013 için](https://github.com/Microsoft/PTVS/releases/v2.2). **Dosya > Yeni proje** Visual Studio 2013'te iletişim size bir kısayol bu işlem için.
    - Visual Studio 2012: [PTVS 2.1 Visual Studio 2012 için](https://pytools.codeplex.com/downloads/get/920478)
    - Visual Studio 2010: [PTVS 2.1 Visual Studio 2010 için](https://pytools.codeplex.com/downloads/get/920479)

1. [Tercih ettiğiniz bir Python yorumlayıcısı yüklemek](installing-python-interpreters.md). Yüklü yorumlayıcı ve Visual Studio zaten varsa değil otomatik olarak algılamak için bkz: [el ile varolan bir ortama tanımlayan](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).

## <a name="install-locations"></a>Konumları yükleyin

Varsayılan olarak, Python desteği, bir bilgisayardaki tüm kullanıcılar için yüklenir.

Visual Studio 2017 Python iş yükü yüklü `%ProgramFiles(x86)%\Microsoft Visual Studio\2017\<VS_edition>Common7\IDE\Extensions\Microsoft\Python` nerede &lt;VS_edition&gt; Community, Professional ya da kuruluş.

Visual Studio 2015 ve önceki sürümlerinde, yükleme yolu aşağıdaki gibidir:

- 32-bit:
  - Yol: `%Program Files(x86)%\Microsoft Visual Studio <VS_ver>\Common7\IDE\Extensions\Microsoft\Python Tools for Visual Studio\<PTVS_ver>`
  - Yolu kayıt defteri konumu: `HKEY_LOCAL_MACHINE\Software\Microsoft\PythonTools\<VS_ver>\InstallDir`
- 64-bit:
  - Yol: `%Program Files%\Microsoft Visual Studio <VS_ver>\Common7\IDE\Extensions\Microsoft\Python Tools for Visual Studio\<PTVS_ver>`
  - Yolu kayıt defteri konumu: `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\PythonTools\<VS_ver>\InstallDir`

burada:

- &lt;VS_ver&gt; değil:
  - Visual Studio 2015 için 14.0
  - Visual Studio 2013 için 12.0
  - Visual Studio 2012 için 11.0
  - Visual Studio 2010 için 10.0
- &lt;PTVS_ver&gt; 2.2, 2.1, 2.0, 1.5, 1.1 ve 1.0 gibi bir sürüm numarası.

### <a name="user-specific-installations-15-and-earlier"></a>Kullanıcıya özgü yüklemeleri (1.5 ve önceki sürümler)

Python araçları Visual Studio 1.5 ve önceki yükleme yalnızca geçerli kullanıcı için izin verilen, bu durumda yükleme yolu `%LocalAppData%\Microsoft\VisualStudio\<VS_ver>\Extensions\Microsoft\Python Tools for Visual Studio\<PTVS_ver>` nerede &lt;VS_ver&gt; ve &lt;PTVS_ver&gt; aynı açıklandığı gibi Yukarıdaki.

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
