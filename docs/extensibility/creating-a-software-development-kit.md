---
title: "Bir yazılım geliştirme seti oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8496afb4-1573-4585-ac67-c3d58b568a12
caps.latest.revision: "54"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4ea17b02cfa2e987c4a3c02acddf838001b4ae2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-software-development-kit"></a>Bir yazılım geliştirme seti oluşturma
Bir yazılım geliştirme seti (SDK), Visual Studio'da tek bir öğe olarak başvurabilir API'leri koleksiyonudur. **Başvuru Yöneticisi** iletişim kutusu projeye uygun olan tüm SDK'ları listeler. Bir projeye bir SDK eklediğinizde API'lerini Visual Studio'da kullanılabilir.  
  
 SDK'ları iki tür vardır:  
  
-   Platform SDK'ları bir platform için uygulamalarını geliştirmek için zorunlu bileşenleridir. Örneğin, [!INCLUDE[win81](../debugger/includes/win81_md.md)] SDK geliştirmek için gerekli olduğunu [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamalar.  
  
-   Uzantı SDK'ları bir platform genişletir, ancak bu platform için uygulamalarını geliştirmek için zorunlu olmayan isteğe bağlı bileşenleridir.  
  
 Aşağıdaki bölümlerde genel altyapı SDK'ları ve platform SDK oluşturma ve uzantı SDK.  
  
-   [Platform SDK'ları](#PlatformSDKs)  
  
-   [Uzantı SDK'ları](#ExtensionSDKs)  
  
##  <a name="PlatformSDKs"></a>Platform SDK'ları  
 Platform SDK'ları bir platform için uygulamalarını geliştirmek için gereklidir. Örneğin, [!INCLUDE[win81](../debugger/includes/win81_md.md)] SDK için uygulama geliştirmek için gerekli olduğunu [!INCLUDE[win81](../debugger/includes/win81_md.md)].  
  
### <a name="installation"></a>Yükleme  
 Tüm platform SDK'ları HKLM\Software\Microsoft\Microsoft SDK'ları sırasında yüklenecek\\[TPI] \v [TPV]\\ @InstallationFolder [SDK kök] =. Buna göre [!INCLUDE[win81](../debugger/includes/win81_md.md)] SDK HKLM\Software\Microsoft\Microsoft SDKs\Windows\v8.1 sırasında yüklenir.  
  
### <a name="layout"></a>Düzen  
 Platform SDK'ları aşağıdaki düzeni olacaktır:  
  
```  
\[InstallationFolder root]  
            SDKManifest.xml  
            \References  
                  \[config]  
                        \[arch]  
            \DesignTime  
                  \[config]  
                        \[arch]  
```  
  
|Düğüm|Açıklama|  
|----------|-----------------|  
|Başvurular klasörü|Karşı kodlanmış API'leri içeren ikili dosyalarını içerir. Bu Windows meta veri (WinMD) dosyaları veya derlemeler içerebilir.|  
|Programatik klasörü|Yalnızca öncesi-run/hata ayıklama sırasında gereken dosyaları içerir. Bu XML belgeleri, kitaplıklar, üst bilgiler, araç kutusu tasarım zamanı ikili dosyaları, MSBuild yapıları ve benzeri içerebilir<br /><br /> XML belgeleri ideal olarak, \DesignTime klasöründe konulabilir ancak XML belgeleri başvuruları için Visual Studio başvurusu dosyasında yanında yerleştirilecek devam eder. Örneğin, XML belge için bir başvuru \References\\[config]\\[arch]\sample.dll \References olacaktır\\[config]\\[arch]\sample.xml ve bu belge yerelleştirilmiş sürümünü \Referencesolacak\\[config]\\[arch]\\[locale]\sample.xml.|  
|Yapılandırma klasörü|Yalnızca üç klasör olabilir: hata ayıklama, perakende ve CommonConfiguration. SDK yazarlar SDK dosyaları aynı kümesini, SDK tüketici hedeflediğini yapılandırma bağımsız olarak kullanılması dosyalarına CommonConfiguration altında koyabilirsiniz.|  
|Mimari klasörü|Herhangi bir desteklenen mimari klasöründe bulunabilir. Visual Studio aşağıdaki mimariler destekler: x86, x64, ARM ve nötr. Not: Win32 için x86 eşler ve AnyCPU için nötr eşler.<br /><br /> MSBuild için Platform SDK'ları yalnızca \CommonConfiguration\neutral altında arar.|  
|SDKManifest.xml|Bu dosya, Visual Studio SDK'yı nasıl kullanmak tanımlar. SDK bildirim bakabilir [!INCLUDE[win81](../debugger/includes/win81_md.md)]:<br /><br /> `<FileList             DisplayName = "Windows"             PlatformIdentity = "Windows, version=8.1"             TargetFramework = ".NET for Windows Store apps, version=v4.5.1; .NET Framework, version=v4.5.1"             MinVSVersion = "14.0">              <File Reference = "Windows.winmd">                <ToolboxItems VSCategory = "Toolbox.Default" />             </File> </FileList>`<br /><br /> **DisplayName:** Nesne Tarayıcısı Gözat listede görüntüler değeri.<br /><br /> **PlatformIdentity:** bu öznitelik varlığını Visual Studio ve MSBuild SDK'sı bir platform SDK'si olduğunu ve ondan eklenen başvuruları kopyalanan döndürmemelidir yerel olarak bildirir.<br /><br /> **TargetFramework:** bu öznitelik, yalnızca hedefleyen projelerde bu değeri belirtildiği gibi aynı çerçeveleri emin olmak için Visual Studio tarafından kullanılan öznitelik SDK tüketebileceği.<br /><br /> **MinVSVersion:** bu öznitelik yalnızca uygulayan SDK'lar kullanmak için Visual Studio tarafından kullanılır.<br /><br /> **Başvuru:** bu öznitelik yalnızca denetimleri içeren bu başvuruları için belirtilmesi gerekir. Bir başvuru denetimleri içerip içermediğini belirtme hakkında daha fazla bilgi için aşağıya bakın.|  
  
##  <a name="ExtensionSDKs"></a>Uzantı SDK'ları  
 Aşağıdaki bölümlerde, uzantı SDK dağıtmak için yapmanız gerekenler açıklanmaktadır.  
  
### <a name="installation"></a>Yükleme  
 Uzantı SDK'ları tüm kullanıcılar için veya belirli bir kullanıcı için bir kayıt defteri anahtarı belirtmeden yüklenebilir. Tüm kullanıcılar için bir SDK yüklemek için aşağıdaki yola kullanın:  
  
 `%Program Files%\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs`  
  
 Bir kullanıcıya özel yükleme için aşağıdaki yola kullanın:  
  
 `%USERPROFILE%\AppData\Local\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs`  
  
 Farklı bir konum kullanmak istiyorsanız, ikisinden birini yapmanız gerekir:  
  
1.  Bir kayıt defteri anahtarında belirtin:  
  
     `HKLM\Software\Microsoft\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs\<SDKName>\<SDKVersion>\`  
  
     ve değerine sahip bir (varsayılan) alt anahtar ekleyin `<path to SDK><SDKName><SDKVersion>`.  
  
2.  MSBuild özellik ekleme `SDKReferenceDirectoryRoot` proje dosyanıza. Bu özellik uzantısı başvuru yapmak istediğinizi SDK'ları bulunduğu dizinlerin noktalı virgülle ayrılmış listesini değerdir.  
  
### <a name="installation-layout"></a>Yükleme düzeni  
 Uzantı SDK'ları aşağıdaki yükleme düzeni vardır:  
  
```  
\<ExtensionSDKs root>  
           \<SDKName>  
                 \<SDKVersion>  
                        SDKManifest.xml  
                        \References  
                              \<config>  
                                    \<arch>  
                        \Redist  
                              \<config>  
                                    \<arch>  
                        \DesignTime  
                               \<config>  
                                     \<arch>  
  
```  
  
1.  \\< SDKName\>\\< SDKVersion\>: adını ve SDK türetilen yolu karşılık gelen klasör adlarında SDK kök uzantısı'nın sürümü. MSBuild SDK diskte bulmak için bu kimliği kullanır ve Visual Studio görüntüler bu kimliğinde **özellikleri** penceresi ve **başvuru Yöneticisi** iletişim.  
  
2.  Başvurular klasörünü: API'leri içeren ikili dosyaları. Bunlar Windows meta veri (WinMD) dosyaları veya derlemeleri olabilir.  
  
3.  Redist klasörü: çalışma zamanı/hata ayıklama için gerekli ve kullanıcının uygulama bir parçası olarak paketlenmiş dosyaları. Tüm ikili dosyaları \redist yerleştirilmesi gerektiğini\\< config\>\\< arch\>, ve ikili adları benzersizlik emin olmak için aşağıdaki biçimde olmalıdır:  **\<şirket >.\< Ürün >. \<amacı >. \<uzantısı >**. Örneğin, Microsoft.Cpp.Build.dll. Dosya adlarından diğer SDK (örneğin, javascript, css, PRI, xaml, png ve jpg dosyaları) ile çakışabilir adlara sahip tüm dosyaları \redist altında yerleştirilmelidir\\< config\>\\< arch\> \\< sdkname\>\ XAML ile ilişkili olan dosyaları dışında denetler. Bu dosyaları \redist altında yerleştirilmelidir\\< config\>\\< arch\>\\< componentname\>\\.  
  
4.  Programatik klasörü: yalnızca öncesi-run/hata ayıklama sırasında gerekli olan dosyaların zaman ve kullanıcının uygulama bir parçası olarak paketlenmiş döndürmemelidir. Bunlar, XML belgeleri, kitaplıklar, üst bilgiler, araç kutusu tasarım zamanı ikili dosyaları, MSBuild yapıları ve benzeri olabilir. Yerel bir proje tüketimi bulunmalıdır kullanılmaya SDK bir *SDKName*.props dosya. Bu dosya türü bir örneğini gösterir.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <ExecutablePath>C:\Temp\ExecutablePath;$(ExecutablePath)</ExecutablePath>  
        <IncludePath>$(FrameworkSDKRoot)\..\v8.1\ExtensionSDKs\cppimagingsdk\1.0\DesignTime\CommonConfiguration\Neutral\include;$(IncludePath)</IncludePath>  
        <AssemblyReferencePath>C:\Temp\AssemblyReferencePath;(AssemblyReferencePath)</AssemblyReferencePath>  
        <LibraryPath>$(FrameworkSDKRoot)\..\v8.1\ExtensionSDKs\cppimagingsdk\1.0\DesignTime\Debug\ARM;$(LibraryPath)</LibraryPath>  
        <SourcePath>C:\Temp\SourcePath\X64;$(SourcePath)</SourcePath>  
        <ExcludePath>C:\Temp\ExcludePath\X64;$(ExcludePath)</ExcludePath>  
        <_PropertySheetDisplayName>DevILSDK, 1.0</_PropertySheetDisplayName>  
      </PropertyGroup>  
    </Project>  
  
    ```  
  
     XML başvuru belgeleri başvuru dosyasını yerleştirilir. Örneğin, başvuru için XML belgesi **\References\\< config\>\\< arch\>\sample.dll** derleme **\References\\ < config\>\\< arch\>\sample.xml**, ve bu belge yerelleştirilmiş sürümü **\References\\< config\>\\< arch\>\\< yerel ayar\>\sample.xml**.  
  
5.  Yapılandırma klasörünü: üç alt klasörleri: hata ayıklama, perakende ve CommonConfiguration. SDK dosyaları aynı kümesini, SDK tüketici tarafından hedeflenen yapılandırma bağımsız olarak kullanılması zaman SDK yazarlar dosyalarına CommonConfiguration altında yerleştirebilirsiniz.  
  
6.  Mimari klasörü: aşağıdaki mimariler desteklenir: x86, x64, ARM, nötr. Win32 için x86 eşler ve AnyCPU için nötr eşler.  
  
### <a name="sdkmanifestxml"></a>SDKManifest.xml  
 Bu dosya, Visual Studio SDK'yı nasıl kullanmak tanımlar. Bir örnek verilmiştir.  
  
```  
<FileList>  
DisplayName = "My SDK"  
ProductFamilyName = "My SDKs"  
TargetFramework = ".NETCore, version=v4.5.1; .NETFramework, version=v4.5.1"  
MinVSVersion = "14.0"  
MaxPlatformVersion = "8.1"  
AppliesTo = "WindowsAppContainer + WindowsXAML"  
SupportPrefer32Bit = "True"  
SupportedArchitectures = "x86;x64;ARM"  
SupportsMultipleVersions = "Error"  
CopyRedistToSubDirectory = "."  
DependsOn = "SDKB, version=2.0"  
MoreInfo = "http://msdn.microsoft.com/MySDK">  
<File Reference = "MySDK.Sprint.winmd" Implementation = "XNASprintImpl.dll">  
<Registration Type = "Flipper" Implementation = "XNASprintFlipperImpl.dll" />  
<Registration Type = "Flexer" Implementation = "XNASprintFlexerImpl.dll" />  
<ToolboxItems VSCategory = "Toolbox.Default" />  
</File>  
</FileList>  
```  
  
 Aşağıdaki listede dosya öğelerini sağlar.  
  
1.  DisplayName: başvuru Yöneticisi'ni, Çözüm Gezgini'nde, Nesne Tarayıcısı ve kullanıcı arabiriminde başka konumlara Visual Studio için görünen değeri.  
  
2.  ProductFamilyName: Genel SDK ürün adı. Örneğin, [!INCLUDE[winjs_long](../debugger/includes/winjs_long_md.md)] SDK SDK ürün ailesi, "Microsoft.WinJS" aynı aileye aitse "Microsoft.WinJS.1.0" ve "Microsoft.WinJS.2.0" adlı. Visual Studio ve MSBuild, bağlantıyı kurmak bu öznitelik sağlar. Bu öznitelik yoksa, SDK adı ürün ailesi adı olarak kullanılır.  
  
3.  FrameworkIdentity: Bu özniteliğin değeri alıcı uygulamanın bildirim içine konur bir veya daha fazla Windows bileşeni kitaplıkları bir bağımlılık belirtir. Bu öznitelik, yalnızca Windows bileşeni kitaplıkları için geçerlidir.  
  
4.  TargetFramework: başvuru Yöneticisi'ni ve araç kullanılabilir SDK'ları belirtir. Bu örneğin hedef framework adları noktalı virgülle ayrılmış listesi olduğu ".NET Framework, sürüm = v2.0; .NET Framework, sürüm v4.5.1 =". Aynı hedef framework'ün birçok sürümlerini belirtilirse, başvuru Yöneticisi amacıyla filtreleme için belirtilen en düşük sürümü kullanır. Örneğin, varsa ".NET Framework, sürüm = v2.0; .NET Framework, sürüm v4.5.1 =" belirtilirse, başvuru Yöneticisi'ni kullanır ".NET Framework, sürüm v2.0 =". Belirli bir hedef framework profili belirtilirse, yalnızca o profili başvuru Yöneticisi tarafından filtreleme amaçlı olarak kullanılır. Örneğin, "Silverlight, sürüm v4.0, profil = WindowsPhone =" belirtilirse, başvuru Yöneticisi filtreler yalnızca Windows Phone profilinde; tam Silverlight 4.0 Framework hedefleme proje başvuru Yöneticisi'nde SDK görmez.  
  
5.  MinVSVersion: en düşük Visual Studio sürümü.  
  
6.  MaxPlatformVerson: En fazla hedef platform sürümü üzerinde uzantısı SDK çalışmaz platform sürümleri belirtmek için kullanılmalıdır. Örneğin, Microsoft Visual C++ çalışma zamanı paketi v11.0 yalnızca Windows 8 projeleri tarafından başvurulan. Bu nedenle, Windows 8 projenin MaxPlatformVersion 8.0 ' dir. Bu başvuru Yöneticisi Windows 8.1 projesi için Microsoft Visual C++ çalışma zamanı paketi filtreleri ve MSBuild bir hata oluşturduğunda anlamına gelir, bir [!INCLUDE[win81](../debugger/includes/win81_md.md)] proje başvurur. Not: Bu öğe itibaren desteklenir [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)].  
  
7.  AppliesTo: başvuru Yöneticisi'nde kullanılabilir olan geçerli Visual Studio Proje türleri belirterek SDK'ları belirtir. Dokuz değerlerini tanınan: WindowsAppContainer, VisualC, VB, CSharp, WindowsXAML, JavaScript, yönetilen ve yerel. SDK Yazar kullanabilirsiniz ve ("+'), ya da ("&#124;"), değil ("! ") tam olarak uygulamak için SDK proje türleri kapsamını belirtmek için işleçler.  
  
     WindowsAppContainer tanımlayan projeleri için [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamalar.  
  
8.  SupportPrefer32Bit: "True" değerleri desteklenir ve "False". Varsayılan değer "True" dir. Değer "False" olarak ayarlanırsa, MSBuild için bir hata döndürür [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] projeleri (veya Masaüstü projeleri için bir uyarı) SDK başvuran projesini etkin Prefer32Bit varsa. Prefer32Bit hakkında daha fazla bilgi için bkz: [derleme sayfası, Proje Tasarımcısı (C#)](../ide/reference/build-page-project-designer-csharp.md) veya [derleme sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/compile-page-project-designer-visual-basic.md).  
  
9. SupportedArchitectures: noktalı virgülle ayrılmış listesini mimarileri SDK destekler. Hedeflenen SDK mimarisi Süren projesinde desteklenmiyorsa MSBuild bir uyarı görüntüler. Bu özniteliği belirtilmezse, MSBuild hiçbir zaman bu tür bir uyarı görüntüler.  
  
10. SupportsMultipleVersions: Bu öznitelik ayarlanırsa **hata** veya **uyarı**, MSBuild gösterir aynı proje SDK ailesini birden fazla sürümünü başvuramaz. Bu öznitelik yok ya da ayarlanır **izin**, MSBuild, bu tür hata veya uyarı görüntülemek değil.  
  
11. AppX: disk üzerinde Windows bileşeni kitaplığı için uygulama paketleri yolunu belirtir. Bu değer, yerel hata ayıklama sırasında Windows bileşeni kitaplığı kayıt bileşenine geçirilir. Dosya adı için adlandırma kuralı  **\<şirket >.\< Ürün >. \<Mimarisi >. \<Yapılandırma >. \<Sürüm > .appx**. Windows Bileşen Kitaplığı'na uygulamazsanız yapılandırması ve mimari öznitelik adı ve öznitelik değeri isteğe bağlıdır. Bu değer yalnızca Windows bileşeni kitaplıkları için geçerlidir.  
  
12. CopyRedistToSubDirectory: Burada \redist klasör altındaki dosyalar uygulama paket köküne göre kopyalanmalıdır belirtir (diğer bir deyişle, **paketi konumu** uygulama Paket Oluştur Sihirbazı'nda seçilen) ve çalışma zamanı düzeni kök. Uygulama paketi ve F5 düzeni kökündeki varsayılan konumdur.  
  
13. DependsOn: Bu SDK bağımlı olduğu SDK'ları tanımlayın SDK kimliklerinin bir listesi. Bu öznitelik başvuru Yöneticisi'nin ayrıntılar bölmesinde görüntülenir.  
  
14. Daha fazla bilgi: Yardım ve daha fazla bilgi sağlayan web sayfası URL'si. Daha fazla bilgi bağlantısına başvuru Yöneticisi'nin sağ bölmede, bu değer kullanılır.  
  
15. Kayıt türü: uygulama bildiriminde WinMD kayıt belirtir ve karşılık gelen uygulama DLL olan yerel WinMD için gereklidir.  
  
16. Dosya başvurusu: yerel WinMDs denetimleri içeren ya da yalnızca bu başvuruları için belirtilen. Bir başvuru denetimleri içerip içermediğini belirtme hakkında daha fazla bilgi için bkz: [araç kutusu öğelerini konumu belirtme](#ToolboxItems) aşağıda.  
  
##  <a name="ToolboxItems"></a>Araç kutusu öğelerini konumunu belirtme  
 ToolBoxItems öğesi SDKManifest.xml şemasının platform ve uzantı SDK'ları kategori ve araç kutusu öğelerini konumunu belirtir. Aşağıdaki örnekler, farklı konumlar belirtebilirsiniz gösterilmektedir. Bu, WinMD veya DLL başvurularını geçerlidir.  
  
1.  Denetimleri araç varsayılan kategorisinde yerleştirin.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Toolbox.Default"/>       
    </File>  
    ```  
  
2.  Belirli kategori adı altında denetimleri yerleştirin.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory= "MyCategoryName"/>  
    </File>  
    ```  
  
3.  Denetimleri belirli kategori adları altına yerleştirin.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Graph">  
        <ToolboxItems/>  
        <ToolboxItems VSCategory = "Data">  
        <ToolboxItems />  
    </File>  
    ```  
  
4.  Denetimleri farklı kategori adları altında karışım ve Visual Studio koyun.  
  
    ```  
    // Blend accepts a slightly different structure for the category name because it allows a path rather than a single category.  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Graph" BlendCategory = "Controls/sample/Graph">   
        <ToolboxItems />  
    </File>  
    ```  
  
5.  Özel denetimler karışım ve Visual Studio farklı şekilde sıralar.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Graph">  
        <ToolboxItems/>  
        <ToolboxItems BlendCategory = "Controls/sample/Graph">  
        <ToolboxItems/>  
    </File>  
    ```  
  
6.  Özel denetimler numaralandırır ve Visual Studio ortak yolunda veya yalnızca tüm denetimler grubuna yerleştirin.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Toolbox.Common">  
        <ToolboxItems />  
        <ToolboxItems VSCategory = "Toolbox.All">  
        <ToolboxItems />  
    </File>  
    ```  
  
7.  Özel denetimler numaralandırır ve yalnızca belirli bir grup içinde ChooseItems onlar olmadan göster araç kutusunda bırakılıyor.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Toolbox.ChooseItemsOnly">  
        <ToolboxItems />  
    </File>  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: C++ kullanarak bir SDK oluşturma](../extensibility/walkthrough-creating-an-sdk-using-cpp.md)   
 [İzlenecek yol: C# veya Visual Basic kullanan bir SDK oluşturma](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md)   
 [Bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md)