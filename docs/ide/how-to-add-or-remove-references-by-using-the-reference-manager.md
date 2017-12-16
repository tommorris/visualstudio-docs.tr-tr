---
title: "Nasıl yapılır: başvuru ekleme veya kaldırma başvuru Yöneticisi'ni kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ReferenceManager
helpviewer_keywords:
- Visual C# projects, references
- references [Visual Studio], adding
- assemblies [Visual Studio], references
- Visual Basic projects, references
- project references, adding
- referencing components, adding references
- project references, removing
- referencing assemblies
- referencing components, removing references
- references [Visual Studio], removing
- referencing components, assemblies not listed
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1a4e225f8a68923963549ba70b7900b0692ddad3
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="how-to-add-or-remove-references-by-using-the-reference-manager"></a>Nasıl yapılır: ekleme veya başvuru Yöneticisi'ni kullanarak başvuruları kaldırma

Kullanabileceğiniz **başvuru Yöneticisi** veya başka bir şirketin geliştirilen eklemek ve yönetmek için iletişim kutusu sizin Microsoft, bileşenleri için başvuruyor. Evrensel Windows uygulama geliştiriyorsanız, projenize otomatik olarak doğru Windows SDK DLL'leri tümünün başvurur. .NET uygulama geliştiriyorsanız, projenize otomatik olarak mscorlib.dll başvurur. Bazı .NET API'ları el ile eklemek zorunda bileşenlerinde sunulur. COM bileşenleri veya özel bileşenleri başvuruları el ile eklenmesi gerekir.

## <a name="reference-manager-dialog-box"></a>Başvuru Yöneticisi iletişim kutusu

**Başvuru Yöneticisi** iletişim kutusu, sol taraftaki proje türüne bağlı olarak farklı kategorileri gösterir:

- [Derlemeleri](#assemblies), Framework ve uzantıları alt grupları ile.

- [COM](#com), başvurmak için kullanılabilir tüm COM bileşenlerini listeler.

- [Çözüm](#solution), projeler alt ile.

- [Windows](#windows), çekirdek ve uzantıları alt grupları ile. Kullanarak Windows SDK veya uzantı SDK'ları başvurularında keşfedebilirsiniz **Nesne Tarayıcısı**.

- [Gözat](#browse), son alt ile.

## <a name="adding-and-removing-a-reference"></a>Ekleme ve bir başvuru kaldırma

### <a name="to-add-a-reference"></a>Başvuru eklemek için

1. İçinde **Çözüm Gezgini**başvurular düğümünü sağ tıklatın ve seçin **Başvuru Ekle**.

2. Başvurular ekleyin ve ardından belirtin **Tamam** düğmesi.

   **Başvuru Yöneticisi** açar ve grup tarafından kullanılabilir başvurular listelenmektedir.

## <a name="a-idassemblies-assemblies-tab"></a><a id="assemblies" />Derlemeleri sekmesi

**Derlemeleri** sekmesi başvurmak için kullanılabilir tüm .NET Framework derlemeleri listeler. **Derlemeleri** GAC derlemelerde çalışma zamanı ortamının bir parçası olduğundan, sekmesinde tüm derlemeleri genel derleme önbelleğinden (GAC) listesinde değil. Dağıtma veya GAC içinde kayıtlı bir derlemesine başvuru içeren bir uygulama kopyalarsanız derleme olmaz dağıtılacağını veya kopya yerel ayarından bağımsız olarak bu uygulama ile kopyalanır. Daha fazla bilgi için bkz: [bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md).

El ile eklediğinizde kümesinin EnvDTE ad alanları (EnvDTE EnvDTE80, EnvDTE90, EnvDTE90a veya EnvDTE100), herhangi bir başvuru **birlikte çalışma türlerini katıştır** referansı özelliğinin **False** içinde Özellikler penceresini açın. Bu özelliği ayarlamak **doğru** neden sorunları katıştırılmış olamaz belirli EnvDTE özellikleri nedeniyle oluşturabilirsiniz.

Tüm masaüstü projeleri, mscorlib öğesine örtük bir başvuru içerir. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]projeleri Microsoft.VisualBasic dolaylı bir başvuru içerir. Başvuruları listesinden kaldırılır olsa bile tüm projeleri System.Core, dolaylı bir başvuru içeriyor.

Proje türü derlemeleri desteklemiyorsa, sekme, görünmez **başvuru Yöneticisi** iletişim kutusu.

Derlemeler sekmesi iki alt sekmeden oluşur:

1. **Framework** hedef çerçeveyi oluşturan tüm derlemeleri listeler.

    Projeler için [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamaları içeren tüm hedeflenen derlemelerde başvuruları [!INCLUDE[net_win8_profile](../ide/includes/net_win8_profile_md.md)] varsayılan olarak proje oluşturma. Yönetilen projelerinde başvuruları klasöründe salt okunur bir düğümünde **Çözüm Gezgini** tüm Framework başvuru gösterir. Buna göre Framework sekmesini olmaz Framework derlemelerden birini numaralandırmak ve bunun yerine aşağıdaki iletiyi görüntüler: "tüm Framework derlemeler zaten başvurulur. Lütfen Nesne Tarayıcısı Framework başvurularında keşfetmek için kullanın." Masaüstü projeleri için hedef çerçeveyi derlemelerden Framework sekmesini numaralandırır ve kullanıcının uygulama gerektiriyor başvurular eklemeniz gerekir.

2. **Uzantıları** bileşenleri ve denetimleri harici satıcıları hedef çerçeveyi genişletmek için geliştirilmiş tüm derlemeleri listeler. Kullanıcı uygulamasının amacına bağlı olarak, bu derlemelere gerek duyulabilir.

    - Uzantılar, aşağıdaki konumlarda kayıtlı derlemeleri numaralandırmak suretiyle doldurulur:

        ```
        32-bit machine:
        HKEY_CURRENT_USER\SOFTWARE\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]  
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]  
        64-bit machine:
        HKEY_CURRENT_USER\SOFTWARE\Wow6432Node\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]  
        HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]  
        And older versions of the [Target Framework Identifier]  
        ```

        Örneğin, bir proje .NET Framework 4 32-bit makine hedefliyorsa, uzantıları \Microsoft altında kayıtlı derlemeleri Numaralandırılacak\\. NETFramework\v4.0\AssemblyFoldersEx\\, \Microsoft\\. NETFramework\v3.5\AssemblyFoldersEx\\, \Microsoft\\. NETFramework\v3.0\AssemblyFoldersEx\\ve \Microsoft\\. NETFramework\v2.0\AssemblyFoldersEx\\.

Listedeki bazı bileşenler, bağlı olarak görüntülenmeyebilir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] projenizi sürümü. Bu aşağıdaki durumlarda oluşabilir:

- Yeni bir .NET Framework sürümü kullanan bir bileşeni .NET Framework'ün önceki bir sürümünü hedefleyen bir projede ile uyumlu değil.

    Bir proje için hedef .NET Framework sürümü değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

- Kullanan bir bileşen [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] hedefleyen bir projede ile uyumsuz [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)].

    Bazı projeleri hedef yeni bir uygulama oluşturduğunuzda [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)] varsayılan olarak.

- Bunun yapılması, derleme hataları neden olabileceğinden aynı çözümde başka bir projeye çıkışları dosyası başvuruları ekleme kaçınmalısınız. Bunun yerine, kullanın **projeleri** sekmesinde **Başvuru Ekle** proje proje başvuruları oluşturmak için iletişim kutusu. Bu takım geliştirme projelerinizde oluşturduğunuz sınıf kitaplıkları daha iyi yönetim etkinleştirerek kolaylaştırır. Daha fazla bilgi için bkz: [bozuk başvuruları sorun giderme](../ide/troubleshooting-broken-references.md).

> [!NOTE]
> Visual Studio 2015 veya sonraki sürümlerde, bir dosya başvurusu proje başvurusu yerine hedef bir proje .NET Framework sürüm 4.5 veya sonraki sürümü olan ve diğer projenin hedef sürüm 2, 3, 3.5 veya 4.0 sürümünü ise oluşturulur.

### <a name="to-display-an-assembly-in-the-add-reference-dialog-box"></a>Bir derleme başvurusu Ekle iletişim kutusunda görüntülemek için

- Taşıma veya derleme aşağıdaki konumlardan birine kopyalayın:

    - Geçerli proje dizini. (Bu derlemeler kullanarak bulabilirsiniz **Gözat** sekmesi.)

    - Diğer aynı çözüme proje dizinlerde. (Bu derlemeler kullanarak bulabilirsiniz **projeleri** sekmesi.)

    \-veya -

- Görüntülenecek derlemelerin konumunu belirten bir kayıt defteri anahtarını ayarlayın:

    Bir 32 bit işletim sistemi için aşağıdaki kayıt defteri anahtarlarından birini ekleyin.

    - [Arasına\\. NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@= "*AssemblyLocation*"

    - [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@= "*AssemblyLocation*"

    Bir 64-bit işletim sistemi için aşağıdaki kayıt defteri anahtarlarından birinin 32-bit kayıt defteri kovanında ekleyin.

    - [HKEY_CURRENT_USER\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@= "*AssemblyLocation*"

    - [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@= "*AssemblyLocation*"

    *VersionMinimum* geçerli en düşük .NET Framework sürümü. Varsa *VersionMinimum* v3.0, AssemblyFoldersEx içinde belirtilen klasörleri uygulamadığınız projelerine hedefleyen .NET Framework 3.0 ve üstü.

    *AssemblyLocation* görünmesini istediğiniz derlemeleri dizin **Başvuru Ekle** iletişim kutusu, örneğin, C:\MyAssemblies\\.

    HKEY_LOCAL_MACHINE düğümü altındaki kayıt defteri anahtarı oluşturulurken belirtilen konumda derlemelerde görmek tüm kullanıcıların sağlar **Başvuru Ekle** iletişim kutusu. HKEY_CURRENT_USER düğümü altındaki kayıt defteri anahtarı oluşturma, yalnızca geçerli kullanıcının ayarını etkiler.

    Açık **Başvuru Ekle** yeniden iletişim kutusu. Derlemeleri görünmesi gereken **.NET** sekmesi. Yapmazsanız, derlemeler bulunduğu olduğundan emin olun belirtilen *AssemblyLocation* dizini, Visual Studio'yu yeniden başlatın ve yeniden deneyin.

## <a name="a-idcom-com-tab"></a><a id="com" />COM sekmesi

COM sekmesi, başvuru için kullanılabilen tüm COM bileşenlerini listeler. Dahili bildirim içeren kayıtlı bir COM DLL öğesine başvuru eklemek isterseniz, önce DLL kaydını silin. Aksi takdirde, Visual Studio, derleme başvurusunu yerel bir DLL olarak değil, bir ActiveX Denetimi olarak ekler.

Proje türü COM desteklemiyorsa, sekme, görünmez **başvuru Yöneticisi** iletişim kutusu.

## <a name="a-idsolution-solution-tab"></a><a id="solution" />Çözüm sekmesi

Çözüm sekmesi, geçerli çözüm içindeki tüm uyumlu projeleri Projeler alt sekmesinde listeler.

Bir proje, farklı bir .NET Framework sürümünü hedef alan başka bir projeye başvuruda bulunabilir. Örneğin, hedefleyen bir proje oluşturabilirsiniz [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] ancak için .NET Framework 2 yerleşik olan bir derleme başvuruyor. Ancak, .NET Framework 2 proje başvuramaz bir [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] projesi. Daha fazla bilgi için bkz: [belirli bir .NET Framework sürümü hedefleme](../ide/targeting-a-specific-dotnet-framework-version.md).

Hedefleyen bir projede [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] hedefleyen bir projede ile uyumsuz [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)].

Bir proje hedefleri .NET Framework 4 ve başka bir projeye önceki bir sürümünü hedefliyorsa dosya başvurusu yerine proje başvurusu oluşturulur.

Hedefleyen bir projede [!INCLUDE[net_win8_profile](../ide/includes/net_win8_profile_md.md)] .NET Framework hedefleyen bir projede bir proje başvurusu eklenemiyor tersi.

## <a name="a-idwindows-windows-tab"></a><a id="windows" />Pencereler sekmesi

Windows sekmesi, Windows işletim sisteminin çalıştığı platformlara özgü tüm SDK'ları listeler.

Visual Studio'da bir WinMD dosyasını iki şekilde oluşturabilirsiniz:

- **[!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]yönetilen uygulama projeleri**: [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulaması projeleri çıktı WinMD ikili dosyaları proje özellikleri &#124; ayarlayarak Çıktı türü = WinMD dosyası. WinMD dosya adı, içinde varolan tüm alan adlarının üst küme alan adı olmalıdır. Örneğin, bir proje A.B ve A.B.C ad alanlarından oluşuyorsa, çıktısı verilen WinMD için olası adlar A.winmd ve A.B.winmd olur. Bir kullanıcı bir proje özellikleri &#124;girerse; Derleme adı veya proje özellikleri &#124; Ayrık ad alanları projeye kümesinden Namespace değer veya bir projede hiç üst ad alanı, bir derleme uyarı oluşturulduğu: 'A.winmd' Bu derleme için bir geçerli .winmd dosya adı değil. Bir Windows Meta Veri dosyası içindeki tüm türler, dosya adının bir alt ad alanında mevcut olmalıdır. Dosya adı bir alt ad alanında var olmayan türleri çalışma zamanında bulunması mümkün olmayacaktır. Bu derlemede, en küçük ortak ad alanı 'CSWSClassLibrary1'dir. Bir masaüstü Visual Basic veya Visual C# projesi kullanarak, oluşturulan WinMDs yalnızca tüketebileceği [!INCLUDE[win8](../debugger/includes/win8_md.md)] birinci taraf WinMDs bilinir ve WinMDs oluşturulamıyor, SDK.

- **[!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]uygulaması yerel projeleri**: meta verileri yalnızca yerel bir WinMD dosyası oluşur. Uygulaması ayrı bir DLL dosyası içinde var olur. Bir oluşturabilirsiniz yerel ikili dosyaları Windows çalışma zamanı bileşeni proje şablonu seçerek **yeni proje** iletişim kutusu ya da boş bir proje başlatarak ve WinMD dosyası oluşturmak için proje özelliklerini değiştirme. Proje kopuk ad alanlarından oluşuyorsa, bir yapı hatası kullanıcıya ad alanlarını birleştirmesi veya MSMerge aracını çalıştırması gerektiğini söyler.

Windows sekmesi iki alt gruptan oluşur.

### <a name="core-subgroup"></a>Çekirdek alt

Çekirdek alt grubu, hedeflenen Windows sürümü için SDK içindeki tüm WinMD'leri (Windows Çalışma Zaman öğeleri için) listeler.

[!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]Uygulama projeleri içeren tüm WinMDs başvuruları [!INCLUDE[win8](../debugger/includes/win8_md.md)] SDK varsayılan olarak proje oluşturma. Yönetilen projelerinde başvuruları klasöründe salt okunur bir düğümünde **Çözüm Gezgini** tüm referansı gösterir [!INCLUDE[win8](../debugger/includes/win8_md.md)] SDK. Çekirdek alt başvuru Yöneticisi'nde derlemelerden birini buna göre listeleme olmaz [!INCLUDE[win8](../debugger/includes/win8_md.md)] SDK ve bunun yerine bir ileti görüntüler: "Windows SDK zaten başvuruyor. Lütfen nesne tarayıcısı Windows SDK'sı içindeki başvuruların keşfetmek için kullanın."

Masaüstü projelerinde çekirdek alt varsayılan olarak görünmüyor. Windows çalışma zamanı proje düğümünün kısayol menüsünü açarak ekleyebilirsiniz seçme **projeyi**, aşağıdaki kod parçacığında ekleme ve projeyi yeniden açmayı (proje düğümüne seçin **projeyiyenidenyükle**). Ne zaman çağırmayı **başvuru Yöneticisi** çekirdek alt iletişim kutusu görüntülenir.

```xml
<PropertyGroup>
  <TargetPlatformVersion>8.0</TargetPlatformVersion>
</PropertyGroup>
```

Seçtiğinizden emin olun **Windows** bu alt grup onay kutusu. Bundan sonra Windows Çalışma Zamanı öğelerini kullanabilmeniz gerekir. Bununla birlikte, Windows Çalışma Zamanı'nın IEnumerable gibi bazı standart sınıfları ve arabirimleri (Windows Çalışma Zamanı kitaplıklarının her yerinde kullanılan) tanımladığı System.Runtime öğesini de eklemek isteyeceksiniz. Modülüyle ekleme hakkında daha fazla bilgi için bkz: [yönetilen Masaüstü uygulamaları ve Windows çalışma zamanı](http://msdn.microsoft.com/library/windows/apps/jj856306.aspx#consuming_standard_windows_runtime_types).

### <a name="extensions-subgroup"></a>Uzantıları alt

Uzantılar, hedeflenen Windows platformunu genişleten kullanıcı SDK'larını listeler. Bu sekme görünür [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulama projeleri yalnızca. Yalnızca birinci taraf .winmd dosyaları tüketebildiğinden Masaüstü projeleri bu sekme göstermeyecektir.

SDK, Visual Studio'nun tek bir bileşen olarak kabul ettiği dosyalar topluluğudur. Uzantıları sekmesinde, projeye, uygulama SDK'ları **başvuru Yöneticisi** iletişim kutusu çağrıldığı tek girişleri olarak listelenir. Bir projeye eklendiğinde, tüm SDK içeriği tüketilen Visual Studio tarafından sağlayacak şekilde kullanıcı IntelliSense, araç kutusu, tasarımcıları, SDK içeriğini yararlanmak için gereken diğer işlemleri yapmanıza gerek olmayan nesne tarayıcısı, yapı, hata ayıklama ve paketleme dağıtım. SDK uzantıları sekmesinde görüntüleme hakkında daha fazla bilgi için bkz: [bir yazılım geliştirme seti oluşturma](../extensibility/creating-a-software-development-kit.md).

> [!NOTE]
> Bir proje üzerinde başka bir SDK bağlıdır bir SDK başvuruyorsa, Visual Studio kullanıcı el ile ikinci SDK'sına bir başvuru ekler sürece ikinci SDK tüketmezsiniz. Ne zaman bir kullanıcının seçtiği bir SDK üzerinde **uzantıları** sekmesinde **başvuru Yöneticisi** iletişim kutusu yalnızca adını ve SDK sürümü aynı zamanda tüm SDK adını listeleyerek SDK bağımlılığı tanımlamak kullanıcı yardımcı olur Ayrıntılar bölmesinde bağımlılıkları. Varsa bir kullanıcı bağımlılıkları fark etmez ve yalnızca SDK, MSBuild bağımlılıkları eklemek için kullanıcıyı uyarır ekler.

Proje türü desteklemiyorsa **uzantıları**, sekmesi içinde görünmüyor **başvuru Yöneticisi** iletişim kutusu.

## <a name="a-idbrowse-browse-button"></a><a id="browse" />Gözat düğmesi

Kullanabileceğiniz **Gözat** bir bileşen için dosya sistemindeki gözatmak için düğmeyi.

Bir proje, farklı bir .NET Framework sürümünü hedef alan başka bir bileşene başvuruda bulunabilir. Örneğin, .NET Framework 2'yi hedefleyen bir bileşene başvuruda bulunan .NET Framework 4 İstemci Profili'ni hedef alan bir uygulama oluşturabilirsiniz. Daha fazla bilgi için bkz: [belirli bir .NET Framework sürümü hedefleme](../ide/targeting-a-specific-dotnet-framework-version.md).

Aynı çözümdeki başka bir projenin çıktılarına dosya başvuruları eklemekten kaçınmalısınız; bu taktik derleme hatalarına neden olabilir. Bunun yerine, kullanın **çözüm** sekmesinde **başvuru Yöneticisi** proje proje başvuruları oluşturmak için iletişim kutusu. Bu takım geliştirme projelerinizde oluşturduğunuz sınıf kitaplıkları daha iyi yönetim etkinleştirerek kolaylaştırır. Daha fazla bilgi için bkz: [bozuk başvuruları sorun giderme](../ide/troubleshooting-broken-references.md).

Bir SDK göz atın ve projenize ekleyin. Yalnızca bir dosyaya (örneğin, bir derleme veya .winmd) göz atabilir ve bu dosyayı projenize ekleyebilirsiniz.

Bir WinMD dosyası başvuru yaparken olan beklenen düzeni *FileName*.winmd, *FileName*.dll, ve *FileName*.pri dosyaları tüm yerleştirilir diğer. Aşağıdaki senaryolarda bir WinMD'ye başvuruda bulunursanız, proje çıkış dizinine eksik bir dosya kümesi kopyalanır ve sonuç olarak, derleme ve çalışma zamanı hataları meydana gelir.

- **Yerel bileşen**: bir yerel her ayrık ad alanları kümesi için bir WinMD ve uygulanması oluşan bir DLL oluşturacaksınız. WinMD'ler ayrı adlara sahip olur. Bu yerel bileşen dosya başvururken MSBuild dissimilarly adlandırılmış WinMDs bir bileşen olun tanımaz. Sonuç olarak, yalnızca aynı adlı *FileName*.dll ve *FileName*.winmd kopyalanacak ve çalışma zamanı hataları oluşur. Bu sorunu geçici bir çözümle aşmak için bir Uzantı SDK oluşturun. Daha fazla bilgi için bkz: [bir yazılım geliştirme seti oluşturma](../extensibility/creating-a-software-development-kit.md).

- **Denetimlerin tüketmesini**: en az bir XAML denetimi oluşan bir *FileName*.winmd, *FileName*.dll, *FileName*.pri, *XamlName* .xaml ve bir *görüntü adı*.jpg. Proje yapılandırıldığında, projenin çıktı dizinine kopyalanmış ve yalnızca dosya başvuru ile ilişkili kaynak dosyaları vermeyecektir *FileName*.winmd, *FileName*.dll ve *FileName*.pri kopyalanacak. Bir derleme hatası kullanıcıyı bilgilendirmek üzere kaydedilir, kaynakları *XamlName*.xaml ve *görüntü adı*.jpg eksik. Başarılı olması için, kullanıcının bu kaynak dosyaları oluşturma ve hata ayıklama/çalışma zamanı için proje çıkış dizinine el ile kopyalaması gerekir. Bu sorunu çözmek için ya da bir uzantı SDK içindeki adımları izleyerek oluşturun [bir yazılım geliştirme seti oluşturma](../extensibility/creating-a-software-development-kit.md) veya aşağıdaki özelliği eklemek için proje dosyasını düzenleyin:

    ```xml
    <PropertyGroup>
       <GenerateLibraryOutput>True</GenerateLibraryOutput>
    </PropertyGroup>
    ```

    > [!NOTE]
    > Özelliği eklerseniz, yapı daha yavaş çalışabilir.

## <a name="recent"></a>En Son

Derlemeler, COM, Windows ve Gözat'ın her biri, bir En Son sekmesini destekler ve bu sekme projelere yakın zamanda eklenmiş bileşenlerin listesini numaralandırır.

## <a name="search"></a>Ara

Arama çubuğuna **başvuru Yöneticisi** odakta sekmesi üzerinden iletişim kutusu çalışır. Örneğin, bir kullanıcı arama çubuğunda sırasında "Sistem" yazdığında **çözüm** sekmesini odakta, "Sistem" içeren bir proje adı çözüm oluşur sürece arama tüm sonuçları döndüren olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md)
