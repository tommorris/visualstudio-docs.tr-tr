---
title: "Sorun giderme ve bilinen sorunlar (Unity için Visual Studio Araçları) | Microsoft Docs"
ms.custom: 
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-unity-tools
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f5db192-8d78-4627-bd07-dbbc803ac554
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: 95d1724561886e1bcfa9a870bdf3bdadb787f9e8
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2018
---
# <a name="troubleshooting-and-known-issues-visual-studio-tools-for-unity"></a>Sorun Giderme ve Bilinen Sorunlar (Unity için Visual Studio Araçları)
Bu bölümde, bilinen sorunların açıklamaları Unity için Visual Studio Araçları ile sık karşılaşılan sorunlara çözümler bulmak ve hata bildirimi tarafından Unity için Visual Studio Araçları geliştirmek nasıl yardımcı olabileceğini öğrenin.

## <a name="troubleshooting"></a>Sorun giderme
Unity için Visual Studio Araçları ile ilgili bazı yaygın sorunları gidermek için aşağıdaki bölümlere bakın.

### <a name="visual-studio-crashes"></a>Visual Studio kilitleniyor
Bu, Visual Studio MEF önbelleği bozuk nedeniyle olabilir.

MEF önbelleği sıfırlamak için şu klasörü kaldırmalısınız (Lütfen Visual Studio bunu yapmadan önce Kapat):

```batch
%localappdata%\Microsoft\VisualStudio\<version>\ComponentModelCache
```

Bu sorunu çözer. Hala sorun yaşıyorsanız, geliştirici komut istemini yönetici olarak Visual Studio için çalıştırın ve aşağıdaki komutu kullanın:

```batch
 devenv /setup
```

### <a name="issues-with-vs2015-and-intellisense-or-code-coloration"></a>VS2015 ve IntelliSense veya kod coloration sorunları.
3 güncelleştirmek için Visual Studio 2015 yükseltme çalışmanız gerekir.

### <a name="visual-studio-hangs"></a>Visual Studio kilitleniyor
Ayrıştırma FMOD, HAZNEYİ (Evrensel Media Player) ZFBrowser veya katıştırılmış tarayıcı gibi birkaç Unity eklentileri yerel iş parçacığı kullanıyor. İşletim sistemi engelleme çağrı yapar çalışma zamanı için bir yerel iş parçacığı ekleme yukarı bir eklenti sona erdiğinde bir sorundur. Bu Unity hata ayıklayıcısı (veya etki alanı yeniden yükle) o iş parçacığı kesme ve askıda anlamına gelir.

FMOD, bir geçici çözüm yoktur, FMOD_STUDIO_INIT_SYNCHRONOUS_UPDATE başlatma geçirebilirsiniz [bayrağı](https://www.fmod.org/docs/content/generated/FMOD_STUDIO_INITFLAGS.html) zaman uyumsuz işleme devre dışı bırakabilir ve tüm işlemler ana iş parçacığı üzerinde gerçekleştirin.

### <a name="incompatible-project-in-visual-studio"></a>Visual Studio'da uyumsuz projesi
İlk olarak, Visual Studio Dış betik düzenleyicinizde Unity (Tercihler/düzenleme/dış araçları) olarak ayarlanmış olduğundan emin olun. Visual Studio eklentisi Unity yüklendiğini denetleyin (Yardımı/hakkında Unity için Microsoft Visual Studio Araçları altındaki etkin gibi bir ileti görüntüler gerekir). Ardından uzantısı düzgün şekilde Visual Studio'da (Yardımı/hakkında) yüklenip yüklenmediğini denetleyin.

### <a name="assembly-reference-issues"></a>Derleme başvurusu sorunları
Projeniz reference-wise karmaşık ise veya daha iyi oluşturma adımını denetlemek istiyorsanız, kullanabileceğiniz bizim [API](../cross-platform/customize-project-files-created-by-vstu.md) oluşturulan proje ya da çözüm içeriği düzenleme için. Aynı zamanda [yanıt dosyaları](https://docs.unity3d.com/Manual/PlatformDependentCompilation.html) , Unity proje ve biz işlenecekleri.

### <a name="breakpoints-with-a-warning"></a>Bir uyarı ile kesme noktaları
Visual Studio belirli bir kesme noktası için bir kaynak konumu bulamıyor ise isabetini bir uyarı görürsünüz. Kullanmakta olduğunuz davranışa düzgün yüklenmiş/geçerli Unity Sahne kullanılan olup olmadığını denetleyin.

### <a name="breakpoints-not-hit"></a>Kesme noktası isabet değil
 Kullanmakta olduğunuz davranışa düzgün yüklenmiş/geçerli Unity Sahne kullanılan olup olmadığını denetleyin. Visual Studio ve Unity çıkın sonra oluşturulan tüm dosyaları (*.csproj, *.sln) ve tüm kitaplık klasörünü silin.

### <a name="unable-to-attach"></a>İliştirilemiyor
-   Geçici olarak virüsten koruma devre dışı bırakmak veya VS ve Unity için dışlama kuralları oluşturmak deneyin.
-   Geçici olarak güvenlik duvarınızı devre dışı veya TCP/UDP ağ VS Unity arasındaki izin vermek için kurallar oluşturmak deneyin.
-   Programları takım Görüntüleyicisi gibi işlem algılamasıyla engel oluyor tanımlanan; belki de bir şey değişirse görmek için geçici olarak ek yazılımları durdurmayı deneyebilirsiniz.
-   VSTU yalnızca "Unity.exe" işlemlerini izleme gibi ana Unity yürütülebilir adlandırmayın.

### <a name="unable-to-debug-android-players"></a>Android oynatıcıları hata ayıklamak için
Çok noktaya yayın kullanıyoruz (Unity tarafından kullanılan varsayılan bir mekanizma olan) player algılamasını, ancak bundan sonra normal bir TCP bağlantısı hata ayıklayıcısını kullanırız. Android cihazlar için ana sorunu algılama aşamasıdır.

USB hata ayıklama için süper hızlı ancak Unity player bulma mekanizmasından ile uyumlu değil.
WiFi gecikme nedeniyle USB karşılaştırıldığında Süper yavaş ancak daha güçlüdür. Bazı yönlendiriciler veya (Nexus serisi bu bilinen) cihazları için uygun çok noktaya yayın desteği olmaması gördük.

Aşağıdaki çalışabilir bağlı cihazına (yukarı player ve hata ayıklama bağlantı noktası, her zaman formun 56xxx görebilmeniz için çalıştıran) açılan bağlantı noktaları görmek için USB kullanarak:

```shell
adb shell netstat
```

Yerel bilgisayar için bağlantı noktası ilet:

```shell
adb forward tcp:56xxx tcp:56xxx
```

Ardından, VSTU iletilen bağlantı noktası 127.0.0.1:56xxx kullanarak bağlanın.

### <a name="migrating-from-unityvs-to-visual-studio-tools-for-unity"></a>Unity için Visual Studio Araçları UnityVS geçirme
 Unity için Visual Studio Araçları için UnityVS geçiş, Unity projelerinizi yeni Visual Studio çözümleri oluşturmanız gerekir.

##### <a name="to-migrate-your-unity-project-from-unityvs-18-to-visual-studio-tools-for-unity-19"></a>Unity projenizi UnityVS 1.8 Visual Studio Araçları için Unity 1.9 geçirmek için

1.  Eski çözüm ve proje dosyalarını Unity projenizden silin. Visual Studio .sln Unity proje kök dizininde bulun ve. * proj dosyaları ve tümünü silin.

2.  Unity paketini için Visual Studio Araçları Unity projenize alın. VSTU paketini içeri aktarma hakkında daha fazla bilgi için Unity için Visual Studio Araçları yapılandırma bakın [Başlarken](../cross-platform/getting-started-with-visual-studio-tools-for-unity.md) sayfası.

3.  Yeni çözüm ve proje dosyalarını oluşturur. Bunları şimdi, Unity Düzenleyicisi'nde, ana menüdeki oluşturmak istiyorsanız seçin **Visual Studio Araçları**, **proje dosyalarını oluşturmak**. Aksi takdirde istiyorsanız bu adımı atlayabilirsiniz; Unity için Visual Studio Araçları oluşturacağını yeni dosyalar otomatik olarak seçtiğinizde **Visual Studio Araçları**, **Visual Studio'da Aç**.

### <a name="on-windows-visual-studio-asks-to-download-the-unity-target-framework"></a>Windows, Unity hedef Framework'ü indirmek Visual Studio ister.
 Unity için Visual Studio Araçları varsayılan olarak 10 veya Windows 8 yüklü değilse .net framework 3.5, gerektirir. Bu sorunu gidermek için indirmek ve .net framework 3.5 yüklemek için yönergeleri izleyin.

## <a name="known-issues"></a>Bilinen Sorunlar
 Bilinen sorunlar vardır hata ayıklayıcı Unity'nın eski sürümü C# derleyici ile nasıl etkileşim gelen neden Visual Studio Araçları Unity için. Bu sorunları gidermeye yardımcı olmak için çalışıyoruz ancak bu arada aşağıdaki sorunlarla karşılaşabilirsiniz:

-   Hata ayıklama sırasında Unity bazen kilitleniyor.

-   Hata ayıklama sırasında Unity bazen donuyor.

-   İçine ve dışına yöntemleri bazen atlama özellikle yineleyiciler veya switch deyimleri içinde yanlış bir şekilde davranır.

## <a name="reporting-errors"></a>Hata Raporlama
 Lütfen kilitlenen, donuyor veya diğer hatalarla karşılaşırsanız, hata raporlarını göndererek Unity için Visual Studio Araçları kalitesini iyileştirmemize yardımcı olun. Bu bize araştırın ve Unity için Visual Studio Araçları sorunları gidermeye yardımcı olur. Teşekkür ederiz!

### <a name="how-to-report-an-error-when-visual-studio-freezes"></a>Visual Studio donuyor olduğunda bir hata bildirme
 Visual Studio bazen Unity için Visual Studio Araçları ile hata ayıklama sırasında donuyor rapor vardır, ancak Biz bu sorunu anlamak için daha fazla veri gerekir. Bize aşağıdaki adımları izleyerek araştırmanıza yardımcı olabilir.

##### <a name="to-report-that-visual-studio-freezes-while-debugging-with-visual-studio-tools-for-unity"></a>Unity için Visual Studio Araçları ile hata ayıklama sırasında Visual Studio donuyor raporu

*On Windows:*

1.  Visual Studio yeni bir örneğini açın.

2.  Ekleme işlemi iletişim için açın. Visual Studio, yeni bir örneğini ana menüdeki seçin **hata ayıklama**, **ekleme işlemi için**.

3.  Hata ayıklayıcısını Visual Studio dondurulmuş örneğine ekleyin. İçinde **ekleme işlemi için** iletişim kutusunda, Visual Studio'dan dondurulmuş örneğini seçin **kullanılabilir işlemler** tablo sonra seçin **Attach** düğmesi.

4.  Hata ayıklayıcı duraklatın. Visual Studio, yeni bir örneğini ana menüdeki seçin **hata ayıklama**, **bölün tüm**, veya yalnızca basın **Ctrl + Alt + Break**.

5.  İş parçacığı dökümü oluşturun. Komut penceresinde komut enter tuşuna basarak aşağıdaki **Enter**:

    ```powershell
    Debug.ListCallStack /AllThreads /ShowExternalCode
    ```

    Yapmanız gerekebilecek **komutu** pencere görünür ilk. Visual Studio'da ana menüde seçin **Görünüm**, **diğer pencereler**, **komut penceresi**.

*On Mac:*

1. Bir terminal açın ve Mac için PID, Visual Studio alın:

    ```shell
    ps aux | grep "[V]isual Studio.app"
    ```

1. Lldb hata ayıklayıcı başlatın:

    ```shell
    lldb
    ```

1. PID kullanarak Mac örneği için Visual Studio ekleyin:

    ```shell
    process attach --pid THE_PID_OF_THE_VSFM_PROCESS
    ```

1. Tüm iş parçacıklarının stacktrace Al:

    ```shell
    bt all
    ```

Son olarak, iş parçacığı-dökümü Gönder [ vstusp@microsoft.com ](mailto:vstusp@microsoft.com), ne zaman yaptığınız işe açıklaması yanı sıra Visual Studio dondurulmuş hale geldi.
