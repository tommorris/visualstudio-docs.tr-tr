---
title: "Visual Studio 2017 genişletilebilirliği değişiklikler | Microsoft Docs"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54d5af60-0b44-4ae1-aa57-45aa03f89f3d
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1d474374a0c7603bc9b6995783bbed96c81c8907
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="changes-in-visual-studio-2017-extensibility"></a>Visual Studio 2017 genişletilebilirlik değişiklikleri

Visual Studio 2017 ile sunuyoruz bir [daha hızlı ve hafifletilmiş Visual Studio yükleme deneyimi](https://blogs.msdn.microsoft.com/visualstudio/2016/04/01/faster-leaner-visual-studio-installer) azaltan Visual Studio etkisi kullanıcı sistemlerinde özellikleri ve iş yükleri üzerinde kullanıcılara daha fazla seçenek verilirken yüklü değildir. Bu geliştirmeler desteklemek için biz genişletilebilirlik modeline değişiklik yaptınız ve Visual Studio genişletilebilirlik bazı önemli değişiklikler yaptınız. Bu belgede, bu değişiklikler ve ne bunları ele almak için yapılabilir teknik ayrıntılar anlatmaktadır. Bazı bilgiler zaman içinde nokta uygulama ayrıntılarını ve daha sonra değiştirilemez lütfen unutmayın.

## <a name="changes-affecting-vsix-format-and-installation"></a>VSIX biçimi ve yükleme etkileyen değişiklikleri

VSIX v3 Tanıtımı Hafif yükleme deneyimini desteklemek için (sürüm 3) biçimi.

VSIX biçimi değişiklikleri içerir:

* Kurulum önkoşullarını bildirimi. Visual Studio, hızlı yükleme, bir basit promise üzerinde sunmak için yükleyici şimdi kullanıcılara daha fazla yapılandırma seçenekleri sunar. Sonuç olarak, bir uzantı tarafından gerekli bileşenleri ve özellikleri yüklü olduğundan emin olun, uzantıları bağımlılıklarını bildirmeniz gerekir.
  * Visual Studio 2017 yükleyici edinmeli ve kullanıcı için gerekli olan bileşenler uzantınızı yükleme bir parçası olarak yüklemek otomatik olarak sunar.
  * Kullanıcılar kendi bildiriminde sürümünü 15.0 hedefleme olarak işaretlenmiş olsa bile, yeni VSIX v3 biçimi kullanılarak oluşturulmuş olmayan bir uzantı yüklenmeye çalışırken alırsınız.
* Gelişmiş özellikleri VSIX biçimi. Üzerinde teslim etmek için bir [low Impact yükleme](https://blogs.msdn.microsoft.com/visualstudio/2016/04/25/anatomy-of-a-low-impact-visual-studio-install) de yan yana yüklemeler destekleyen Visual Studio'nun biz artık çoğu yapılandırma verileri sistem kayıt defterine Kaydet ve Visual Studio özel derlemeler GAC dışında taşınmış. Biz de VSIX biçimini ve VSIX yükleme altyapısı yeteneklerini bazı yükleme türleri, uzantıları yüklemek için bunun yerine bir MSI ya da EXE kullanmanıza olanak sağlayan daha yüksek.

  Yeni özellikleri şunlardır:

  * Belirtilen Visual Studio örneği içine kaydı.
  * Yükleme dışında [uzantıları klasörünü](set-install-root.md).
  * İşlemci mimarisi algılama.
  * Dil Ayrılmış dil paketlerini bağımlılığı.
  * Yükleme işlemine [NGEN Destek](ngen-support.md).

## <a name="building-an-extension-for-visual-studio-2017"></a>Bir uzantıyı Visual Studio 2017 için oluşturma

Tasarımcı yeni yazmak için tooling VSIX v3 bildirim biçimi Visual Studio 2017 ' kullanıma sunulmuştur. Eşlik eden belgesine bakın [nasıl yapılır: Visual Studio 2017 genişletilebilirlik projelerine geçirmek](how-to-migrate-extensibility-projects-to-visual-studio-2017.md) Tasarımcı araçlarını kullanarak veya el ile güncelleştirmeleri projeye yapma hakkında bilgi ve VSIX v3 uzantılar geliştirmek üzere bildirimi.

## <a name="change-visual-studio-user-data-path"></a>Değiştir: Visual Studio kullanıcı veri yolu

Daha önce her ana sürümü Visual Studio'nun tek bir yüklemesini her makinede mevcut. Visual Studio 2017 yan yana yüklemesini desteklemek için Visual Studio için birden çok kullanıcı veri yollarını, kullanıcının makinesinde bulunabilir.

Visual Studio ayarları Yöneticisi'ni kullanmak için Visual Studio işlemi içinde çalıştırılan kod güncelleştirilmesi gerekir. Visual Studio işlemin dışında çalışan kodu, belirli bir Visual Studio yükleme kullanıcı yolunu bulabilir [burada yönergeleri izleyerek](locating-visual-studio.md).

## <a name="change-global-assembly-cache-gac"></a>Değişikliği: Genel Derleme Önbelleği (GAC)

Çoğu Visual Studio çekirdek derlemeler artık GAC içine yüklenir. Visual Studio işlemde çalışan kod hala gerekli derlemeleri çalışma zamanında bulabilmesi için aşağıdaki değişiklikler yapıldı.

> [!NOTE]
> [INSTALLDİR] aşağıda Visual Studio yükleme kök dizini gösterir. VSIXInstaller.exe otomatik olarak bu doldurmak ancak özel dağıtım kod yazmaya okuyun [Visual Studio bulma](locating-visual-studio.md).

* Yalnızca GAC içine yüklenmiş olan derlemelerin:
  * Bu derlemeler [INSTALLDİR] \Common7\IDE altında artık yüklüdür\, [INSTALLDİR] \Common7\IDE\PublicAssemblies veya [INSTALLDİR] \Common7\IDE\PrivateAssemblies. Bu klasörler Visual Studio işleminin algılama yolları bir parçasıdır.
* Yoklama olmayan bir yolu içine ve GAC içine yüklenmiş olan derlemelerin:
  * GAC kopyalama kurulumundan kaldırıldı.
  * .Pkgdef dosya derleme için bir kod temel girdiyi belirlemek için eklendi.

    Örneğin:
    
    ```xml
    [$RootKey$\RuntimeConfiguration\dependentAssembly\codeBase\{UniqueGUID}]
    "name"="AssemblyName" "codeBase"="$PackageFolder$\AssemblyName.dll"
    "publicKeyToken"="Public Key Token"
    "culture"="neutral"
    "version"=15.0.0.0
    ```
    Çalışma zamanında, olarak, bu girişler Visual Studio işlemin çalışma zamanı yapılandırma dosyasına (altında [VSAPPDATA]\devenv.exe.config) Visual Studio pkgdef alt birleştirecektir [ `<codeBase>` ](https://msdn.microsoft.com/en-us/library/efs781xb(v=vs.110).aspx) öğeleri. Bu yolları yoklama aracılığıyla aramayı önler olduğundan, derlemenizi Bul Visual Studio işlemini izin vermek için önerilen yoludur.

### <a name="reacting-to-this-breaking-change"></a>Bu önemli değişiklik tepki

* Uzantınızın Visual Studio işlemi içinde çalışıyorsa:
  * Kodunuzu Visual Studio çekirdek derlemeler bulamıyor olacaktır.
  * Derlemeleriniz gerekirse bir yolunu belirtmek için bir .pkgdef dosyası kullanmayı düşünün.
* Uzantınızın Visual Studio işlemi dışında çalışıyorsa:
  * Visual Studio çekirdek derlemeler [INSTALLDİR] \Common7\IDE altında arayan göz önünde bulundurun\, [INSTALLDİR] \Common7\IDE\PublicAssemblies veya yapılandırma dosyası veya bütünleştirilmiş Çözücü kullanma [INSTALLDİR] \Common7\IDE\PrivateAssemblies.

## <a name="change-reduce-registry-impact"></a>Değişikliği: kayıt defteri etkisini azaltmak

### <a name="global-com-registration"></a>Global COM kayıt

* Visual Studio çoğu kayıt defteri anahtarı yerel COM kaydını desteklemek üzere HKEY_CLASSES_ROOT ve HKEY_LOCAL_MACHINE yığınlar daha önce yüklenmiş. Bu etkilerini ortadan kaldırmak için Visual Studio artık kullanır [kayıtsız etkinleştirme COM bileşenleri için](https://msdn.microsoft.com/en-us/library/ms973913.aspx).
* Sonuç olarak, çoğu TLB / OLB / DLL dosyaları % ProgramFiles (x86) %\Common Files\Microsoft Shared\MSEnv altında tarafından varsayılan olarak Visual Studio artık yüklenir. Bu dosyalar, Visual Studio ana bilgisayar işlemi tarafından kullanılan karşılık gelen Kayıtsız COM bildirimleri ile [INSTALLDİR] altında şimdi yüklenir.
* Sonuç olarak, Visual Studio COM arabirimleri için genel bir COM kayıt dayanan harici kod artık bu kayıtları bulur. Visual Studio işlemi içinde çalıştırılan kodda bir fark görmez.

### <a name="visual-studio-registry"></a>Visual Studio kayıt defteri

* Visual Studio çoğu kayıt defteri anahtarı bir Visual Studio özel anahtarı altında sistemin HKEY_LOCAL_MACHINE ve HKEY_CURRENT_USER yığınlar halinde daha önce yüklenmiş:
  * HKLM\Software\Microsoft\VisualStudio\\**sürüm**: MSI yükleyicileri ve makine başına uzantıları tarafından oluşturulan kayıt defteri anahtarları.
  * HKCU\Software\Microsoft\VisualStudio\\**sürüm**: kullanıcıya özgü ayarları depolamak için Visual Studio tarafından oluşturulan kayıt defteri anahtarları.
  * HKCU\Software\Microsoft\VisualStudio\\**sürüm**_Config: Visual Studio HKLM anahtar yukarıdaki ve kayıt defteri anahtarlarını bir kopyasını .pkgdef dosyalarından uzantıları tarafından birleştirilir.
* Kayıt defteri üzerindeki etkisini azaltmak için Visual Studio şimdi kullanır [RegLoadAppKey](https://msdn.microsoft.com/en-us/library/windows/desktop/ms724886(v=vs.85).aspx) kayıt defteri anahtarları [VSAPPDATA]\privateregistry.bin. altında özel bir ikili dosyasında depolamak için işlevi Çok az sayıda Visual Studio özel anahtarları sistem kayıt defterinde kalır.
* Visual Studio işlemi içinde çalıştırılan var olan kodda etkilenmez. Visual Studio HKCU Visual Studio özel anahtarı altındaki tüm kayıt defteri işlemlerini özel kayıt defterine yönlendirir. Okuma ve yazma diğer kayıt defteri konumları sistem kayıt defteri kullanmaya devam eder.
* Harici kod yükleyin ve Visual Studio kayıt defteri girdileri için bu dosyayı okuma gerekecektir.

### <a name="reacting-to-this-breaking-change"></a>Bu önemli değişiklik tepki

* Harici kod kayıtsız etkinleştirme de COM bileşenlerini kullanacak şekilde dönüştürülmelidir.
* Dış bileşenler, Visual Studio konumu bulabilir [burada yönergeleri izleyerek](https://blogs.msdn.microsoft.com/heaths/2016/09/15/changes-to-visual-studio-15-setup).
* Dış bileşenler kullanmanızı öneririz [dış ayarları Yöneticisi](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.settings.externalsettingsmanager.aspx) yerine doğrudan Visual Studio kayıt defteri anahtarları için okuma/yazma.
* Uzantınızı kullanarak bileşenlerini kaydı için başka bir yöntem uygulanmadı denetleyin. Örneğin, hata ayıklayıcı uzantıları yeni yararlanmak mümkün olabilir [msvsmon JSON dosyası COM kayıt](migrate-debugger-COM-registration.md).
