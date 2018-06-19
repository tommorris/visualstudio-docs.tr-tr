---
title: 'Nasıl yapılır: Visual Studio 2017 genişletilebilirlik projeleri geçirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/09/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 8ca07b00-a3ff-40ab-b647-c0a93b55e86a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 93f5d663a31d43dc7a52cbd11261ca78134c682a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133550"
---
# <a name="how-to-migrate-extensibility-projects-to-visual-studio-2017"></a>Nasıl yapılır: Visual Studio 2017 genişletilebilirlik projeleri geçirme

Bu belge, Visual Studio 2017 genişletilebilirlik projelerini yükseltme açıklanmaktadır. Proje dosyaları güncelleştirmek nasıl açıklayan ek olarak, yeni sürüm 3 VSIX bildirim biçimine (VSIX v3) uzantısı bildirim sürümden 2 (VSIX v2) yükseltmek nasıl de açıklanmaktadır.

## <a name="install-visual-studio-2017-with-required-workloads"></a>Visual Studio 2017 gerekli iş yükleri ile yükleme

Aşağıdaki iş yüklerini yüklemenizi içerdiğinden emin olun:

* .NET masaüstü geliştirme
* Visual Studio uzantısı geliştirme

## <a name="open-vsix-solution-in-visual-studio-2017"></a>Visual Studio 2017 açık VSIX çözümde

Tüm VSIX projeleri Visual Studio 2017 ana sürüm tek yönlü yükseltmeye gerektirir.

Proje dosyası (örneğin *.csproj) güncelleştirilecek:

* MinimumVisualStudioVersion - 15.0 için şimdi Ayarla
* OldToolsVersion (varsa önceden var)-şimdi 14.0 için ayarlama

## <a name="update-the-microsoftvssdkbuildtools-nuget-package"></a>Microsoft.VSSDK.BuildTools NuGet paketi güncelleştirme

>**Not:** çözümünüzü Microsoft.VSSDK.BuildTools NuGet paketi başvurmaması durumunda bu adımı atlayabilirsiniz.

Yeni VSIX v3 uzantı oluşturmak için (sürüm 3) biçimi çözümünüzü gerekecektir yeni VSSDK derleme araçları ile oluşturulmuş. Bu Visual Studio 2017 ile yüklenir, ancak VSIX v2 uzantınızı NuGet aracılığıyla daha eski bir sürümü başvuru bulunduran. Bu durumda, çözümünüz için Microsoft.VSSDK.BuildTools NuGet paketi güncelleştirme el ile yüklemeniz gerekir.

Microsoft.VSSDK.BuildTools NuGet başvurularını güncelleştirmek için:

* Çözüm üzerinde sağ tıklatın ve seçin **çözüm için NuGet paketlerini Yönet...**
* Gidin **güncelleştirmeleri** sekmesi.
* Microsoft.VSSDK.BuildTools (en son sürüm) seçin.
* Tuşuna **güncelleştirme**.

![VSSDK derleme araçları](media/vssdk-build-tools.png)

## <a name="make-changes-to-the-vsix-extension-manifest"></a>VSIX uzantı bildirimi için değişiklik yapma

Visual Studio kullanıcının yüklemesi uzantısı çalıştırmak için gerekli tüm derlemelerde olduğundan emin olmak için tüm önkoşul bileşenleri veya paketler uzantısı bildirim dosyasında belirtin. Bir kullanıcı uzantı yükleme girişiminde bulunduğunda VSIXInstaller tüm önkoşulların yüklü olup olmadığını kontrol eder. Bazı eksikse, eksik bileşenleri uzantısı yükleme işleminin bir parçası olarak yüklemek için kullanıcı istenir.

>**Not:** en azından tüm uzantıları Visual Studio çekirdek Düzenleyici bileşeni bir önkoşul olarak belirtmeniz gerekir.

* (Genellikle source.extension.vsixmanifest olarak da adlandırılır) uzantı bildirim dosyasını düzenleyin.
* Olun `InstallationTarget` 15.0 içerir.
* Gerekli yükleme önkoşulları (aşağıdaki örnekte gösterildiği gibi) ekleyin.
  * Yalnızca bileşen kimlikleri için yükleme önkoşulları belirlemek öneririz.
  * İçin bu belgenin sonuna bakın [Bileşen kimlikleri tanımlayan yönergeleri](#finding-component-ids).

Örnek:

```xml
<PackageManifest>
 ...
    <Prerequisites>
        <Prerequisite Id="Microsoft.VisualStudio.Component.CoreEditor" Version="[15.0,16.0)" />
        <Prerequisite Id="Microsoft.VisualStudio.Component.DiagnosticTools" Version="[15.0.25814.0,16.0)" />
        <Prerequisite Id="Microsoft.VisualStudio.Shell.12.0" Version="[12.0]" />
    </Prerequisites>
 ...
</PackageManifest>
```

### <a name="option-use-the-designer-to-make-changes-to-the-vsix-extension-manifest"></a>Seçenek: Tasarımcı VSIX uzantı bildirimi için değişiklik yapmak için kullanın.

Bildirim XML doğrudan düzenlemek yerine yeni kullanabileceğiniz **Önkoşullar** sizin için Önkoşullar seçmek için bildirim Tasarımcısı ve XML sekmesinde güncelleştirilir.

>**Not:** bildirim Tasarımcısı yalnızca geçerli Visual Studio örnek üzerinde yüklü bileşenleri (iş yükleri veya paketleri) seçmenize olanak sağlar. Bir iş yükü için bir önkoşul eklemeniz gerekiyorsa, paket veya şu anda yüklü değil, bileşen XML bildirimi doğrudan düzenleyebilirsiniz.

* Source.extension.vsixmanifest [tasarım] dosyasını açın.
* Seçin **Önkoşullar** sekmesi ve tuşuna **yeni** düğmesi.

  ![VSIX bildirim Tasarımcısı](media/vsix-manifest-designer.png)

* **Yeni önkoşul eklemek** penceresi açılır.

  ![VSIX önkoşul ekleme](media/add-vsix-prerequisite.png)

* İçin açılan listeyi tıklatın **adı** ve istenen önkoşul seçin.
* Sürüm gerekirse güncelleştirin.

  >Not: Sürüm alanı bir aralığı en çok kapsayıcı (ancak değil de dahil olmak üzere) ile şu anda yüklü bileşen sürümü ile önceden doldurulur bileşenin sonraki ana sürümü.

  ![roslyn önkoşul ekleme](media/add-roslyn-prerequisite.png)

* Press **OK**.

## <a name="update-debug-settings-for-project"></a>Projesi için hata ayıklama ayarlarını güncelleştirme

Visual Studio deneysel örneği uzantı hata ayıklama isterseniz, emin olun proje ayarlarını **hata ayıklama** > **Başlat eylem** sahip **dış Başlat Program:** Visual Studio 2017 yüklemenizi devenv.exe dosyasına değerini ayarlayın.

Bunu aşağıdaki gibi görünmelidir:

```
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\devenv.exe
```

![Dış program Başlat](media/start-external-program.png)

>**Not:** hata ayıklama eylemi Başlat genellikle depolanır. csproj.user dosya. Bu dosya, genellikle .gitignore dosyası içinde bulunur ve bu nedenle, normal olarak kaynak denetimi için kaydedilen diğer proje dosyaları ile kaydedilmez. Çözümünüzü yeni kaynak denetiminden çekilen durumunda, bu nedenle proje başlangıç eylem için hiçbir değerlere sahip olur olasıdır. Visual Studio 2017 ile oluşturulan yeni VSIX proje olacaktır bir. csproj.user dosya geçerli Visual Studio yükleme dizinine işaret eden varsayılanları ile oluşturulmuş. VSIX v2 uzantısı geçiriyorsanız, ancak olasıdır,. csproj.user dosya önceki Visual Studio sürüme ait yükleme dizini başvurular içerir. Değeri ayarlanırken **hata ayıklama** > **Başlat eylem** uzantınızı hata ayıklamak çalıştığınızda başlatmak doğru Visual Studio deneysel örneği izin verir.

## <a name="check-that-the-extension-builds-correctly-as-a-vsix-v3"></a>Uzantı doğru (bir VSIX v3) derlemeler denetleyin

* VSIX projesi oluşturun.
* Oluşturulan VSIX sıkıştırmasını açın.
  * Göre varsayılan VSIX dosya yaşamlarını bin/Debug içinde veya bin / [YourCustomExtension] .vsix sürüm.
  * .Vsix kolayca içeriğini görüntülemek için .zip olarak yeniden adlandırın.
* Üç dosya varlığını denetle:
  * Extension.vsixmanifest
  * manifest.JSON
  * catalog.JSON

## <a name="check-when-all-required-prerequisites-are-installed"></a>Tüm gerekli Önkoşullar yüklendi denetimi

VSIX bir makinede yüklü gereken tüm önkoşulları başarıyla yüklenir. sınayın.

>**Not:** uzantıyı yüklemeden önce lütfen Visual Studio tüm örneklerini kapatın.

Uzantıyı yüklemek dener:

* Visual Studio 2017 üzerinde

![Visual Studio 2017 VSIX yükleyicisini](media/vsixinstaller-vs-2017.png)

* İsteğe bağlı: Visual Studio'nun önceki sürümleri denetleyin.
  * Geriye dönük uyumluluk kanıtlar.
  * Çalışmalıdır Visual Studio 2012, Visual Studio 2013, Visual Studio 2015 için.
* İsteğe bağlı: VSIX yükleyici sürümü denetleyicisi sürümlerinin bir seçenek sunar denetleyin.
  * Visual Studio'nun önceki sürümleri (yüklüyse) içerir.
  * Visual Studio 2017 içerir.

Visual Studio son açılmışsa, bu gibi bir iletişim kutusu görebilirsiniz:

![vs çalışan işlemleri](media/vs-running-processes.png)

Kapatmak için işlemleri bekleyin veya görevleri el ile bitemez. Listelenen adı veya PID'si parantez içine listelenen işlemler bulabilirsiniz.

>**Not:** Visual Studio örneği çalışırken bu işlemleri otomatik olarak kapatılacak değil. Visual Studio makinede - diğer kullanıcılardan dahil olmak üzere tüm örneklerini kapatın sonra yeniden denemeye devam emin olun.

## <a name="check-when-missing-the-required-prerequisites"></a>Gerekli Önkoşullar eksik olduğunda denetleyin

* Uzantıyı bir makinede Visual Studio 2017 bu olmadığı içeren (yukarıda) Önkoşullar tanımlanan tüm bileşenleri yüklemek çalışır.
* Yükleme eksik Bileşen/s tanımlar ve bunları bir önkoşul olarak VSIXInstaller listeler denetleyin.
* Not: herhangi bir önkoşulu uzantısıyla yüklenmesi gerekiyorsa, yükseltme gerekli olacaktır.

![Önkoşul eksik vsixinstaller](media/vsixinstaller-missing-prerequisite.png)

## <a name="deciding-on-components"></a>Bileşenlerini karar verme

Bağımlılıklarını ararken bir bağımlılık birden çok bileşenleriyle eşleme bulacaksınız. Önkoşul olarak belirttiğiniz hangi bağımlılıkları önerdiğimiz Uzantınız için benzer bir işlevi olan bileşen seçin ve ayrıca, kullanıcılarınızın ve ne tür bir bileşenleri misiniz dikkate almanız için bunlar büyük olasılıkla yüklü belirlemek için veya Yükleme sorun olmayacaktır. Ayrıca, burada uzantınızı çalışmasına izin verdiği en düşük gerekli önkoşulları karşılayan bir yolla ve ek özellikler bunları belirli varsa bileşenleri algılanmadı etkinliği olmayan olması uzantılı yapı öneririz.

Daha ayrıntılı yönergeler sağlamak üzere birkaç ortak uzantı türlerini ve bunların önerilen Önkoşullar belirledik:

Uzantı türü | Görünen ad | Kimliği
--- | --- | ---
Düzenleyici | Visual Studio çekirdek Düzenleyicisi  | Microsoft.VisualStudio.Component.CoreEditor
Roslyn | C# ve Visual Basic | Microsoft.VisualStudio.Component.Roslyn.LanguageServices
WPF | Yönetilen masaüstü iş yükü çekirdek | Microsoft.VisualStudio.Component.ManagedDesktop.Core
Hata ayıklayıcı | Tam zamanında hata ayıklayıcı | Microsoft.VisualStudio.Component.Debugger.JustInTime

## <a name="finding-component-ids"></a>Bileşen kimlikleri bulma

Visual Studio ürün tarafından sıralanan bileşenlerin listesini altındadır [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](https://aka.ms/vs2017componentIDs). Bu bileşen kimlikleri önkoşul kimliklerinizi bildiriminizdeki kullanın.

Emin değilseniz hangi bileşenin belirli bir ikili, indirme içeren [bileşen ikili eşleme elektronik tablosu ->](https://aka.ms/vs2017componentid-binaries).

### <a name="vs2017-componentbinarymappingxlsx"></a>vs2017 ComponentBinaryMapping.xlsx

Excel sayfasında dört sütun vardır: **bileşen adı**, **ComponentId**, **sürüm**, ve **ikili / dosya adları**.  Arama ve belirli bileşenlere ve ikili dosyaları bulmak için filtreleri kullanabilirsiniz.

Tüm başvuruları için önce hangilerinin çekirdek Düzenleyicisi'ni (Microsoft.VisualStudio.Component.CoreEditor) bileşeni olduğunu belirleyin.  En azından tüm uzantılar için bir önkoşul olarak belirtilmesi için çekirdek Düzenleyici bileşeni gerektirir. Çekirdek Düzenleyicisi'nde olmayan bırakılan başvuruları, filtreleri Ekle **ikili / dosya adlarını** bu başvuruları alt olan bileşenleri bulmak için bölüm.

Örnekler:

* Hata ayıklayıcı uzantısına sahiptir ve projenizin VSDebugEng.dll ve VSDebug.dll başvuru olduğunu biliyorsanız filtre düğmesini tıklatın **ikili / dosya adlarını** üstbilgi.  "VSDebugEng.dll" için arama ve Tamam'ı seçin.  Sonraki filtre düğmesini tıklatın **ikili / dosya adlarını** yeniden başlığı ve "VSDebug.dll" arayın.  "Filtrelemek için Ekle geçerli seçim" onay kutusunu seçin ve Tamam'ı seçin.  Şimdi Ara **bileşen adı** en çok bir bileşen bulmak için uzantı türü için ilgili. Bu örnekte, zaman içinde sadece seçtiğiniz hata ayıklayıcı ve, vsixmanifest ekleyin.
* Projenizi hata ayıklayıcı öğeleriyle ilgilenir biliyorsanız, "adında hata ayıklayıcı hangi bileşenleri içeren görmek için hata ayıklayıcı" Filtre Arama kutusuna arama yapabilirsiniz.

## <a name="specifying-a-visual-studio-2017-release"></a>Visual Studio 2017 sürüm belirtme

Uzantınızın Visual Studio 2017 belirli bir sürümünü gerektiriyorsa, örneğin, 15.3 serbest bir özellik bağlıdır, içinde VSIX içine yapı numarası belirtmelisiniz **InstallationTarget**. Örneğin, yayın 15.3 '15.0.26730.3' derleme sayısı vardır. Yapı numaralarını sürümlerini eşleme görebilirsiniz [burada](../install/visual-studio-build-numbers-and-release-dates.md). '15.3' sürüm numarasını kullanarak düzgün çalışmaz.

Uzantınızı 15.3 gerektirir veya üzeri, bildirmek **InstallationTarget sürüm** olarak [15.0.26730.3, 16.0):

```xml
<Installation>
  <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0.26730.3, 16.0)" />
</Installation>
```