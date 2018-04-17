---
title: Başvuru Yöneticisi'nde başvurular ekleyin
ms.date: 04/11/2018
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ReferenceManager
helpviewer_keywords:
- C# projects, references
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6ea4ede96af8bfa68c7de65f50d6b96f88c77018
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-or-remove-references-by-using-the-reference-manager"></a>Nasıl yapılır: ekleme veya başvuru Yöneticisi'ni kullanarak başvuruları kaldırma

Kullanabileceğiniz **başvuru Yöneticisi** veya başka bir şirketin geliştirilen eklemek ve yönetmek için iletişim kutusu sizin Microsoft, bileşenleri için başvuruyor. Evrensel Windows uygulama geliştiriyorsanız, projenize otomatik olarak doğru Windows SDK DLL'leri tümünün başvurur. .NET uygulama geliştiriyorsanız, projenize otomatik olarak başvuran *mscorlib.dll*. Bazı .NET API'ları el ile eklemek zorunda bileşenlerinde sunulur. COM bileşenleri veya özel bileşenleri başvuruları el ile eklenmesi gerekir.

## <a name="reference-manager-dialog-box"></a>Başvuru Yöneticisi iletişim kutusu

**Başvuru Yöneticisi** iletişim kutusu, sol taraftaki proje türüne bağlı olarak farklı kategorileri gösterir:

- Derlemeler; Çerçeve ve Uzantılar alt grupları ile.

- COM, başvurmak için kullanılabilir tüm COM bileşenlerini listeler.

- Çözüm; Projeler alt grubu ile.

- Windows; Çekirdek ve Uzantılar alt grupları ile. Kullanarak Windows SDK veya uzantı SDK'ları başvurularında keşfedebilirsiniz **Nesne Tarayıcısı**.

- Gözat; En Son alt grubu ile.

## <a name="add-and-remove-a-reference"></a>Ekleme ve bir başvuru kaldırma

### <a name="to-add-a-reference"></a>Başvuru eklemek için

1. İçinde **Çözüm Gezgini**, sağ tıklayın **başvuruları** veya **bağımlılıkları** düğümü seçin **Başvuru Ekle**. Ayrıca proje düğümüne sağ tıklayın ve seçin **Ekle** > **başvuru**.

   **Başvuru Yöneticisi** açar ve grup tarafından kullanılabilir başvurular listelenmektedir.

2. Başvurular ekleyin ve ardından belirtin **Tamam**.

## <a name="assemblies-tab"></a>Derlemeler sekmesi

**Derlemeleri** sekmesi başvurmak için kullanılabilir tüm .NET Framework derlemeleri listeler. **Derlemeleri** GAC derlemelerde çalışma zamanı ortamının bir parçası olduğundan, sekmesinde tüm derlemeleri genel derleme önbelleğinden (GAC) listesinde değil. Dağıtma veya GAC içinde kayıtlı bir derlemesine başvuru içeren bir uygulama kopyalarsanız derleme olmaz dağıtılacağını veya bağımsız olarak, uygulama ile kopyalanan **kopya yerel** ayarı. Daha fazla bilgi için bkz: [bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md).

El ile eklediğinizde EnvDTE ad alanları herhangi bir başvuru (<xref:EnvDTE>, <xref:EnvDTE80>, <xref:EnvDTE90>, <xref:EnvDTE90a>, veya <xref:EnvDTE100>) ayarlayın **birlikte çalışma türlerini katıştır** referansıözelliğinin**Yanlış** içinde **özellikleri** penceresi. Bu özelliği ayarlamak **doğru** neden sorunları katıştırılmış olamaz belirli EnvDTE özellikleri nedeniyle oluşturabilirsiniz.

Tüm masaüstü projeleri dolaylı bir başvuru içeren **mscorlib**. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projeleri dolaylı bir başvuru içeren <xref:Microsoft.VisualBasic>. Tüm projeleri dolaylı bir başvuru içeren **System.Core**başvuruları listesinden kaldırılır olsa bile.

Proje türü derlemeleri desteklemiyorsa, sekme, görünmez **başvuru Yöneticisi** iletişim kutusu.

**Derlemeleri** sekmesi iki alt sekme oluşur:

1. **Framework** hedef çerçeveyi oluşturan tüm derlemeleri listeler.

    Windows 8.x mağazası uygulamaları için projeleri içeren tüm hedeflenen derlemelerde başvuruları [!INCLUDE[net_win8_profile](../ide/includes/net_win8_profile_md.md)] varsayılan olarak proje oluşturma. Yönetilen projelerinde salt okunur bir düğümü altında **başvuruları** klasöründe **Çözüm Gezgini** tüm Framework başvuru gösterir. Buna göre Framework sekmesini olmaz Framework derlemelerden birini numaralandırmak ve bunun yerine aşağıdaki iletiyi görüntüler: "tüm Framework derlemeler zaten başvurulur. Lütfen Nesne Tarayıcısı Framework başvurularında keşfetmek için kullanın." Masaüstü projeleri için **Framework** sekmesini hedef çerçeveyi derlemelerden numaralandırır ve kullanıcının uygulama gerektiriyor başvurular eklemeniz gerekir.

2. **Uzantıları** bileşenleri ve denetimleri harici satıcıları hedef çerçeveyi genişletmek için geliştirilmiş tüm derlemeleri listeler. Kullanıcı uygulamasının amacına bağlı olarak, bu derlemelere gerek duyulabilir.

   **Uzantıları** aşağıdaki konumlarda kayıtlı derlemeleri numaralandırarak doldurulur:

   32-bit makine:
   - Arasına\[hedef Framework tanımlayıcısı] \v [hedef Framework sürümü] \AssemblyFoldersEx\[UserComponentName]\@varsayılan [derlemelerin konumunu Disk] =
   - HKEY_LOCAL_MACHINE\Software\Microsoft\[hedef Framework tanımlayıcısı] \v [hedef Framework sürümü] \AssemblyFoldersEx\[UserComponentName]\@varsayılan [derlemelerin konumunu Disk] =

   64-bit makine:
   - HKEY_CURRENT_USER\SOFTWARE\Wow6432Node\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]
   - HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies] And older versions of the [Target Framework Identifier]

   Örneğin, bir projeniz .NET Framework 4 32-bit makine üzerindeki hedefliyorsa **uzantıları** altında kayıtlı derlemeleri Numaralandırılacak _\Microsoft\\. NETFramework\v4.0\AssemblyFoldersEx\\_, _\Microsoft\\. NETFramework\v3.5\AssemblyFoldersEx\\_, _\Microsoft\\. NETFramework\v3.0\AssemblyFoldersEx\\_, ve _\Microsoft\\. NETFramework\v2.0\AssemblyFoldersEx\\_.

Listedeki bazı bileşenler, projeniz .NET Framework sürümüne bağlı olarak görünmeyebilir. Bu aşağıdaki durumlarda oluşabilir:

- Yeni bir .NET Framework sürümü kullanan bir bileşeni .NET Framework'ün önceki bir sürümünü hedefleyen bir projede ile uyumlu değil.

    Bir proje için hedef .NET Framework sürümü değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

- Kullanan bir bileşen [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] hedefleyen bir projede ile uyumsuz [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)].

    Bazı projeleri hedef yeni bir uygulama oluşturduğunuzda [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)] varsayılan olarak.

- Bunun yapılması, derleme hataları neden olabileceğinden aynı çözümde başka bir projeye çıkışları dosyası başvuruları ekleme kaçınmalısınız. Bunun yerine, kullanın **projeleri** sekmesinde **Başvuru Ekle** proje proje başvuruları oluşturmak için iletişim kutusu. Bu takım geliştirme projelerinizde oluşturduğunuz sınıf kitaplıkları daha iyi yönetim etkinleştirerek kolaylaştırır. Daha fazla bilgi için bkz: [başvuruları bozuk sorun giderme](../ide/troubleshooting-broken-references.md).

> [!NOTE]
> Visual Studio 2015 veya sonraki sürümlerde, bir dosya başvurusu proje başvurusu yerine hedef bir proje .NET Framework sürüm 4.5 veya sonraki sürümü olan ve diğer projenin hedef sürüm 2, 3, 3.5 veya 4.0 sürümünü ise oluşturulur.

### <a name="to-display-an-assembly-in-the-add-reference-dialog-box"></a>Bir derleme başvurusu Ekle iletişim kutusunda görüntülemek için

- Taşıma veya derleme aşağıdaki konumlardan birine kopyalayın:

    - Geçerli proje dizini. (Bu derlemeler kullanarak bulabilirsiniz **Gözat** sekmesi.)

    - Diğer aynı çözüme proje dizinlerde. (Bu derlemeler kullanarak bulabilirsiniz **projeleri** sekmesi.)

    \- veya -

- Görüntülenecek derlemelerin konumunu belirten bir kayıt defteri anahtarını ayarlayın:

   Bir 32 bit işletim sistemi için aşağıdaki kayıt defteri anahtarlarından birini ekleyin.

   - [Arasına\\. NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@= "*AssemblyLocation*"

   - [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@= "*AssemblyLocation*"

   Bir 64-bit işletim sistemi için aşağıdaki kayıt defteri anahtarlarından birinin 32-bit kayıt defteri kovanında ekleyin.

   - [HKEY_CURRENT_USER\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@="*AssemblyLocation*"

   - [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@="*AssemblyLocation*"

   *VersionMinimum* geçerli en düşük .NET Framework sürümü. Varsa *VersionMinimum* v3.0, AssemblyFoldersEx içinde belirtilen klasörleri uygulamadığınız projelerine hedefleyen .NET Framework 3.0 ve üstü.

   *AssemblyLocation* görünmesini istediğiniz derlemeleri dizin **Başvuru Ekle** iletişim kutusunda *C:\MyAssemblies\\*.

   HKEY_LOCAL_MACHINE düğümü altındaki kayıt defteri anahtarı oluşturulurken belirtilen konumda derlemelerde görmek tüm kullanıcıların sağlar **Başvuru Ekle** iletişim kutusu. HKEY_CURRENT_USER düğümü altındaki kayıt defteri anahtarı oluşturma, yalnızca geçerli kullanıcının ayarını etkiler.

   Açık **Başvuru Ekle** yeniden iletişim kutusu. Derlemeleri görünmesi gereken **.NET** sekmesi. Yapmazsanız, derlemeler bulunduğu olduğundan emin olun belirtilen *AssemblyLocation* dizini, Visual Studio'yu yeniden başlatın ve yeniden deneyin.

## <a name="projects-tab"></a>Projeler sekmesi

**Projeleri** sekmesi geçerli çözümde uyumlu tüm projeleri listeler **çözüm** alt sekmesi.

Bir proje, farklı bir .NET Framework sürümünü hedef alan başka bir projeye başvuruda bulunabilir. Örneğin, hedefleyen bir proje oluşturabilirsiniz [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] ancak için .NET Framework 2 yerleşik olan bir derleme başvuruyor. Ancak, .NET Framework 2 proje başvuramaz bir [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] projesi. Daha fazla bilgi için bkz: [çoklu sürüm desteğine genel bakış](../ide/visual-studio-multi-targeting-overview.md).

Hedefleyen bir projede [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] hedefleyen bir projede ile uyumsuz [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)].

Bir proje hedefleri .NET Framework 4 ve başka bir projeye önceki bir sürümünü hedefliyorsa dosya başvurusu yerine proje başvurusu oluşturulur.

Hedefleyen bir projede [!INCLUDE[net_win8_profile](../ide/includes/net_win8_profile_md.md)] .NET Framework hedefleyen bir projede bir proje başvurusu eklenemiyor tersi.

## <a name="windows-tab"></a>Windows sekmesi

**Windows** sekmesi hangi Windows işletim sistemleri çalıştıran platformlarda özgü tüm SDK'ları listeler.

Visual Studio'da bir WinMD dosyasını iki şekilde oluşturabilirsiniz:

- **Windows 8.x mağazası uygulaması projeleri yönetilen**: Windows 8.x mağazası uygulaması projeleri çıktı WinMD ikili dosyaları ayarlayarak **proje özelliklerini** > **çıktı türü = WinMD dosyası**. WinMD dosya adı, içinde varolan tüm alan adlarının üst küme alan adı olmalıdır. Örneğin, bir proje isim oluşuyorsa `A.B` ve `A.B.C`, kendi outputted WinMD için olası adları *A.winmd* ve *A.B.winmd*. Bir kullanıcı girerse bir **proje özelliklerini** > **derleme adı** veya **proje özelliklerini** > **Namespace**ayrık ad alanları projeye kümesinden değer veya bir projede hiç üst ad alanı, bir derleme uyarı oluşturulduğu: 'A.winmd' Bu derleme için bir geçerli .winmd dosya adı değil. Bir Windows Meta Veri dosyası içindeki tüm türler, dosya adının bir alt ad alanında mevcut olmalıdır. Dosya adı bir alt ad alanında var olmayan türleri çalışma zamanında bulunması mümkün olmayacaktır. Bu derlemede en küçük ortak ad alanıdır `CSWSClassLibrary1`. Bir masaüstü Visual Basic veya C# projesinde yalnızca birinci taraf WinMDs bilinen Windows 8 SDK'ları kullanarak, oluşturulan WinMDs tüketebileceği ve WinMDs oluşturulamıyor.

- **Windows 8.x mağazası uygulaması yerel projeleri**: meta verileri yalnızca yerel bir WinMD dosyası oluşur. Uygulaması ayrı bir DLL dosyası içinde var olur. Bir oluşturabilirsiniz yerel ikili dosyaları Windows çalışma zamanı bileşeni proje şablonu seçerek **yeni proje** iletişim kutusu ya da boş bir proje başlatarak ve WinMD dosyası oluşturmak için proje özelliklerini değiştirme. Proje kopuk ad alanlarından oluşuyorsa, bir yapı hatası kullanıcıya ad alanlarını birleştirmesi veya MSMerge aracını çalıştırması gerektiğini söyler.

**Windows** sekmesinde iki alt grupları oluşur.

### <a name="core-subgroup"></a>Çekirdek alt

**Çekirdek** alt hedeflenen Windows sürümü için SDK'sındaki WinMDs (Windows çalışma zamanı öğeleri için) tüm listeler.

Windows 8.x mağazası uygulaması projeleri proje oluşturma sırasında varsayılan olarak tüm Windows 8 SDK'sındaki WinMDs başvurular içeriyor. Yönetilen projelerinde salt okunur bir düğümü altında **başvuruları** klasöründe **Çözüm Gezgini** tüm Windows 8 SDK referansı gösterir. Buna göre **çekirdek** alt gruba **başvuru Yöneticisi** Windows 8 SDK derlemelerden birini listeleme kullanmazsınız ve bunun yerine bir ileti görüntüler: "Windows SDK zaten başvuruyor. Lütfen nesne tarayıcısı Windows SDK'sı içindeki başvuruların keşfetmek için kullanın."

Masaüstü projelerinde **çekirdek** alt grup, varsayılan olarak görünmüyor. Windows çalışma zamanı proje düğümünün kısayol menüsünü açarak ekleyebilirsiniz seçme **projeyi**, aşağıdaki kod parçacığında ekleme ve projeyi yeniden açmayı (proje düğümüne seçin **projeyiyenidenyükle**). Ne zaman çağırmayı **başvuru Yöneticisi** iletişim kutusu, **çekirdek** alt görüntülenir.

```xml
<PropertyGroup>
  <TargetPlatformVersion>8.0</TargetPlatformVersion>
</PropertyGroup>
```

Seçtiğinizden emin olun **Windows** bu alt grup onay kutusu. Bundan sonra Windows Çalışma Zamanı öğelerini kullanabilmeniz gerekir. Ancak, sonra da eklemek istersiniz <xref:System.Runtime>, Windows çalışma zamanı bazı standart sınıflar ve arabirimler, gibi tanımlayan içinde <xref:System.Collections.IEnumerable>, Windows çalışma zamanı kitaplıkları kullanılır. Nasıl ekleneceği hakkında bilgi için <xref:System.Runtime>, bkz: [yönetilen Masaüstü uygulamaları ve Windows çalışma zamanı](http://msdn.microsoft.com/library/windows/apps/jj856306.aspx#consuming_standard_windows_runtime_types).

### <a name="extensions-subgroup"></a>Uzantıları alt

**Uzantıları** kullanıcı hedeflenen Windows platformu genişletmek SDK'ları listeler. Bu sekme, Windows 8.x mağazası uygulaması projeleri için yalnızca görüntülenir. Yalnızca birinci taraf .winmd dosyaları tüketebildiğinden Masaüstü projeleri bu sekme göstermeyecektir.

SDK, Visual Studio'nun tek bir bileşen olarak kabul ettiği dosyalar topluluğudur. İçinde **uzantıları** sekmesinde, projeye, uygulama SDK'ları **başvuru Yöneticisi** iletişim kutusu çağrıldığı tek girişleri olarak listelenir. Bir projeye eklendiğinde, tüm SDK içeriği tüketilen Visual Studio tarafından sağlayacak şekilde kullanıcı IntelliSense, araç kutusu, tasarımcıları, SDK içeriğini yararlanmak için gereken diğer işlemleri yapmanıza gerek olmayan nesne tarayıcısı, yapı, hata ayıklama ve paketleme dağıtım. SDK'görüntüleme hakkında bilgi için **uzantıları** sekmesinde bkz [bir yazılım geliştirme seti oluşturma](../extensibility/creating-a-software-development-kit.md).

> [!NOTE]
> Bir proje üzerinde başka bir SDK bağlıdır bir SDK başvuruyorsa, Visual Studio kullanıcı el ile ikinci SDK'sına bir başvuru ekler sürece ikinci SDK tüketmezsiniz. Ne zaman bir kullanıcının seçtiği bir SDK üzerinde **uzantıları** sekmesinde **başvuru Yöneticisi** iletişim kutusu yalnızca adını ve SDK sürümü aynı zamanda tüm SDK adını listeleyerek SDK bağımlılığı tanımlamak kullanıcı yardımcı olur Ayrıntılar bölmesinde bağımlılıkları. Varsa bir kullanıcı bağımlılıkları fark etmez ve yalnızca SDK, MSBuild bağımlılıkları eklemek için kullanıcıyı uyarır ekler.

Proje türü desteklemiyorsa **uzantıları**, sekmesi içinde görünmüyor **başvuru Yöneticisi** iletişim kutusu.

## <a name="com-tab"></a>COM sekmesi

**COM** sekmesi başvurmak için kullanılabilir tüm COM bileşenlerini listeler. Dahili bildirim içeren kayıtlı bir COM DLL öğesine başvuru eklemek isterseniz, önce DLL kaydını silin. Aksi takdirde, Visual Studio derleme başvurusu bir ActiveX denetimini yerel DLL olarak olarak ekler.

Proje türü desteklemiyorsa **COM**, sekmesi içinde görünmüyor **başvuru Yöneticisi** iletişim kutusu.

## <a name="browse-button"></a>Gözat düğmesi

Kullanabileceğiniz **Gözat** bir bileşen için dosya sistemindeki gözatmak için düğmeyi.

Bir proje, farklı bir .NET Framework sürümünü hedef alan başka bir bileşene başvuruda bulunabilir. Örneğin, bir uygulama .NET Framework 4.7 hedef .NET Framework 4 hedefleyen bir bileşen başvuruda bulunan oluşturabilirsiniz. Daha fazla bilgi için bkz: [çoklu sürüm desteğine genel bakış](../ide/visual-studio-multi-targeting-overview.md).

Aynı çözümdeki başka bir projenin çıktılarına dosya başvuruları eklemekten kaçınmalısınız; bu taktik derleme hatalarına neden olabilir. Bunun yerine, kullanın **çözüm** sekmesinde **başvuru Yöneticisi** proje proje başvuruları oluşturmak için iletişim kutusu. Bu takım geliştirme projelerinizde oluşturduğunuz sınıf kitaplıkları daha iyi yönetim etkinleştirerek kolaylaştırır. Daha fazla bilgi için bkz: [başvuruları bozuk sorun giderme](../ide/troubleshooting-broken-references.md).

Bir SDK göz atın ve projenize ekleyin. Yalnızca bir dosyaya (örneğin, bir derleme veya .winmd) göz atabilir ve bu dosyayı projenize ekleyebilirsiniz.

Bir WinMD dosyası başvuru yaparken olan beklenen düzeni *FileName*.winmd, *FileName*.dll, ve *FileName*.pri dosyaları tüm yerleştirilir diğer. Aşağıdaki senaryolarda bir WinMD'ye başvuruda bulunursanız, proje çıkış dizinine eksik bir dosya kümesi kopyalanır ve sonuç olarak, derleme ve çalışma zamanı hataları meydana gelir.

- **Yerel bileşen**: bir yerel her ayrık ad alanları kümesi için bir WinMD ve uygulanması oluşan bir DLL oluşturacaksınız. WinMD'ler ayrı adlara sahip olur. Bu yerel bileşen dosya başvururken MSBuild dissimilarly adlandırılmış WinMDs bir bileşen olun tanımaz. Sonuç olarak, yalnızca aynı adlı *FileName*.dll ve *FileName*.winmd kopyalanacak ve çalışma zamanı hataları oluşur. Bu sorunu geçici bir çözümle aşmak için bir Uzantı SDK oluşturun. Daha fazla bilgi için bkz: [bir yazılım geliştirme seti oluşturmak](../extensibility/creating-a-software-development-kit.md).

- **Denetimlerin tüketmesini**: en az bir XAML denetimi oluşan bir *FileName*.winmd, *FileName*.dll, *FileName*.pri, *XamlName* .xaml ve bir *görüntü adı*.jpg. Proje yapılandırıldığında, projenin çıktı dizinine kopyalanmış ve yalnızca dosya başvuru ile ilişkili kaynak dosyaları vermeyecektir *FileName*.winmd, *FileName*.dll ve *FileName*.pri kopyalanacak. Bir derleme hatası kullanıcıyı bilgilendirmek üzere kaydedilir, kaynakları *XamlName*.xaml ve *görüntü adı*.jpg eksik. Başarılı olması için, kullanıcının bu kaynak dosyaları oluşturma ve hata ayıklama/çalışma zamanı için proje çıkış dizinine el ile kopyalaması gerekir. Bu sorunu çözmek için ya da bir uzantı SDK içindeki adımları izleyerek oluşturun [bir yazılım geliştirme seti oluşturma](../extensibility/creating-a-software-development-kit.md) veya aşağıdaki özelliği eklemek için proje dosyasını düzenleyin:

    ```xml
    <PropertyGroup>
       <GenerateLibraryOutput>True</GenerateLibraryOutput>
    </PropertyGroup>
    ```

    > [!NOTE]
    > Özelliği eklerseniz, yapı daha yavaş çalışabilir.

## <a name="recent"></a>En Son

Derlemeler, COM, Windows ve Destek göz atma bir **son** projelerine yakın zamanda eklenen bileşenlerin listesini numaralandırır sekmesi.

## <a name="search"></a>Ara

Arama çubuğuna **başvuru Yöneticisi** odakta sekmesi üzerinden iletişim kutusu çalışır. Örneğin, bir kullanıcı arama çubuğunda sırasında "Sistem" yazdığında **çözüm** sekmesini odakta, "Sistem" içeren bir proje adı çözüm oluşur sürece arama tüm sonuçları döndüren olmaz.

## <a name="see-also"></a>Ayrıca bkz.

- [Bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md)
