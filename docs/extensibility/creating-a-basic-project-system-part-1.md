---
title: "Temel Proje sistem oluşturma, bölüm 1 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- writing a project system
- project system
- tutorial
ms.assetid: 882a10fa-bb1c-4b01-943a-7a3c155286dd
caps.latest.revision: "47"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e61c0d681dac52e85c3854325ee20ada29d74d4c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-basic-project-system-part-1"></a>Temel Proje sistem oluşturma, bölüm 1
Visual Studio'da projeler geliştiricilerin kaynak kodu dosyaları ve diğer varlıklar düzenlemek için kullandığınız kapsayıcılardır. Projeleri görünür çözümlerinde alt öğeleri olarak **Çözüm Gezgini**. Projeleri düzenlemek, yapı, hata ayıklama ve kaynak kodu dağıtmak ve Web Hizmetleri, veritabanları ve diğer kaynaklara başvurular oluşturmanıza olanak tanır.  
  
 Projeleri proje dosyalarında örneğin .csproj dosyasından bir Visual C# projesi için tanımlanır. Kendi proje dosya adı uzantısına sahip kendi proje türü oluşturabilirsiniz. Proje türleri hakkında daha fazla bilgi için bkz: [proje türleri](../extensibility/internals/project-types.md).  
  
> [!NOTE]
>  Visual Studio özel Proje türü ile genişletmek gerekiyorsa, yararlanarak tavsiye [Visual Studio Proje sistemi](https://github.com/Microsoft/VSProjectSystem) birkaç proje sistemi sıfırdan oluşturma avantajları vardır:  
>   
>  -   Daha kolay başlatılıyor.  Temel Proje sistem on binlerce kod satırı gerektirir.  Gereksinimlerinize özelleştirmek önce CPS yararlanarak birkaç tıklama ekleme maliyeti azaltır.  
> -   Daha kolay bakım.  CPS yararlanarak, yalnızca kendi senaryolarınızı korumak gerekir.  Proje sistem altyapı sürdürülmesinden işleme.  
>   
>  Visual Studio Visual Studio 2013'ün eski sürümleri hedef gerekiyorsa, bir Visual Studio Uzantısı'nda CPS yararlanamaz olmaz.  Bu durumda, bu kılavuzda başlamak için uygun bir yerdir.  
  
 Bu kılavuzda proje dosya adı uzantısı .myproj olan bir proje türü oluşturulacağını gösterir. Bu kılavuz, mevcut Visual C# proje sistemden taşır.  
  
> [!NOTE]
>  Uzantısı projeleri daha fazla örnekleri için bkz: [VSSDK örnekleri](http://aka.ms/vs2015sdksamples).  
  
 Bu kılavuzda, bu görevleri gerçekleştirmek üzere öğretir:  
  
-   Temel Proje türü oluşturun.  
  
-   Temel Proje şablonu oluşturun.  
  
-   Proje şablonu Visual Studio ile kaydedin.  
  
-   Proje örneği açarak oluşturma **yeni proje** iletişim kutusunu ve ardından, şablonunuzu kullanarak.  
  
-   Proje sisteminiz için bir proje fabrikası oluşturun.  
  
-   Proje sisteminiz için bir proje düğümüne oluşturun.  
  
-   Proje sistemi için özel simgeler ekleyin.  
  
-   Temel Şablon parametre değiştirme uygulayın.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
 Kaynak kodu indirmeniz gerekir [paket çerçevesi ile yönetilen projeleri için](http://mpfproj12.codeplex.com/). Dosyayı oluşturmak için kalacaklarını çözüme erişilebilen bir konuma ayıklayın.  
  
## <a name="creating-a-basic-project-type"></a>Temel Proje türü oluşturma  
 Adlı bir C# VSIX proje oluşturma **SimpleProject**. (**Dosya, yeni, proje** ve ardından **C#, genişletilebilirlik, Visual Studio Paketi**). Visual Studio Paketi proje öğesi şablon ekleme (Çözüm Gezgini proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**, ardından **genişletilebilirlik / Visual Studio Paketi**). Dosya adı **SimpleProjectPackage**.  
  
## <a name="creating-a-basic-project-template"></a>Temel Proje şablonu oluşturma  
 Artık, yeni .myproj proje türü uygulamak için bu temel VSPackage değiştirebilirsiniz. .Myproj proje türüne göre bir proje oluşturmak için Visual Studio hangi dosyaları, kaynakları ve yeni projeye eklemek için başvurular bilmesi gerekir. Bu bilgi sağlamak için bir proje şablonu klasöründe proje dosyalarını yerleştirin. Bir kullanıcı bir proje oluşturmak için .myproj proje kullandığında, dosyaları yeni projeye kopyalanır.  
  
#### <a name="to-create-a-basic-project-template"></a>Temel Proje şablonu oluşturmak için  
  
1.  Üç klasör proje diğer altında bir tane ekleyin: **Templates\Projects\SimpleProject**. (İçinde **Çözüm Gezgini**, sağ **SimpleProject** proje düğümünü, fareyle **Ekle**ve ardından **yeni klasör**. Klasör adı `Templates`. İçinde **şablonları** klasör adında bir klasör ekleme `Projects`. Buna **projeleri** klasör adında bir klasör ekleme `SimpleProject`.)  
  
2.  İçinde **Projects\SimpleProject** klasörü Ekle adlı bir simge dosyası `SimpleProject.ico`. Tıkladığınızda **Ekle**, simge Düzenleyicisi'ni açar.  
  
3.  Simge ayırıcı olun. Bu simge görünür **yeni proje** iletişim kutusunda daha sonra gözden geçirme.  
  
     ![Basit Proje simgesi](../extensibility/media/simpleprojicon.png "SimpleProjIcon")  
  
4.  Kaydet simgesine ve simge Düzenleyicisi'ni kapatın.  
  
5.  İçinde **Projects\SimpleProject** klasörüne eklemek bir **sınıfı** adlı öğe `Program.cs`.  
  
6.  Varolan kod aşağıdaki satırları içeren değiştirin.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
  
    namespace $nameSpace$  
    {  
        public class $className$  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
    > [!IMPORTANT]
    >  Bu son formun Program.cs kod değildir; değiştirme parametreleri ile bir sonraki adımda ele. Görebileceğiniz derleme hataları, ancak sürece dosyanın **BuildAction** olan **içerik**, projesini derlemeyi ve her zamanki gibi çalıştırmayı yapabiliyor olmanız gerekir.  
  
1.  Dosyayı kaydedin.  
  
2.  AssemblyInfo.cs dosyasından kopyalama **özellikleri** klasörüne **Projects\SimpleProject** klasör.  
  
3.  İçinde **Projects\SimpleProject** klasörü Ekle adlı bir XML dosyası `SimpleProject.myproj`.  
  
    > [!NOTE]
    >  Bu türdeki tüm projeleri için dosya adı uzantısı .myproj ' dir. Bunu değiştirmek istiyorsanız, bu kılavuzda açıklanan her yerde değiştirmelisiniz.  
  
4.  Var olan içerik, aşağıdaki satırları içeren değiştirin.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <SchemaVersion>2.0</SchemaVersion>  
        <ProjectGuid></ProjectGuid>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>MyRootNamespace</RootNamespace>  
        <AssemblyName>MyAssemblyName</AssemblyName>  
        <EnableUnmanagedDebugging>false</EnableUnmanagedDebugging>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">  
        <DebugSymbols>true</DebugSymbols>  
        <OutputPath>bin\Debug\</OutputPath>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">  
        <DebugSymbols>false</DebugSymbols>  
        <OutputPath>bin\Release\</OutputPath>  
      </PropertyGroup>  
      <ItemGroup>  
        <Reference Include="mscorlib" />  
        <Reference Include="System" />  
        <Reference Include="System.Data" />  
        <Reference Include="System.Xml" />  
      </ItemGroup>  
      <ItemGroup>  
        <Compile Include="AssemblyInfo.cs">  
          <SubType>Code</SubType>  
        </Compile>  
        <Compile Include="Program.cs">  
          <SubType>Code</SubType>  
        </Compile>  
      </ItemGroup>  
      <Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />  
    </Project>  
    ```  
  
5.  Dosyayı kaydedin.  
  
6.  İçinde **özellikleri** penceresindeki ayarlayın **yapı eylemi** AssemblyInfo.cs, Program.cs, SimpleProject.ico ve SimpleProject.myproj için **içerik**ve kendi ayarlayın **İçinde VSIX içine dahil** özelliklerine **doğru**.  
  
 Bu proje şablonu, bir hata ayıklama yapılandırmasını ve yayın yapılandırma sahip bir temel Visual C# projesinde açıklar. İki kaynak dosyaları, AssemblyInfo.cs ve Program.cs ve birkaç derleme proje içeriyor başvuruları. Bir proje şablonu oluşturduğunuzda, ProjectGuid değer otomatik olarak yeni bir GUID ile değiştirilir.  
  
 İçinde **Çözüm Gezgini**, Genişletilmiş **şablonları** klasörü aşağıdaki gibi görünmelidir:  
  
 Şablonlar  
  
 Projeler  
  
 SimpleProject  
  
 AssemblyInfo.cs  
  
 Program.cs  
  
 SimpleProject.ico  
  
 SimpleProject.myproj  
  
## <a name="creating-a-basic-project-factory"></a>Bir temel proje fabrikası oluşturma  
 Visual Studio Proje şablonu klasörünün konumunu bildirmeniz gerekir. Bunu yapmak için bir öznitelik proje Fabrika uygular ve böylece VSPackage yapılandırıldığında şablon konumu sistem kayıt defterine yazılır VSPackage sınıfına ekleyin. Proje fabrikası GUID tarafından tanımlanan bir temel proje fabrikası oluşturmaya başlayın. Kullanım <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> SimpleProjectPackage sınıfına proje Fabrika bağlanmak için öznitelik.  
  
#### <a name="to-create-a-basic-project-factory"></a>Temel Proje factory oluşturmak için  
  
1.  SimpleProjectPackageGuids.cs kod düzenleyicisinde açın.  
  
2.  Proje fabrikanızın GUID'ler oluşturun (üzerinde **Araçları** menüsünde tıklatın **Create GUID**), veya aşağıdaki örnekte kullanın. GUID'lerin SimpleProjectPackageGuids sınıfına ekleyin. GUID'lerin hem GUID ve dize formunda olmalıdır. Ortaya çıkan kodu aşağıdaki örneğe benzemelidir.  
  
    ```  
    static class SimpleProjectPackageGuids  
    {  
        public const string guidSimpleProjectPkgString =   
            "96bf4c26-d94e-43bf-a56a-f8500b52bfad";  
        public const string guidSimpleProjectCmdSetString =   
            "72c23e1d-f389-410a-b5f1-c938303f1391";  
        public const string guidSimpleProjectFactoryString =   
            "471EC4BB-E47E-4229-A789-D1F5F83B52D4";  
  
        public static readonly Guid guidSimpleProjectCmdSet =   
            new Guid(guidSimpleProjectCmdSetString);  
        public static readonly Guid guidSimpleProjectFactory =   
            new Guid(guidSimpleProjectFactoryString);  
    }  
    ```  
  
3.  Bir sınıf en üstüne ekleyin **SimpleProject** adlı klasörü `SimpleProjectFactory.cs`.  
  
4.  Aşağıdaki using deyimlerini:  
  
    ```  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.Shell;  
    ```  
  
5.  Guid özniteliği SimpleProjectFactory sınıfına ekleyin. Yeni Proje üreteci GUID öznitelik değeri.  
  
    ```  
    [Guid(SimpleProjectGuids.guidSimpleProjectFactoryString)]  
    class SimpleProjectFactory  
    {  
    }  
    ```  
  
 Artık, proje şablonu kaydedebilirsiniz.  
  
#### <a name="to-register-the-project-template"></a>Proje şablonu kaydetmek için  
  
1.  SimpleProjectPackage.cs içinde eklemek bir <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> SimpleProjectPackage sınıfına aşağıdaki gibi özniteliği.  
  
    ```  
    [ProvideProjectFactory(    typeof(SimpleProjectFactory),     "Simple Project",   
        "Simple Project Files (*.myproj);*.myproj", "myproj", "myproj",   
        @"Templates\Projects\SimpleProject",     LanguageVsTemplate = "SimpleProject")]  
    [Guid(SimpleProjectGuids.guidSimpleProjectPkgString)]  
    public sealed class SimpleProjectPackage : Package  
    ```  
  
2.  Çözümü yeniden derleyin ve hatasız oluşturulduğunu doğrulayın.  
  
     Yeniden derleme proje şablonu kaydeder.  
  
 Parametreleri `defaultProjectExtension` ve `possibleProjectExtensions` proje dosya adı uzantısını (.myproj) ayarlayın. `projectTemplatesDirectory` Parametresini Şablonlar klasörünün göreli yolu ayarlayın. Derleme sırasında bu yol için tam bir yapı dönüştürülür ve proje sistemi kaydetmek için kayıt defterine eklenen.  
  
## <a name="testing-the-template-registration"></a>Şablonu kayıt test etme  
 Şablonu kayıt Visual Studio şablon adı ve simgesine görüntüleyebilmesi bu Visual Studio Proje şablonu klasörünün konumunu belirten **yeni proje** iletişim kutusu.  
  
#### <a name="to-test-the-template-registration"></a>Şablonu kayıt sınamak için  
  
1.  Visual Studio deneysel örneği hata ayıklamayı başlatmak için F5 tuşuna basın.  
  
2.  Deneysel örneğinde, yeni oluşturulan proje türü yeni bir proje oluşturun. İçinde **yeni proje** iletişim kutusu, görmelisiniz **SimpleProject** altında **yüklenmiş şablonlar**.  
  
 Artık kayıtlı bir proje fabrikası vardır. Ancak, bir proje henüz oluşturulamaz. Proje paketi ve proje Fabrika oluşturmak ve bir proje başlatmak için birlikte çalışır.  
  
## <a name="add-the-managed-package-framework-code"></a>Paket çerçevesi ile yönetilen kod ekleme  
 Proje paket ve proje Fabrika arasındaki bağlantıyı uygulayın.  
  
-   Kaynak kodu dosyaları için yönetilen paket çerçevesi Al.  
  
    1.  SimpleProject proje kaldırma (içinde **Çözüm Gezgini**, proje düğümünü seçin ve bağlam menüsünde tıklatın **projeyi**.) ve proje dosyasını XML düzenleyicisinde açın.  
  
    2.  Proje dosyasına aşağıdaki bloklarını ekleyin (yukarıdaki \<alma > blokları). Az önce indirdiğiniz paketi çerçevesi ile yönetilen kodda ProjectBase.files dosyasının konumu için ProjectBasePath ayarlayın. Yol adı bir ters eğik çizgi eklemeniz gerekebilir. Bunu yapmazsanız, proje paket çerçevesi ile yönetilen kod bulmak başarısız olabilir.  
  
        ```  
        <PropertyGroup>  
             <ProjectBasePath>your path here\</ProjectBasePath>  
             <RegisterWithCodebase>true</RegisterWithCodebase>  
          </PropertyGroup>  
          <Import Project="$(ProjectBasePath)\ProjectBase.Files" />  
        ```  
  
        > [!IMPORTANT]
        >  Yolun sonuna ters eğik çizgi unutmayın.  
  
    3.  Projeyi yeniden yükleyin.  
  
    4.  Aşağıdaki derlemelere başvurular ekleyin:  
  
        -   Microsoft.VisualStudio.Designer.Interfaces (içinde \<VSSDK yükleme > \VisualStudioIntegration\Common\Assemblies\v2.0)  
  
        -   WindowsBase  
  
        -   Microsoft.Build.Tasks.v4.0  
  
#### <a name="to-initialize-the-project-factory"></a>Proje Fabrika başlatmak için  
  
1.  Aşağıdaki SimpleProjectPackage.cs dosyasına ekleyin `using` deyimi.  
  
    ```  
    using Microsoft.VisualStudio.Project;  
    ```  
  
2.  Türetilen `SimpleProjectPackage` sınıfıyla `Microsoft.VisualStudio.Package.ProjectPackage`.  
  
    ```  
    public sealed class SimpleProjectPackage : ProjectPackage  
    ```  
  
3.  Proje üreteci kaydettirir. Aşağıdaki satırı ekleyin `SimpleProjectPackage.Initialize` yöntemi, hemen sonra `base.Initialize`.  
  
    ```  
    base.Initialize();  
    this.RegisterProjectFactory(new SimpleProjectFactory(this));  
    ```  
  
4.  Özet özelliği uygulamak `ProductUserContext`:  
  
    ```csharp  
    public override string ProductUserContext  
        {  
            get { return ""; }  
    }  
    ```  
  
5.  SimpleProjectFactory.cs içinde aşağıdaki ekleme `using` varolan sonra deyimi `using` deyimleri.  
  
    ```  
    using Microsoft.VisualStudio.Project;  
    ```  
  
6.  Türetilen `SimpleProjectFactory` sınıfıyla `ProjectFactory`.  
  
    ```  
    class SimpleProjectFactory : ProjectFactory  
    ```  
  
7.  Aşağıdaki kukla yöntemine ekleyin `SimpleProjectFactory` sınıfı. Bu yöntem bir sonraki bölümde gerçekleştireceksiniz.  
  
    ```  
    protected override ProjectNode CreateProject()  
    {  
        return null;  
    }  
    ```  
  
8.  Aşağıdaki alan ve oluşturucuya ekleyin `SimpleProjectFactory` sınıfı. Bu `SimpleProjectPackage` başvuru hizmet sağlayıcı site ayarı kullanılabilir böylece özel bir alana önbelleğe.  
  
    ```  
    private SimpleProjectPackage package;  
  
    public SimpleProjectFactory(SimpleProjectPackage package)  
        : base(package)  
    {  
        this.package = package;  
    }  
    ```  
  
9. Çözümü yeniden derleyin ve hatasız oluşturulduğunu doğrulayın.  
  
## <a name="testing-the-project-factory-implementation"></a>Proje Üreteç uygulaması test etme  
 Proje Fabrika uygulamanızı Oluşturucusu adlı olup olmadığını test edin.  
  
#### <a name="to-test-the-project-factory-implementation"></a>Proje Fabrika uygulanmasını test etmek için  
  
1.  Aşağıdaki satırında bir kesme noktası SimpleProjectFactory.cs dosyasında ayarlanan `SimpleProjectFactory` Oluşturucusu.  
  
    ```  
    this.package = package;  
    ```  
  
2.  Visual Studio deneysel örneği başlatmak için F5 tuşuna basın.  
  
3.  Yeni bir proje oluşturmak için deneysel örneğinde başlatın. İçinde **yeni proje** SimpleProject proje türü ve ardından iletişim kutusunda **Tamam**. Yürütme kesme noktasında durur.  
  
4.  Kesme noktası temizleyin ve hata ayıklamayı durdurun. Proje düğümüne henüz oluşturduk değil olduğundan, proje oluşturma kodu hala özel durumları oluşturur.  
  
## <a name="extending-the-project-node-class"></a>Proje düğümü sınıfı genişletme  
 Uygulayabileceğiniz artık `SimpleProjectNode` türeyen sınıf `ProjectNode` sınıfı. `ProjectNode` Temel sınıf proje oluşturma, aşağıdaki görevleri gerçekleştirir:  
  
-   Proje şablon dosyası, SimpleProject.myproj, yeni proje klasörüne kopyalar. Kopya girildiğini adına göre adlandırılır **yeni proje** iletişim kutusu. `ProjectGuid` Özellik değeri, yeni bir GUID ile değiştirilir.  
  
-   MSBuild öğeleri SimpleProject.myproj, proje şablonu dosyasının erişir ve arar `Compile` öğeleri. Her `Compile` hedef dosya, dosya yeni proje klasörüne kopyalar.  
  
 Türetilmiş `SimpleProjectNode` sınıfı bu görevleri gerçekleştirir:  
  
-   Proje ve dosya düğümler için simgeler etkinleştirir **Çözüm Gezgini** seçili veya oluşturulacak.  
  
-   Ek proje şablonu parametresi değiştirmeleri belirtilmesine olanak sağlar.  
  
#### <a name="to-extend-the-project-node-class"></a>Proje düğümü sınıfı genişletmek için  
  
1.  
  
2.  Adlı bir sınıf ekleyin `SimpleProjectNode.cs`.  
  
3.  Var olan kodu aşağıdaki kodla değiştirin.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Project;  
  
    namespace SimpleProject  
    {  
        public class SimpleProjectNode : ProjectNode  
        {  
            private SimpleProjectPackage package;  
  
            public SimpleProjectNode(SimpleProjectPackage package)  
            {  
                this.package = package;  
            }  
            public override Guid ProjectGuid  
            {  
                get { return SimpleProjectGuids.guidSimpleProjectFactory; }  
            }  
            public override string ProjectType  
            {  
                get { return "SimpleProjectType"; }  
            }  
  
            public override void AddFileFromTemplate(  
                string source, string target)  
            {  
                this.FileTemplateProcessor.UntokenFile(source, target);  
                this.FileTemplateProcessor.Reset();  
            }  
        }  
    }  
    ```  
  
 Bu `SimpleProjectNode` sınıfı uygulama geçersiz kılınan bu yöntemleri vardır:  
  
-   `ProjectGuid`, proje Fabrika GUID döndürür.  
  
-   `ProjectType`, proje türü yerelleştirilmiş adını döndürür.  
  
-   `AddFileFromTemplate`, hangi seçili dosyalarını kopyalar şablonu klasöründen hedef projeye. Bu yöntem daha sonraki bir bölüme uygulanır.  
  
 `SimpleProjectNode` Oluşturucusu gibi `SimpleProjectFactory` oluşturucusu, önbelleğe alan bir `SimpleProjectPackage` daha sonra kullanmak için özel bir alan başvurusu.  
  
 Bağlanmak için `SimpleProjectFactory` sınıfının `SimpleProjectNode` sınıfının, size gereken örneği yeni bir `SimpleProjectNode` içinde `SimpleProjectFactory.CreateProject` yöntemi ve daha sonra kullanmak için özel bir alandaki önbelleğe.  
  
#### <a name="to-connect-the-project-factory-class-and-the-node-class"></a>Proje Fabrika ve düğüm sınıf bağlanmak için  
  
1.  Aşağıdaki SimpleProjectFactory.cs dosyasına ekleyin `using` deyimi:  
  
    ```  
    using IOleServiceProvider =    Microsoft.VisualStudio.OLE.Interop.IServiceProvider;  
    ```  
  
2.  Değiştir `SimpleProjectFactory.CreateProject` aşağıdaki kodu kullanarak yöntemi.  
  
    ```  
    protected override ProjectNode CreateProject()  
    {  
        SimpleProjectNode project = new SimpleProjectNode(this.package);  
  
        project.SetSite((IOleServiceProvider)        ((IServiceProvider)this.package).GetService(            typeof(IOleServiceProvider)));  
        return project;  
    }  
    ```  
  
3.  Çözümü yeniden derleyin ve hatasız oluşturulduğunu doğrulayın.  
  
## <a name="testing-the-project-node-class"></a>Proje düğümü sınıfı test etme  
 Bir proje hiyerarşisi oluşturur olup olmadığını görmek için proje Fabrika sınayın.  
  
#### <a name="to-test-the-project-node-class"></a>Proje düğümü sınıfı test etmek için  
  
1.  Hata ayıklamayı başlatmak için F5 tuşuna basın. Deneysel örneğinde yeni SimpleProject oluşturun.  
  
2.  Visual Studio Proje oluşturmak için proje Fabrika çağırmanız gerekir.  
  
3.  Visual Studio Deneysel örneklerini kapatın.  
  
## <a name="adding-a-custom-project-node-icon"></a>Özel proje düğüm simgesi ekleme  
 Proje düğümü önceki bölümdeki varsayılan bir simge simgedir. Özel bir simgesi değiştirebilirsiniz.  
  
#### <a name="to-add-a-custom-project-node-icon"></a>Özel proje düğüm simgesi eklemek için  
  
1.  İçinde **kaynakları** klasörü, SimpleProjectNode.bmp adlı bir bit eşlem dosyası ekleyin.  
  
2.  İçinde **özellikleri** windows bit eşlem için 16 x 16 piksel azaltın. Bit eşlem ayırıcı olun.  
  
     ![Basit Proje iletişimi](../extensibility/media/simpleprojprojectcomm.png "SimpleProjProjectComm")  
  
3.  İçinde **özellikleri** penceresinde, değişiklik **yapı eylemi** bit eşlem için **katıştırılmış kaynak**.  
  
4.  SimpleProjectNode.cs içinde aşağıdaki ekleme `using` deyimleri:  
  
    ```  
    using System.Drawing;  
    using System.Windows.Forms;  
    ```  
  
5.  Aşağıdaki statik alan ekleyip oluşturucuya `SimpleProjectNode` sınıfı.  
  
    ```  
    private static ImageList imageList;  
  
    static SimpleProjectNode()  
    {  
        imageList =        Utilities.GetImageList(            typeof(SimpleProjectNode).Assembly.GetManifestResourceStream(                "SimpleProject.Resources.SimpleProjectNode.bmp"));  
    }  
    ```  
  
6.  Aşağıdaki özellik başlangıcına ekleme `SimpleProjectNode` sınıfı.  
  
    ```  
    internal static int imageIndex;  
       public override int ImageIndex  
       {  
           get { return imageIndex; }  
       }  
    ```  
  
7.  Örnek oluşturucusu aşağıdaki kodla değiştirin.  
  
    ```  
    public SimpleProjectNode(SimpleProjectPackage package)  
    {  
        this.package = package;  
  
        imageIndex = this.ImageHandler.ImageList.Images.Count;  
  
        foreach (Image img in imageList.Images)  
        {  
            this.ImageHandler.AddImage(img);  
        }  
    }  
    ```  
  
 Statik oluşturma sırasında `SimpleProjectNode` proje düğümü bitmap derleme bildirimi kaynaklardan alır ve daha sonra kullanmak için özel bir alandaki önbelleğe alır. Söz dizimi fark <xref:System.Reflection.Assembly.GetManifestResourceStream%2A> görüntü yolu. Bir derlemede katıştırılmış bildirim kaynakların adları görmek için <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> yöntemi. Ne zaman bu yöntem uygulanan `SimpleProject` derleme, sonuçları aşağıdaki gibi olmalıdır:  
  
-   SimpleProject.Resources.resources  
  
-   VisualStudio.Project.resources  
  
-   SimpleProject.VSPackage.resources  
  
-   Resources.imagelis.bmp  
  
-   Microsoft.VisualStudio.Project.DontShowAgainDialog.resources  
  
-   Microsoft.VisualStudio.Project.SecurityWarningDialog.resources  
  
-   SimpleProject.Resources.SimpleProjectNode.bmp  
  
 Örnek oluşturma sırasında `ProjectNode` temel sınıf olduğu Resources\imagelis.bmp gelen yaygın olarak kullanılan katıştırılmış 16 x 16 bit eşlemler Resources.imagelis.bmp yükler. Bu bit eşlem listesi için kullanılabilir hale getirilir `SimpleProjectNode` ImageHandler.ImageList olarak. `SimpleProjectNode`Proje düğümü bitmap listesine ekler. Resim listesi proje düğümü eşleminde uzaklığını değeri genel olarak daha sonra kullanmak için önbelleğe alınan `ImageIndex` özelliği. Visual Studio Proje düğümü simge olarak görüntülemek için hangi bit eşlem belirlemek için bu özelliği kullanır.  
  
## <a name="testing-the-custom-project-node-icon"></a>Özel proje düğüm simgesi test etme  
 Özel proje düğümü simgesine sahip bir proje hiyerarşisi oluşturur olup olmadığını görmek için proje Fabrika sınayın.  
  
#### <a name="to-test-the-custom-project-node-icon"></a>Özel proje düğüm simgesi sınamak için  
  
1.  Hata Ayıklamayı Başlat ve yeni SimpleProject deneysel örneğinde oluşturun.  
  
2.  Yeni oluşturulan proje SimpleProjectNode.bmp proje düğümü simgesi olarak kullanılmıştır.  
  
     ![Basit Proje yeni proje düğümünü](../extensibility/media/simpleprojnewprojectnode.png "SimpleProjNewProjectNode")  
  
3.  Program.cs kod düzenleyicisinde açın. Aşağıdaki kod benzer kaynak kodu görmeniz gerekir.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
  
    namespace $nameSpace$  
    {  
        public class $className$  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
     Yeni değerler olmayan şablon parametreleri $nameSpace$ ve $className$ dikkat edin. Sonraki bölümde şablon parametre değiştirme uygulamak öğreneceksiniz.  
  
## <a name="substituting-template-parameters"></a>Şablon parametreleri değiştirme  
 Bir önceki bölümde, proje şablonu ile Visual Studio kullanarak kayıtlı `ProvideProjectFactory` özniteliği. Bu şekilde bir şablon klasörünün yolunu kaydetme temel şablon parametre değiştirme geçersiz kılma ve genişletme etkinleştirme sağlar `ProjectNode.AddFileFromTemplate` sınıfı. Daha fazla bilgi için bkz: [yeni proje oluşturma: başlık altında bölümü iki](../extensibility/internals/new-project-generation-under-the-hood-part-two.md).  
  
 Şimdi değiştirme kodu ekleyin `AddFileFromTemplate` sınıfı.  
  
#### <a name="to-substitute-template-parameters"></a>Şablon parametreleri değiştirmek için  
  
1.  Aşağıdaki SimpleProjectNode.cs dosyasına ekleyin `using` deyimi.  
  
    ```  
    using System.IO;  
    ```  
  
2.  Değiştir `AddFileFromTemplate` aşağıdaki kodu kullanarak yöntemi.  
  
    ```  
    public override void AddFileFromTemplate(  
        string source, string target)  
    {  
        string nameSpace =   
            this.FileTemplateProcessor.GetFileNamespace(target, this);  
        string className = Path.GetFileNameWithoutExtension(target);  
  
        this.FileTemplateProcessor.AddReplace("$nameSpace$", nameSpace);  
        this.FileTemplateProcessor.AddReplace("$className$", className);  
  
        this.FileTemplateProcessor.UntokenFile(source, target);  
        this.FileTemplateProcessor.Reset();  
    }  
    ```  
  
3.  Hemen sonra yönteminde kesme noktası ayarlama `className` atama ifadesi.  
  
 Atama deyimleri makul değerler için bir ad alanı ve yeni bir sınıf adı belirler. İki `ProjectNode.FileTemplateProcessor.AddReplace` yöntem çağrıları, bu yeni değerleri kullanarak karşılık gelen şablon parametre değerlerini değiştirin.  
  
## <a name="testing-the-template-parameter-substitution"></a>Şablon parametresi değiştirme test etme  
 Artık şablon parametre değiştirme test edebilirsiniz.  
  
#### <a name="to-test-the-template-parameter-substitution"></a>Şablon parametresi değiştirme sınamak için  
  
1.  Hata Ayıklamayı Başlat ve yeni SimpleProject deneysel örneğinde oluşturun.  
  
2.  Yürütme durdurur kesme noktasındaki `AddFileFromTemplate` yöntemi.  
  
3.  Değerleri inceleyin `nameSpace` ve `className` parametreleri.  
  
    -   `nameSpace`değerini verilen \<RootNamespace > \Templates\Projects\SimpleProject\SimpleProject.myproj proje şablonu dosyasındaki öğesi. Bu durumda, "MyRootNamespace" değeridir.  
  
    -   `className`sınıf kaynak dosya adı, dosya adı uzantısı olmadan değeri verilir. Bu durumda, hedef klasöre kopyalanacak ilk AssemblyInfo.cs dosyasıdır; Bu nedenle, className "AssemblyInfo" değeri.  
  
4.  Kesme noktası kaldırın ve yürütme devam etmek için F5 tuşuna basın.  
  
     Visual Studio Proje oluşturma tamamlanmalıdır.  
  
5.  Program.cs kod düzenleyicisinde açın. Aşağıdaki kod benzer kaynak kodu görmeniz gerekir.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace MyRootNamespace  
    {  
        public class Program  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
     Ad alanı artık "MyRootNamespace" ve sınıf adı olduğuna dikkat edin "Program" sunulmuştur.  
  
6.  Projeyi hata ayıklamayı Başlat. Yeni Proje derleme, çalıştırmak ve "Merhaba VSX!!!" görüntülemek Konsol penceresinde.  
  
     ![Basit Proje komutu](../extensibility/media/simpleprojcommand.png "SimpleProjCommand")  
  
 Tebrikler! Temel yönetilen proje sistem uyguladık.