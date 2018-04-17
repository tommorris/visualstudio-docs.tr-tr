---
title: Profil oluşturma HPC (yüksek performanslı hesaplama) kümelerinde | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.hpc.wizard.exeoptions
- vs.performance.hpc.wizard.summary
- vs.performance.hpc.wizard.startoptions
- vs.performance.hpc.wizard.intro
- vs.performance.hpc.property.basic
- vs.performance.hpc.wizard.application
- vs.performance.hpc.wizard.clusteroptions
- vs.performance.hpc.property.advanced
helpviewer_keywords:
- profililng tools,HPC
- HPC profiling
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba816c7d69d148aab498076d29cbaaf33a79026b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="profiling-on-hpc-high-performance-computing-clusters"></a>HPC (Yüksek Performanslı Hesaplama) Kümelerinde Profil Oluşturma

Profil oluşturma Visual Studio Araçları örnekleme yöntemini kullanarak işlem Microsoft Windows HPC küme düğümlerinde profil. HPC hakkında daha fazla bilgi için bkz: [Windows HPC](http://go.microsoft.com/fwlink/?LinkId=165393) Microsoft Web sitesinde.

## <a name="prerequisites"></a>Önkoşullar

Bir HPC işlem düğümünde profil için aşağıdakileri yapmanız gerekir:

- Visual Studio ile aynı bilgisayarda Microsoft HPC Pack 2008 yükleyin. Bilgisayar HPC kümesinin parçası olmak zorunda değildir. HPC paketini yükleyebilirsiniz [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=177414).

- Yükleme [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)] ve HPC profil oluşturma araçları tek başına bir sürümünü işlem düğümü. Program için yükleme [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] ve tek başına profil oluşturucu Visual Studio yükleme medyasında bulunur. **Not** yükledikten sonra işlem yeniden başlatmanız gerekir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] ve profil oluşturma araçları yüklemeden önce.

 Yüklemek için [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)] ve tek başına profil oluşturma araçları etkin bir HPC işlem düğümü ve küme makinede etkinleştir profil oluşturma, şu adımları izleyin:

1. HPC pack yüklü komut istemi penceresi açın.

2. Ayrı komut istemleri aşağıdaki komutları yazın:

    1. `clusrun /all /scheduler:` *% HeadNode % FxPath %* `/q /norestart`

    2. `clusrun /all /scheduler:` *% HeadNode %* `shutdown /r /t 0 /d u:4:2 /c "Microsoft .NET Framework install required restart"`

    3. `clusrun /all /scheduler:` *% HeadNode % ProfilerPath %* `/q /norestart`

|||
|-|-|
|*%HeadNode%*|Küme baş düğüm adı.|
|*%FxPath%*|Yolu [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)] yükleyici. Visual Studio yükleme medyasında yoludur: WCU\dotNetFramework\dotNetFx40_Full_x86_x64.exe|
|*%ProfilerPath%*|Profil oluşturma araçları yükleyici tek başına sürümü yolu. Visual Studio yükleme medyasında yoludur: tek başına Profiler\x64\vs_profiler.exe|

## <a name="profiling-on-an-hpc-compute-node"></a>Bir HPC işlem düğümünde profil oluşturma

Profil oluşturma oturumu HPC küme ve hedef bilgileri belirtmek için HPC performans Sihirbazı'nı kullanarak yapılandırın. Performans oturumu özellik sayfalarında ek seçenekler belirleyebilirsiniz. Profil oluşturma araçları otomatik olarak gerekli hedef ikili dosyaları dağıtma ve profil oluşturucu ve HPC uygulama başlatma.

1. Üzerinde **Çözümle** menüsünde tıklatın **HPC performans Sihirbazı'nı başlatma**. Komut kullanılabilir durumda değilse, yukarıda listelenen önkoşullara sahip olduğunuzdan emin olun.

2. Tıklatın **sonraki** Sihirbazı'nın ilk sayfasında.

3. Sihirbazın ikinci sayfasında profil oluşturmayı istediğiniz uygulamayı seçin.

    - Şu anda açık olan bir projeyi profilini [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]seçin **bir veya daha fazla kullanılabilir projeler** seçeneğini ve ardından listeden proje adı.

    - Kullanımda olmayan bir ikili profil için bir açık projeye seçin **bir yürütülebilir dosya (. EXE dosyası)** seçeneği.

4. **İleri**'ye tıklayın.

5. Sihirbazın üçüncü sayfasında:

    - Açık projesinde olmayan yürütülebilir profil, ikili dosya yolunu belirtin **yürütülebilir dosyanın tam yolunu nedir**.

    - Açık projesinde olmayan yürütülebilir profil, işlemde geçirilecek komut satırı bağımsız değişkenleri belirtebilirsiniz **komut satırı bağımsız değişkenleri**.

    - İçinde **uzak çalışma dizini**, işlem düğümlerini tek tek işlem örneklerinde tarafından kullanılan klasörün yolunu belirtin.

    - İçinde **dağıtım konumu**, HPC server aşama görüntülerini dağıtım için kullanacağı dizinin yolunu belirtin.

6. **İleri**'ye tıklayın.

7. Sihirbazının dördüncü sayfasında:

    - İçinde **baş düğüm** listesinde, çalıştırmak profil HPC baş düğümü görevi gören bilgisayar'ı tıklatın. Baş düğüm, bir küme gerektirmeden yerel makinedeki profili sağlar "localhost" olabilir.

    - İçinde **işlemlerin sayısı** listesinde, uygulamayı çalıştırmak için örnek sayısı tıklayın.

    - Gelen **seçenekleri profil** listesinde, profil hedef seçin.

         Küme içindeki belirli bir işlemin profil için seçin **derece profilinde** seçeneğini ve sonra işlem sırasını aşağı açılan listeden seçin.

         İşlem ya da belirli bir HPC küme düğümünde çalışan işlemde profil için seçin **profil düğümde** seçeneğini ve ardından düğümü aşağı açılan listeden seçin.

8. **İleri**'ye tıklayın.

9. Beşinci sihirbaz sayfasında, profil oluşturucu ve profil oluşturma işlemi hemen başlatmak için ya da daha sonra performans Gezgini'ni kullanarak profil oluşturmayı başlatmak için seçebilirsiniz.

    - Seçin **Sihirbaz tamamlandıktan sonra profil oluşturmayı Başlat** hemen başla veya el ile profil oluşturmayı başlatmak için bu onay kutusunu temizleyin.

10. **Son**'a tıklayın.

## <a name="setting-hpc-profiling-properties-by-using-performance-session-property-pages"></a>Performans oturumu özellik sayfalarını kullanarak HPC profil özelliklerini ayarlama

HPC profili oluşturma Sihirbazı'nı performans oturum özellikleri sayfasının HPC başlatma özellikleri sayfasında üzerinde ayarladığınız performans oturum özellikleri değiştirebilirsiniz. HPC Gelişmiş Özellikler sayfasındaki ek seçenekleri ayarlayın.

### <a name="to-open-the-performance-session-property-pages"></a>Performans oturumu özellik sayfalarını açmak için

1. Gerekirse, performans oturumu (.psess) dosyası performans Explorer'da açın. Üzerinde **dosya** menüsünde tıklatın **açık** ve dosyasını bulun.

2. Performans Gezgini performans oturumu adına sağ tıklayın ve ardından **özellikleri**.

3. Özellik sayfaları iletişim kutusunda, aşağıdaki yöntemlerden birini kullanın:

    - Tıklatın **genel** ve ardından **HPC kümesi üzerinde toplama** profil oluşturma HPC kapatma veya HPC profili oluşturma devre dışı bırakmak için onay kutusunu temizleyin.

    - Tıklatın **HPC başlatma özellikleri** HPC uygulamayı başlatmak özelliklerini değiştirmek için.

    - Tıklatın **HPC Gelişmiş Özellikler** ek seçenekleri ayarlamak için

### <a name="hpc-launch-properties"></a>HPC başlatma özellikleri

|Özellik|Açıklama|
|--------------|-----------------|
|**Baş düğüm**|Profil oluşturma Çalıştır HPC baş düğüm olarak davranan bilgisayarı belirtir.|
|**İşlem sayısı**|Profili uygulamayı çalıştırmak için uygulamanın örneklerinin sayısını belirtir.|
|**RANK üzerinde profil**|Küme içindeki belirli bir işlemin profil için seçin **derece profilinde** seçeneğini ve sonra işlem sırasını aşağı açılan listeden seçin.|
|**Düğümde profil**|İşlem ya da belirli bir HPC küme düğümünde çalışan işlemde profil için seçin **profil düğümde** seçeneğini ve ardından düğümü aşağı açılan listeden seçin.|
|**Uzaktan çalışma dizini**|İşlem düğümlerini tek tek işlem örneklerinde tarafından kullanılan klasörün yolunu belirtir.|
|**Dağıtım konumu**|HPC server aşama görüntülerini dağıtım için kullanacağı dizinin yolunu belirtir.|

### <a name="advanced-properties"></a>Gelişmiş Özellikler

|Özellik|Açıklama|
|--------------|-----------------|
|**Proje adı**|Geçerli adını [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] proje ya da çözüm.|
|**Profil Oluşturucu durdurulduğunda temizleme**|Doğru olduğunda, yürütme dizinine dağıtılan ikili dosyaları kaldırır. Bu adımda, dosyalar ve dizinler kullanıcı program tarafından oluşturulan kaldırılmaz. Dağıtım dizini ve yürütme dizinine IDE tarafından oluşturulmuşsa IDE bunları kaldırmak çalışır ancak IDE tarafından dağıtılan dosyalarınız varsa bunu yapmaz.|
|**Dağıtmak için ek dosyalar**|İşlem düğümü üzerinde dağıtmak için ek dosyalardan noktalı virgülle ayrılmış listesini belirtir. Üç nokta düğmesini tıklatabilirsiniz (**...** ) iletişim kutusunu kullanarak birden çok dosya seçin.|
|**Mpiexec komutu**|MPI uygulama başladığında uygulama belirtir. Varsayılan değer **mpiexec.exe**|
|**Mpiexec bağımsız değişkenleri**|Mpiexec.exe komutuna geçirilecek bağımsız değişkenleri belirtir.|
|**İstenen küme düğümlerinde**|Uygulamayı çalıştırmak için kümedeki düğüm sayısını belirtir.|
|**CRT dosyaları dağıtma**|Doğru olduğunda, C/C++ çalışma zamanı kümede dağıtır.|
|**Komut dosyasını önceden profil**|Profil oluşturma oturumu başlamadan önce yerel geliştirme bilgisayarda çalıştırılacak bir komut dosyası yolu ve dosya adını belirtir.|
|**Komut dosyası değişkenleri önceden profil**|Ön profili komut dosyasına geçirilecek bağımsız değişkenleri belirtir.|
|**Komut sonrası profil**|Profil oluşturma oturumu sona erdikten sonra yerel geliştirme bilgisayarda çalıştırılacak bir komut dosyası yolu ve dosya adını belirtir.|
|**Sonrası profili betik bağımsız değişkenleri**|Sonrası profili komut dosyasına geçirilecek bağımsız değişkenleri belirtir.|