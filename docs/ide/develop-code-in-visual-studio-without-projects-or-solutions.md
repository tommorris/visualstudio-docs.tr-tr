---
title: Visual Studio projeleri veya çözümler olmadan kod geliştirme
ms.date: 02/21/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- open folder [Visual Studio]
- anycode [Visual Studio]
- projects and solutions, develop code without
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a784015c57aee41488b1d8988166bea1cf7ca874
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117127"
---
# <a name="develop-code-in-visual-studio-without-projects-or-solutions"></a>Visual Studio projeleri veya çözümler olmadan kod geliştirme

Visual Studio 2017 ', kod neredeyse tüm dizin tabanlı proje türünden Visual Studio'ya bir çözüm ya da proje dosyası gerek kalmadan açabilirsiniz. Bu,, örneğin, github'da depoyu kopyalama, doğrudan Visual Studio'ya açın ve bir çözüm ya da proje oluşturmak zorunda kalmadan geliştirmeye başlamak anlamına gelir. Gerekirse, özel derleme görevleri belirtin ve parametreler aracılığıyla basit JSON dosyaları başlatın.

Visual Studio'da kod dosyalarınızın açtıktan sonra **Çözüm Gezgini** klasördeki tüm dosyaları görüntüler. Düzenlemeye başlamak için herhangi bir dosya tıklatabilirsiniz. Arka planda, IntelliSense, gezinme ve düzenleme özellikleri etkinleştirmek için dosyaların dizinini Visual Studio başlatır. Düzenleme, oluşturma, taşıma veya dosyaları sil gibi Visual Studio değişiklikleri otomatik olarak izler ve IntelliSense dizinini sürekli olarak güncelleştirir. Kod söz dizimi renklendirme ve çoğu durumda, görünür temel IntelliSense deyim tamamlama içerir.

## <a name="open-any-code"></a>Herhangi bir kod açın

Kod aşağıdaki yollardan herhangi birini kullanarak bir Visual Studio'ya açabilirsiniz:

- Visual Studio menü çubuğunda seçin **dosya** > **açık** > **klasörü**ve kod konuma göz atın.
- Kodu içeren bir klasör (sağ tıklatma) bağlam menüsünde seçin **Visual Studio'da Aç** komutu.
- Seçin **Klasör Aç** Visual Studio bağlantıdaki **başlangıç sayfası**.
- Klavye kullanıcısıysanız basın **Ctrl**+**Shift**+**Alt**+**O** Visual içinde Studio.
- Kopyalanan bir GitHub deposuna açık koddan.

### <a name="to-open-code-from-a-cloned-github-repo"></a>Kopyalanan bir GitHub deposuna kod açmak için

Aşağıdaki örnek, bir GitHub deposuna kopyalamak ve kendi kod Visual Studio'da açın gösterilmektedir. Bu yordamı takip etmek için GitHub hesabı ve Windows için Git sisteminize yüklenmiş olmalıdır. Bkz: [yeni bir GitHub hesabı için kaydolmadan](https://help.github.com/articles/signing-up-for-a-new-github-account/) ve [Windows için Git](https://git-for-windows.github.io/) daha fazla bilgi için.

1. Github'da kopyalamak istediğiniz depoya gidin.

1. Seçin **kopyalama veya indirme** düğmesine tıklayın ve ardından **Panoya Kopyala** GitHub depo için güvenli URL'yi kopyalamak için açılır menüde düğmesi.

   ![GitHub kopya düğmesi](./media/VSIDE_Code_Clone.png)

1. Visual Studio'da, **Takım Gezgini** sekmesini açmak için **Takım Gezgini**. Sekmesini görmüyorsanız, ondan açmak **Görünüm** > **Takım Gezgini**.

1. Takım Gezgini'nde altında **yerel Git depoları** bölümünde, seçin **kopya** komut ve GitHub sayfasının URL'sini metin kutusuna yapıştırın.

   ![Proje kopyalama](./media/VSIDE_Code_Clone2.png)

1. Seçin **kopya** proje dosyalarını yerel bir Git deposuna kopyalamak için düğmesi. Depodaki boyutuna bağlı olarak, bu işlem birkaç dakika sürebilir.

1. Depoyu üzere, sisteminize içinde klonlanmış sonra **Takım Gezgini**, seçin **açık** yeni kopyalanmış depo bağlamını (sağ tıklatma) menüsünde komutu.

   ![Kopyalanan deposu](./media/VSIDE_Code_Clone3.png)

1. Seçin **klasör görünümü göster** dosyaları görüntülemek için komut **Çözüm Gezgini**.

   ![Klasör Görünümü Göster](./media/VSIDE_Code_Clone3_show.png)

   Şimdi kopyalanan depodaki dosya ve klasörleri bulun ve da görüntüleyebilir ve kod söz dizimi renklendirme ile tam Visual Studio kod düzenleyicisini ve diğer özellikleri arayabilirsiniz.

|         |         |
|---------|---------|
|  ![video film kamera simgesi](../install/media/video-icon.png)|    [Bir video izlemek](https://mva.microsoft.com/en-us/training-courses/getting-started-with-visual-studio-2017-17798?l=lp3TOKD6D_6711787171) nasıl kopyalamak ve kod'i GitHub deposuna Visual Studio'da açın. |

## <a name="run-and-debug-your-code"></a>Çalıştırın ve kodunuzu hata ayıklama

Visual Studio kodunuzda proje ya da çözüm olmadan ayıklayabilirsiniz! Bazı diller hata ayıklamak için geçerli bir belirtmeniz gerekebilir *başlatma dosyasını* komut dosyası, yürütülebilir dosya veya proje gibi codebase içinde. Yanında aşağı açılan liste kutusu **Başlat** araç çubuğunda tüm Visual Studio, özellikle belirttiğiniz öğeleri yanı sıra algıladığı Başlangıç öğeleri listeler. Kodunuzdaki hataları ayıklamanıza visual Studio bu kodu önce çalıştırılır.

Visual Studio'da çalıştırmak için kodunuzu yapılandırma olmasından ne tür bir kod ve derleme araçları nelerdir bağlı olarak farklılık gösterir.

### <a name="codebases-that-use-msbuild"></a>MSBuild kullanan olarak kullanılabilecek kod temeli

MSBuild tabanlı olarak kullanılabilecek kod temeli görünür birden çok derleme yapılandırmaları olabilir **Başlat** düğmenin aşağı açılan liste. Başlangıç öğesi olarak kullanın ve ardından istediğiniz dosyayı seçin **Başlat** hata ayıklama başlamak için düğmesini.

> [!NOTE]
> C# ve Visual Basic olarak kullanılabilecek kod temeli için bulunmalıdır **.NET masaüstü geliştirme** yüklü iş yükü. C++ olarak kullanılabilecek kod temeli için bulunmalıdır **C++ ile masaüstü geliştirme** yüklü iş yükü.

### <a name="codebases-that-use-custom-build-tools"></a>Özel derleme araçlarını kullanın olarak kullanılabilecek kod temeli

Codebase kullanılan özel derleme araçları sonra Visual Studio kullanarak kod oluşturma söylemelisiniz *derleme görevleri* içinde tanımlanan bir *.json* dosya. Daha fazla bilgi için bkz: [yapı özelleştirebilir ve hata ayıklama görevleri](../ide/customize-build-and-debug-tasks-in-visual-studio.md).

### <a name="codebases-that-contain-python-or-javascript-code"></a>Olarak kullanılabilecek kod temeli Python veya JavaScript kodu içerir

Kod temeliniz Python veya JavaScript kodu içeriyorsa, tüm yapılandırmak zorunda kalmamaları *.json* dosyaları, ancak karşılık gelen iş yükü yüklemek sahip. Başlangıç betiği de yapılandırmanız gerekir:

1. Yükleme [Node.js geliştirme](https://visualstudio.microsoft.com/vs/node-js/) veya [Python geliştirme](https://visualstudio.microsoft.com/vs/python/) seçerek iş yükü **Araçları** > **alma araçları ve özelliklerinin**, veya Visual Studio kapatma ve Visual Studio yükleyicisi çalışır.

   ![Node.js ve Python geliştirme iş yükleri](media/python_nodejs_workloads.png)

1. İçinde **Çözüm Gezgini**, JavaScript veya Python dosyasını sağ tıklatın veya bağlam menüsünde seçin **başlangıç öğesi olarak ayarla** komutu.

1. Seçin **Başlat** hata ayıklama başlamak için düğmesini.

### <a name="codebases-that-contain-c-code"></a>Olarak kullanılabilecek kod temeli C++ kodu içerir

Visual Studio'da C++ kodu çözümleri veya projeleri olmadan açma hakkında daha fazla bilgi için bkz: [C++ Klasör Aç projelerde](/cpp/ide/non-msbuild-projects).

### <a name="codebases-that-contain-a-visual-studio-project"></a>Olarak kullanılabilecek kod temeli, içeren bir Visual Studio projesi

Kod klasörünüze Visual Studio projesi içeriyorsa, proje başlangıç öğesi olarak belirleyebilirsiniz.

![Başlangıç öğesi olarak ayarla proje](media/customize-set-project-as-startup-item.png)

**Başlat** projenin başlangıç öğesi olduğunu yansıtacak şekilde düğmenin metin değişir.

![Başlat düğmesine proje](media/customize-start-button-project.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Yapı özelleştirme ve hata ayıklama görevleri](../ide/customize-build-and-debug-tasks-in-visual-studio.md)
- [C++ için açık klasörü projeler](/cpp/ide/non-msbuild-projects)
- [C++'ta CMake projeleri](/cpp/ide/cmake-tools-for-visual-cpp)
- [Kod ve Metin Düzenleyici'de kod yazma](../ide/writing-code-in-the-code-and-text-editor.md)