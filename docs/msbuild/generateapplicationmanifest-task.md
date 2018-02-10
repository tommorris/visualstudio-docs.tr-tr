---
title: "GenerateApplicationManifest görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GenerateApplicationManifest
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateApplicationManifest task
- HostInBrowser property (MSBuild)
- GenerateApplicationManifest task [MSBuild]
ms.assetid: a494102b-0cb2-4755-8e2a-d2c0f39fac1d
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 76a2fc5e184b566e0c9783f6f64beecc7ca882a2
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="generateapplicationmanifest-task"></a>GenerateApplicationManifest Görevi
Oluşturan bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi ya da yerel bir bildirim. Yerel bir bildirim bileşen için benzersiz bir kimlik tanımlayarak ve tüm derlemeleri ve yedekleme bileşeni olun dosyaları tanımlayan bir bileşen açıklar. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi uygulamanın giriş noktası belirten ve uygulama güvenlik düzeyi belirterek yerel bir bildirim genişletir.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerini açıklar `GenerateApplicationManifest` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AssemblyName`|İsteğe bağlı `String` parametresi.<br /><br /> Belirtir `Name` üretilen bildirim için derleme kimlik alanı. Bu parametre belirtilmezse, ad alanından algılanır `EntryPoint` veya `InputManifest` parametreleri. Görev adı yok oluşturulabilir, bir hata oluşturur.|  
|`AssemblyVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Belirtir `Version` üretilen bildirim için derleme kimlik alanı. Bu parametre belirtilmezse, varsayılan değer "1.0.0.0" olarak kullanılır.|  
|`ClrVersion`|İsteğe bağlı `String` parametresi.<br /><br /> En düşük sürüm, ortak dil çalışma zamanı (uygulama tarafından istenen CLR) belirtir. CLR sürümü yapı sistem tarafından kullanılan varsayılan değerdir. Görev bir yerel bildirimi oluşturuyorsa, bu parametre yoksayılır.|  
|`ConfigFile`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Uygulama yapılandırma dosyasına hangi öğeyi içeren belirtir. Görev bir yerel bildirimi oluşturuyorsa, bu parametre yoksayılır.|  
|`Dependencies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Üretilen bildirim için bağımlı derlemeler kümesini tanımlayan bir öğe listesini belirtir. Her bir öğe başka ek dağıtım durumu ve bağımlılığı türünü belirtmek için öğe meta verileri tarafından açıklanan. Daha fazla bilgi için aşağıdaki "Öğe meta verileri" bölümüne bakın.|  
|`Description`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama veya bileşen için açıklamayı belirtir.|  
|`EntryPoint`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Giriş noktası için oluşturulan bildirim derleme belirten tek bir öğe belirtir.<br /><br /> İçin bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi, bu parametre, uygulamayı çalıştırdığınızda başlayan derleme belirtir.|  
|`ErrorReportUrl`|İsteğe bağlı <xref:System.String?displayProperty=fullName> parametresi.<br /><br /> İletişim kutularında hata raporlarına ClickOnce yüklemeleri sırasında görüntülenen Web sayfasının URL'sini belirtir.|  
|`FileAssociations`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> ClickOnce dağıtım bildirimi ile ilişkili bir veya daha fazla dosya türü listesini belirtir.<br /><br /> Yalnızca .NET Framework 3.5 veya sonrasını hedeflendiğinde ilişkilendirmeleri yalnızca geçerli dosya.|  
|`Files`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Bildirimde eklenecek dosyaları. Her bir dosyanın tam yolunu belirtin.|  
|`HostInBrowser`|İsteğe bağlı <xref:System.Boolean> parametresi.<br /><br /> Varsa `true`, uygulama (WPF Web tarayıcısı uygulamaları gibi) bir tarayıcıda barındırılır.|  
|`IconFile`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Uygulama simge dosyasını belirtir. Uygulama simgesi oluşturulan uygulama bildiriminde ifade edilir ve Başlat menüsünde ve Program Ekle/Kaldır iletişim kutusu için kullanılır. Bu giriş belirtilmezse, varsayılan bir simge kullanılır. Görev bir yerel bildirimi oluşturuyorsa, bu parametre yoksayılır.|  
|`InputManifest`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Bildirim oluşturucu için bir temel olarak hizmet verecek bir girdi XML belgesi gösterir. Bu uygulama güvenliği veya çıkış bildiriminde yansıtılması özel bildirim tanımları gibi yapılandırılmış verileri sağlar. XML belgesi kök öğesinde bir derleme düğümü asmv1 ad alanında olması gerekir.|  
|`IsolatedComReferences`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Oluşturulan bildiriminde yalıtmak için COM bileşenlerini belirtir. Bu parametre "Kayıt ücretsiz COM" dağıtımı için COM bileşenlerini yalıtmak için özelliğini destekler. Otomatik standart COM kayıt tanımları içeren bir bildirim oluşturmak tarafından çalışır. Ancak, COM bileşenleri bu düzgün çalışması sırayla yapı makinesinde kayıtlı olması gerekir.|  
|`ManifestType`|İsteğe bağlı `String` parametresi.<br /><br /> Bildirimi oluşturmak için hangi türünü belirtir. Bu parametre aşağıdaki değerlere sahip olabilir:<br /><br /> -   `Native`<br />-   `ClickOnce`<br /><br /> Bu parametre belirtilmezse, görevin varsayılan olarak `ClickOnce`.|  
|`MaxTargetPath`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dosya yolu için izin verilen uzunluk üst sınırını belirtir bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama dağıtımı. Bu değer belirtilmezse, uygulamadaki her dosya yolunun uzunluğu bu sınırınızı denetlenir. Sınırı aşan tüm öğeleri bir yapı uyarısına ortaya koyar. Bu giriş belirtilmemiş ya da sıfır sonra hiçbir denetimi gerçekleştirilir. Görev bir yerel bildirimi oluşturuyorsa, bu parametre yoksayılır.|  
|`OSVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama için gereken en düşük gerekli işletim sistemi (OS) sürümünü belirtir. Örneğin, değeri "5.1.2600.0" işletim sistemi Windows XP olduğunu gösterir. Bu parametre belirtilmezse, Windows 98 İkinci Sürüm belirten "4.10.0.0" değeri kullanılır, desteklenen en düşük .NET Framework'ün işletim sistemi. Görev bir yerel bildirimi oluşturuyorsa bu girişi göz ardı edilir.|  
|`OutputManifest`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> çıkış parametresi.<br /><br /> Oluşturulan çıktı bildirim dosyasının adını belirtir. Bu parametre belirtilmezse, çıktı dosyası adını üretilen bildirim kimlikten algılanır.|  
|`Platform`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulamanın hedef platformu belirtir. Bu parametre aşağıdaki değerlere sahip olabilir:<br /><br /> -   `AnyCPU`<br />-   `x86`<br />-   `x64`<br />-   `Itanium`<br /><br /> Bu parametre belirtilmezse, görevin varsayılan olarak `AnyCPU`.|  
|`Product`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulamanın adını belirtir. Bu parametre belirtilmezse, adı üretilen bildirim kimlikten algılanır. Bu ad Başlat menüsündeki kısayol adı için kullanılan ve Program Ekle veya Kaldır iletişim kutusunda görünen adı bir parçasıdır.|  
|`Publisher`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama yayımcısının belirtir. Bu parametre belirtilmezse, adı kayıtlı kullanıcı veya üretilen bildirim kimliğini algılanır. Bu ad Başlat menüsündeki klasör adı için kullanılan ve Program Ekle veya Kaldır iletişim kutusunda görünen adı bir parçasıdır.|  
|`RequiresMinimumFramework35SP1`|İsteğe bağlı `Boolean` parametresi.<br /><br /> TRUE ise, uygulama .NET Framework 3.5 SP1 veya daha yeni bir sürüm gerektiriyor.|  
|`TargetCulture`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama kültürünü tanımlar ve belirtir `Language` üretilen bildirim için derleme kimlik alanı. Bu parametre belirtilmezse, sabit kültür uygulamasıdır varsayılır.|  
|`TargetFrameworkMoniker`|İsteğe bağlı `String` parametresi.<br /><br /> Hedef framework ad belirtir.|  
|`TargetFrameworkProfile`|İsteğe bağlı `String` parametresi.<br /><br /> Hedef framework profilini belirtir.|  
|`TargetFrameworkSubset`|İsteğe bağlı `String` parametresi.<br /><br /> Hedef .NET Framework alt adını belirtir.|  
|`TargetFrameworkVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Hedef .NET Framework projenin belirtir.|  
|`TrustInfoFile`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Uygulama güvenliği belirten bir XML belgesi gösterir. XML belgesi kök öğesinde bir trustInfo düğümü asmv2 ad alanında olması gerekir. Görev bir yerel bildirimi oluşturuyorsa, bu parametre yoksayılır.|  
|`UseApplicationTrust`|İsteğe bağlı `Boolean` parametresi.<br /><br /> TRUE ise, `Product`, `Publisher`, ve `SupportUrl` özellikleri, uygulama bildirimine yazılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.GenerateManifestBase> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Task sınıfı parametrelerinin listesi için bkz: [görev taban sınıfı](../msbuild/task-base-class.md).  
  
 Nasıl kullanılacağı hakkında bilgi için `GenerateDeploymentManifest` görev için bkz: [GenerateApplicationManifest görevi](../msbuild/generateapplicationmanifest-task.md).  
  
 Her öğe için ek dağıtım durumu belirtmek için öğe meta verileri ile girişleri bağımlılıklar ve dosyaları için daha fazla donatılmış.  
  
## <a name="item-metadata"></a>Öğe meta verileri  
  
|Meta veri adı|Açıklama|  
|-------------------|-----------------|  
|`DependencyType`|Bağımlılık yayımlanan ve uygulama veya bir önkoşulu yüklü olup olmadığını gösterir. Bu meta veriler için tüm bağımlılıkların geçerlidir, ancak dosyaları için kullanılmaz. Bu meta verileri için kullanılabilir değerler şunlardır:<br /><br /> -   `Install`<br />-   `Prerequisite`<br /><br /> Yükleme varsayılan değerdir.|  
|`AssemblyType`|Bağımlılık yönetilen olup veya yerel bir derleme gösterir. Bu meta veriler için tüm bağımlılıkların geçerlidir, ancak dosyaları için kullanılmaz. Bu meta verileri için kullanılabilir değerler şunlardır:<br /><br /> -   `Managed`<br />-   `Native`<br />-   `Unspecified`<br /><br /> `Unspecified`Bildirim oluşturucu derleme türü otomatik olarak belirler gösteren varsayılan değerdir.|  
|`Group`|Ek dosyalar isteğe bağlı indirme için grubu gösterir. Grup adı uygulama tarafından tanımlanır ve herhangi bir dize olabilir. Boş bir dize dosyanın varsayılan yükleme bir grubun parçası olduğunu gösterir. Dosyaları bir gruptaki ilk uygulama indirme bir parçasıdır. Açıkça kullanılarak uygulama tarafından istendiğinde, bir grup içindeki dosyaları karşıdan yalnızca <xref:System.Deployment.Application>.<br /><br /> Bu meta veriler tüm dosyalar için geçerli nerede `IsDataFile` olan `false` ve tüm bağımlılıkları nerede `DependencyType` olan `Install`.|  
|`TargetPath`|Yolun oluşturulan bildiriminde nasıl tanımlanmalıdır belirtir. Bu öznitelik tüm dosyalar için geçerli değil. Bu özniteliği belirtilmezse, öğesi belirtimi kullanılır. Bu öznitelik tüm dosyaları ve bağımlılıkları olan geçerli bir `DependencyType` değerini `Install`.|  
|`IsDataFile`|A `Boolean` dosyayı bir veri dosyası olup olmadığını gösteren meta veri değeri. Uygulama güncelleştirmeleri arasında geçiş, bir veri dosyası özeldir. Bu meta veriler yalnızca dosyalar için geçerlidir. `False`varsayılan değerdir.|  
  
## <a name="example"></a>Örnek  
 Bu örnekte `GenerateApplicationManifest` oluşturmak için görev bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi ve `GenerateDeploymentManifest` tek bir derleme olan bir uygulama için dağıtım bildirimi oluşturmak için görev. Daha sonra kullanır `SignFile` bildirimlerini imzalamak için görev.  
  
 Bu basit olası bildirim üretme senaryosu gösterilmektedir nerede [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bildirimleri için tek bir program oluşturulur. Varsayılan adı ve kimlik için bildirim derlemesinden algılanır.  
  
> [!NOTE]
>  Aşağıdaki örnekte, tüm uygulama ikili dosyaları bildirim üretme yönlere odaklanmak için önceden oluşturulmuş. Bu örnek tam olarak çalışan üretir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım.  
  
> [!NOTE]
>  Daha fazla bilgi için `Thumbprint` kullanılan özellik `SignFile` görev Bu örnekte, bkz: [SignFile görevi](../msbuild/signfile-task.md).  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <Thumbprint>  
             <!-- Insert generated thumbprint here -->  
        </Thumbprint>  
    </PropertyGroup>  
  
    <Target Name="Build">  
  
        <GenerateApplicationManifest  
            EntryPoint="@(EntryPoint)">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
        <GenerateDeploymentManifest  
            EntryPoint="@(ApplicationManifest)">  
            <Output  
                ItemName="DeployManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateDeploymentManifest>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(ApplicationManifest)"/>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(DeployManifest)"/>  
  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Örnek  
 Bu örnekte `GenerateApplicationManifest` ve `GenerateDeploymentManifest` oluşturmak için görevler [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama ve dağıtım bildirimlerini adı ve bildirimleri kimliğini belirten tek bir derleme olan bir uygulama için.  
  
 Bildirimleri kimliğini ve adını açıkça belirtilen dışında bu önceki örneğe benzer bir örneğidir. Ayrıca, bu örnek, yüklü bir uygulama yerine çevrimiçi bir uygulama olarak yapılandırılır.  
  
> [!NOTE]
>  Aşağıdaki örnekte, tüm uygulama ikili dosyaları bildirim üretme yönlere odaklanmak için önceden oluşturulmuş. Bu örnek tam olarak çalışan üretir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım.  
  
> [!NOTE]
>  Daha fazla bilgi için `Thumbprint` kullanılan özellik `SignFile` görev Bu örnekte, bkz: [SignFile görevi](../msbuild/signfile-task.md).  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <Thumbprint>  
             <!-- Insert generated thumbprint here -->  
        </Thumbprint>  
    </PropertyGroup>  
  
    <Target Name="Build">  
  
        <GenerateApplicationManifest  
            AssemblyName="SimpleWinApp.exe"  
            AssemblyVersion="1.0.0.0"  
            EntryPoint="@(EntryPoint)"  
            OutputManifest="SimpleWinApp.exe.manifest">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
        <GenerateDeploymentManifest  
                AssemblyName="SimpleWinApp.application"  
                AssemblyVersion="1.0.0.0"  
                EntryPoint="@(ApplicationManifest)"  
                Install="false"  
                OutputManifest="SimpleWinApp.application">  
                <Output  
                    ItemName="DeployManifest"  
                    TaskParameter="OutputManifest"/>  
        </GenerateDeploymentManifest>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(ApplicationManifest)"/>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(DeployManifest)"/>  
  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Örnek  
 Bu örnekte `GenerateApplicationManifest` ve `GenerateDeploymentManifest` oluşturmak için görevler [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama ve dağıtım birden çok dosya ve derlemeler için uygulama bildirimleri.  
  
> [!NOTE]
>  Aşağıdaki örnekte, tüm uygulama ikili dosyaları bildirim üretme yönlere odaklanmak için önceden oluşturulmuş. Bu örnek tam olarak çalışan üretir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım.  
  
> [!NOTE]
>  Daha fazla bilgi için `Thumbprint` kullanılan özellik `SignFile` görev Bu örnekte, bkz: [SignFile görevi](../msbuild/signfile-task.md).  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <Thumbprint>  
             <!-- Insert generated thumbprint here -->  
        </Thumbprint>  
        <DeployUrl>  
            <!-- Insert the deployment URL here -->  
        </DeployUrl>  
        <SupportUrl>  
            <!-- Insert the support URL here -->  
        </SupportUrl>  
    </PropertyGroup>  
  
    <Target Name="Build">  
  
    <ItemGroup>  
        <EntryPoint Include="SimpleWinApp.exe"/>  
        <Dependency Include="ClassLibrary1.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Install</DependencyType>  
        </Dependency>  
        <Dependency Include="ClassLibrary2.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Install</DependencyType>  
            <Group>Secondary</Group>  
        </Dependency>  
        <Dependency Include="MyAddIn1.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Install</DependencyType>  
            <TargetPath>Addins\MyAddIn1.dll</TargetPath>  
        </Dependency>  
        <Dependency Include="ClassLibrary3.dll">  
            <AssemblyType>Managed</AssemblyType>  
            <DependencyType>Prerequisite</DependencyType>  
        </Dependency>  
  
        <File Include="Text1.txt">  
            <TargetPath>Text\Text1.txt</TargetPath>  
            <Group>Text</Group>  
        </File>  
        <File Include="DataFile1.xml ">  
            <TargetPath>Data\DataFile1.xml</TargetPath>  
            <IsDataFile>true</IsDataFile>  
        </File>  
  
        <IconFile Include="Heart.ico"/>  
        <ConfigFile Include="app.config">  
            <TargetPath>SimpleWinApp.exe.config</TargetPath>  
        </ConfigFile>  
        <BaseManifest Include="app.manifest"/>  
    </ItemGroup>  
  
    <Target Name="Build">  
  
        <GenerateApplicationManifest  
            AssemblyName="SimpleWinApp.exe"  
            AssemblyVersion="1.0.0.0"  
            ConfigFile="@(ConfigFile)"  
            Dependencies="@(Dependency)"  
            Description="TestApp"  
            EntryPoint="@(EntryPoint)"  
            Files="@(File)"  
            IconFile="@(IconFile)"  
            InputManifest="@(BaseManifest)"  
            OutputManifest="SimpleWinApp.exe.manifest">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
        <GenerateDeploymentManifest  
            AssemblyName="SimpleWinApp.application"  
            AssemblyVersion="1.0.0.0"  
            DeploymentUrl="$(DeployToUrl)"  
            Description="TestDeploy"  
            EntryPoint="@(ApplicationManifest)"  
            Install="true"  
            OutputManifest="SimpleWinApp.application"  
            Product="SimpleWinApp"  
            Publisher="Microsoft"  
            SupportUrl="$(SupportUrl)"  
            UpdateEnabled="true"  
            UpdateInterval="3"  
            UpdateMode="Background"  
            UpdateUnit="weeks">  
            <Output  
                ItemName="DeployManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateDeploymentManifest>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(ApplicationManifest)"/>  
  
        <SignFile  
            CertificateThumbprint="$(Thumbprint)"  
            SigningTarget="@(DeployManifest)"/>  
  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Örnek  
 Bu örnekte `GenerateApplicationManifest` uygulama yerel bileşeni Alpha.dll ve yalıtılmış bir COM bileşeni Bravo.dll başvuran Test.exe için yerel bir bildirim oluşturmak üzere görev.  
  
 Bu örnek uygulama XCOPY dağıtılabilir yararlanarak kayıt ücretsiz com yapma Test.exe.manifest üretir  
  
> [!NOTE]
>  Aşağıdaki örnekte, tüm uygulama ikili dosyaları bildirim üretme yönlere odaklanmak için önceden oluşturulmuş. Bu örnek tam olarak çalışan üretir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım.  
  
```xml  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <File Include="Test.exe" />  
        <Dependency Include="Alpha.dll">  
            <AssemblyType>Native</AssemblyType>  
            <DependencyType>Install</DependencyType>  
        </Dependency>  
        <ComComponent Include="Bravo.dll" />  
    </ItemGroup>  
  
    <Target Name="Build">  
        <GenerateApplicationManifest  
            AssemblyName="Test.exe"  
            AssemblyVersion="1.0.0.0"  
            Dependencies="@(Dependency)"  
            Files="@(File)"  
            IsolatedComReferences="@(ComComponent)"  
            ManifestType="Native">  
            <Output  
                ItemName="ApplicationManifest"  
                TaskParameter="OutputManifest"/>  
        </GenerateApplicationManifest>  
  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [GenerateDeploymentManifest görevi](../msbuild/generatedeploymentmanifest-task.md)   
 [SignFile görevi](../msbuild/signfile-task.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)