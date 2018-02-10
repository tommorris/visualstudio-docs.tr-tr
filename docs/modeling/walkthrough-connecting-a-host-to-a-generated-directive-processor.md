---
title: "İzlenecek yol: bir oluşturulan bir yönerge işlemcisi konağa bağlanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- walkthroughs [text templates], connecting host to processor
- text templates, custom directive hosts
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: b506957c80b1e678bab75afedb8a50621d611220
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="walkthrough-connecting-a-host-to-a-generated-directive-processor"></a>İzlenecek yol: Üretilen bir Yönerge İşlemcisine Ana Bilgisayar Bağlama
Metin şablonları işler kendi ana bilgisayar yazabilirsiniz. Temel bir özel konak örneklerde gösterildiği [izlenecek yol: özel metin şablonu konağı oluşturma](../modeling/walkthrough-creating-a-custom-text-template-host.md). Birden çok çıktı dosyaları oluşturma gibi işlevler eklemek için bu konak genişletebilirsiniz.  
  
 Bu kılavuzda, böylece yönerge işlemcileri çağrı metin şablonları destekleyen özel ana bilgisayarınız genişletin. Bir etki alanına özgü dil tanımladığınızda, bunu oluşturan bir *yönerge işlemcisi* etki alanı modeli için. Yönerge işlemcisi derleme yazma ve şablonlarındaki yönergeleri almak için gereksinimini azaltır modeline erişim şablonları yazmak kullanıcılar için daha kolay hale getirir.  
  
> [!WARNING]
>  Bu kılavuzda derlemeler [izlenecek yol: özel metin şablonu konağı oluşturma](../modeling/walkthrough-creating-a-custom-text-template-host.md). Bu izlenecek yol ilk gerçekleştirin.  
  
 Bu izlenecek yol aşağıdaki görevleri içerir:  
  
-   Kullanarak [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] bir etki alanı modelini temel alan bir yönerge işlemcisi oluşturmak için.  
  
-   Özel metin şablonu ana bilgisayarı için oluşturulan yönerge işlemcisi bağlanılıyor.  
  
-   Özel konak oluşturulan yönerge işlemcisi ile test etme.  
  
## <a name="prerequisites"></a>Önkoşullar  
 DSL tanımlamak için aşağıdaki bileşenler yüklü olmalıdır:  
  
|||  
|-|-|  
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|  
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|  
|Visual Studio Görselleştirme ve modelleme SDK||  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
  
 Ayrıca, oluşturduğunuz özel metin şablonu dönüştürme olmalıdır [izlenecek yol: özel metin şablonu konağı oluşturma](../modeling/walkthrough-creating-a-custom-text-template-host.md).  
  
## <a name="using-domain-specific-language-tools-to-generate-a-directive-processor"></a>Bir yönerge işlemcisi oluşturmak için etki alanına özgü dil araçları kullanma  
 Bu kılavuzda, bir etki alanına özgü dil DSLMinimalTest çözümü oluşturmak için etki alanına özgü dil Tasarımcısı Sihirbazı'nı kullanın.  
  
#### <a name="to-use-domain-specific-language-tools-to-generate-a-directive-processor-that-is-based-on-a-domain-model"></a>Etki alanına özgü dil araçları kullanarak bir etki alanı modelini temel alan bir yönerge işlemcisi oluşturmak için  
  
1.  Aşağıdaki özelliklere sahip bir etki alanına özgü dil çözümü oluşturun:  
  
    -   Ad: DSLMinimalTest  
  
    -   Çözüm şablonu: en az bir dil  
  
    -   Dosya uzantısı: en az  
  
    -   Şirket adı: Fabrikam  
  
     Bir etki alanına özgü dil çözümü oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir etki alanına özgü dil çözümü oluşturma](../modeling/how-to-create-a-domain-specific-language-solution.md).  
  
2.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
    > [!IMPORTANT]
    >  Bu adım yönerge işlemcisi oluşturur ve için kayıt defterinde anahtar ekler.  
  
3.  Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat**.  
  
     İkinci bir örneğini [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] açar.  
  
4.  Deneysel yapı içinde **Çözüm Gezgini**, dosyayı çift tıklatın **sample.min**.  
  
     Dosya Tasarımcısı'nda açılır. Model iki öğe, ExampleElement1 ve ExampleElement2 ve aralarındaki bağlantının olduğuna dikkat edin.  
  
5.  İkinci bir örneğini kapatmak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
6.  Çözüm kaydedin ve ardından etki alanına özgü dil Tasarımcısı'nı kapatın.  
  
## <a name="connecting-a-custom-text-template-host-to-a-directive-processor"></a>Özel metin şablonu yönerge işlemcisi konağa bağlanma  
 Yönerge işlemcisi ve oluşturduğunuz özel metin şablonu konağı yönerge işlemcisi oluşturduktan sonra bağlandığınız [izlenecek yol: özel metin şablonu konağı oluşturma](../modeling/walkthrough-creating-a-custom-text-template-host.md).  
  
#### <a name="to-connect-a-custom-text-template-host-to-the-generated-directive-processor"></a>Oluşturulan yönerge işlemcisi bir özel metin şablonu ana bilgisayarına bağlanmak için  
  
1.  CustomHost çözümü açın.  
  
2.  Üzerinde **proje** menüsünde tıklatın **Başvuru Ekle**.  
  
     **Başvuru Ekle** iletişim kutusu açılır ile **.NET** sekmesi görüntülenir.  
  
3.  Aşağıdaki başvurular ekleyin:  
  
    -   Microsoft.VisualStudio.Modeling.Sdk.11.0  
  
    -   Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0  
  
    -   Microsoft.VisualStudio.TextTemplating.11.0  
  
    -   Microsoft.VisualStudio.TextTemplating.Interfaces.11.0  
  
    -   Microsoft.VisualStudio.TextTemplating.Modeling.11.0  
  
    -   Microsoft.VisualStudio.TextTemplating.VSHost.11.0  
  
4.  Program.cs veya Module1.vb üst kısmında, aşağıdaki kod satırını ekleyin:  
  
    ```csharp  
    using Microsoft.Win32;  
    ```  
  
    ```vb  
    Imports Microsoft.Win32  
    ```  
  
5.  Özelliği için kodu bulun `StandardAssemblyReferences`ve aşağıdaki kod ile değiştirin:  
  
    > [!NOTE]
    >  Bu adımda, ana bilgisayarınız destekleyecek oluşturulan yönerge işlemcisi tarafından gerekli derlemelerine başvurular ekleyin.  
  
    ```csharp  
    //the host can provide standard assembly references  
    //the engine will use these references when compiling and  
    //executing the generated transformation class  
    //--------------------------------------------------------------  
    public IList<string> StandardAssemblyReferences  
    {  
        get  
        {  
            return new string[]  
            {  
                //if this host searches standard paths and the GAC  
                //we can specify the assembly name like this:  
                //"System"  
                //since this host only resolves assemblies from the   
                //fully qualified path and name of the assembly  
                //this is a quick way to get the code to give us the  
                //fully qualified path and name of the System assembly  
                //---------------------------------------------------------  
                typeof(System.Uri).Assembly.Location,  
                            typeof(System.Uri).Assembly.Location,  
                typeof(Microsoft.VisualStudio.Modeling.ModelElement).Assembly.Location,  
                typeof(Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape).Assembly.Location,  
                typeof(Microsoft.VisualStudio.TextTemplating.VSHost.ITextTemplating).Assembly.Location,  
                typeof(Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation).Assembly.Location  
  
            };  
        }  
    }  
    ```  
  
6.  İşlev için kodu bulun `ResolveDirectiveProcessor`ve aşağıdaki kod ile değiştirin:  
  
    > [!IMPORTANT]
    >  Bu kod, bağlanmak istediğiniz oluşturulan yönerge işlemcisi adını sabit kodlanmış başvurular içeriyor. Kolayca bu daha genel yaptığınız, kayıt defterinde listelenen tüm yönerge işlemcileri için görünüyor; bu durumda ve bir eşleşme bulmaya çalışır. Bu durumda, konak ile oluşturulan tüm yönerge işlemcisi çalışır.  
  
    ```csharp  
    //the engine calls this method based on the directives the user has   
            //specified it in the text template  
            //this method can be called 0, 1, or more times  
            //---------------------------------------------------------------------  
            public Type ResolveDirectiveProcessor(string processorName)  
            {  
                //check the processor name, and if it is the name of the processor the   
                //host wants to support, return the type of the processor  
                //---------------------------------------------------------------------  
                if (string.Compare(processorName, "DSLMinimalTestDirectiveProcessor", StringComparison.InvariantCultureIgnoreCase) == 0)  
                {  
                    try  
                    {  
                        string keyName = @"Software\Microsoft\VisualStudio\10.0Exp_Config\TextTemplating\DirectiveProcessors\DSLMinimalTestDirectiveProcessor";  
                        using (RegistryKey specificKey = Registry.CurrentUser.OpenSubKey(keyName))  
                        {  
                            if (specificKey != null)  
                            {  
                                List<string> names = new List<String>(specificKey.GetValueNames());  
                                string classValue = specificKey.GetValue("Class") as string;  
                                if (!string.IsNullOrEmpty(classValue))  
                                {  
                                    string loadValue = string.Empty;  
                                    System.Reflection.Assembly processorAssembly = null;  
                                    if (names.Contains("Assembly"))  
                                    {  
                                        loadValue = specificKey.GetValue("Assembly") as string;  
                                        if (!string.IsNullOrEmpty(loadValue))  
                                        {  
                                            //the assembly must be installed in the GAC  
                                            processorAssembly = System.Reflection.Assembly.Load(loadValue);  
                                        }  
                                    }  
                                    else if (names.Contains("CodeBase"))  
                                    {  
                                        loadValue = specificKey.GetValue("CodeBase") as string;  
                                        if (!string.IsNullOrEmpty(loadValue))  
                                        {  
                                            //loading local assembly  
                                            processorAssembly = System.Reflection.Assembly.LoadFrom(loadValue);  
                                        }  
                                    }  
                                    if (processorAssembly == null)  
                                    {  
                                        throw new Exception("Directive Processor not found");  
                                    }  
                                    Type processorType = processorAssembly.GetType(classValue);  
                                    if (processorType == null)  
                                    {  
                                        throw new Exception("Directive Processor not found");  
                                    }  
                                    return processorType;  
                                }  
                            }  
                        }  
                    }  
                    catch (Exception e)  
                    {  
                        //if the directive processor can not be found, throw an error  
                        throw new Exception("Directive Processor not found");  
                    }  
                }  
  
                //if the directive processor is not one this host wants to support  
                throw new Exception("Directive Processor not supported");  
            }  
    ```  
  
7.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet**.  
  
8.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
## <a name="testing-the-custom-host-with-the-directive-processor"></a>Özel konak yönerge işlemcisi ile test etme  
 İlk özel metin şablonu konağı test etmek için oluşturulan yönerge işlemcisi çağıran bir metin şablonu yazma gerekir. Ardından, özel konak çalıştırın, kendisine metin şablonu adını geçirmek ve yönergesi doğru olarak işlendi doğrulayın.  
  
#### <a name="to-create-a-text-template-to-test-the-custom-host"></a>Özel ana bilgisayarı sınamak amacıyla metin şablonu oluşturmak için  
  
1.  Bir metin dosyası oluşturun ve adlandırın `TestTemplateWithDP.tt`. Dosyası oluşturmak için Not Defteri gibi herhangi bir metin düzenleyicisi kullanabilirsiniz.  
  
2.  Aşağıdakileri metin dosyasına ekleyin:  
  
    > [!NOTE]
    >  Metin şablonu programlama dili özel ana bilgisayar adıyla eşleşmesi gerekmez.  
  
    ```csharp  
    Text Template Host Test  
  
    <#@ template debug="true" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>  
    <# //this is the call to the examplemodel directive in the generated directive processor #>  
    <#@ DSLMinimalTest processor="DSLMinimalTestDirectiveProcessor" requires="fileName='<Your Path>\Sample.min'" provides="ExampleModel=ExampleModel" #>  
    <# //uncomment this line to test that the host allows the engine to set the extension #>  
    <# //@ output extension=".htm" #>  
  
    <# //uncomment this line if you want to see the generated transformation class #>  
    <# //System.Diagnostics.Debugger.Break(); #>  
    <# //this code uses the results of the examplemodel directive #>  
    <#  
        foreach ( ExampleElement box in this.ExampleModel.Elements )   
        {   
            WriteLine("Box: {0}", box.Name);  
  
            foreach (ExampleElement linkedTo in box.Targets)  
            {  
                WriteLine("Linked to: {0}", linkedTo.Name);  
            }  
  
            foreach (ExampleElement linkedFrom in box.Sources)  
            {  
                WriteLine("Linked from: {0}", linkedFrom.Name);  
            }  
  
            WriteLine("");  
        }   
    #>  
    ```  
  
    ```vb  
    Text Template Host Test  
  
    <#@ template debug="true" language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>  
  
    <# 'this is the call to the examplemodel directive in the generated directive processor #>  
    <#@ DSLMinimalTest processor="DSLMinimalTestDirectiveProcessor" requires="fileName='<Your Path>\Sample.min'" provides="ExampleModel=ExampleModel" #>  
  
    <# 'Uncomment this line to test that the host allows the engine to set the extension. #>  
    <# '@ output extension=".htm" #>  
  
    <# 'Uncomment this line if you want to see the generated transformation class. #>  
    <# 'System.Diagnostics.Debugger.Break() #>  
  
    <# 'this code uses the results of the examplemodel directive #>  
  
    <#      
       For Each box as ExampleElement In Me.ExampleModel.Elements   
  
           WriteLine("Box: {0}", box.Name)  
  
            For Each LinkedTo as ExampleElement In box.Targets  
                WriteLine("Linked to: {0}", LinkedTo.Name)  
            Next  
  
            For Each LinkedFrom as ExampleElement In box.Sources  
                WriteLine("Linked from: {0}", LinkedFrom.Name)  
            Next  
  
            WriteLine("")  
  
       Next   
    #>  
    ```  
  
3.  Kodla \<bilgisayarınızı yolu > ilk yordamda oluşturduğunuz tasarım özgü dil Sample.min dosyasından yoluna sahip.  
  
4.  Dosyayı kaydedin ve kapatın.  
  
#### <a name="to-test-the-custom-host"></a>Özel ana bilgisayarı sınamak için  
  
1.  Bir komut istemi penceresi açın.  
  
2.  Özel ana bilgisayar için yürütülebilir dosyanın yolunu yazın, ancak henüz ENTER'a basmayın.  
  
     Örneğin, şunu yazın:  
  
     `<YOUR PATH>CustomHost\bin\Debug\CustomHost.exe`  
  
    > [!NOTE]
    >  Adres yazmak yerine, CustomHost.exe dosyasına gözatabilirsiniz içinde **Windows Explorer**ve ardından dosyayı komut istemi penceresine sürükleyin.  
  
3.  Bir boşluk yazın.  
  
4.  Metin şablonu dosyasının yolunu yazın ve ENTER tuşuna basın.  
  
     Örneğin, şunu yazın:  
  
     `<YOUR PATH>TestTemplateWithDP.txt`  
  
    > [!NOTE]
    >  Adres yazmak yerine, TestTemplateWithDP.txt dosyasına gözatabilirsiniz içinde **Windows Explorer**ve ardından dosyayı komut istemi penceresine sürükleyin.  
  
     Özel ana bilgisayar uygulamasını çalışır ve metin şablonu dönüştürme süreci başlatılır.  
  
5.  İçinde **Windows Explorer**, TestTemplateWithDP.txt dosyasını içeren klasöre göz atın.  
  
     Klasör, dosya TestTemplateWithDP1.txt da içerir.  
  
6.  Metin şablonu dönüştürme sonuçlarını görmek için bu dosyayı açın.  
  
     Oluşturulan metin çıktısı sonuçlarını görüntülenir ve aşağıdaki gibi görünmelidir:  
  
    ```  
    Text Template Host Test  
  
    Box: ExampleElement1  
    Linked to: ExampleElement2  
  
    Box: ExampleElement2  
    Linked from: ExampleElement1  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Özel Metin Şablonu Konağı Oluşturma](../modeling/walkthrough-creating-a-custom-text-template-host.md)
