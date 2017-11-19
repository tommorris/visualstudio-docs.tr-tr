---
title: MSBuild | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, about MSBuild
- MSBuild, overview
ms.assetid: e39f13f7-1e1d-4435-95ca-0c222bca071c
caps.latest.revision: "59"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 45714799a518cefa1edb7164437af7c4a067b0e4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild"></a>MSBuild
[!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] Uygulamaları oluşturmak için bir platformdur. Olarak da bilinen MSBuild olduğundan, bu altyapı yapı platformunu nasıl işler ve yazılım derlemeler denetleyen bir proje dosyası için bir XML Şeması sağlar. Visual Studio MSBuild kullanır, ancak Visual Studio bağımlı değil. Proje ya da çözüm dosyanızı MSBuild.exe çağırarak düzenlemek ve ürünleri, Visual Studio yüklü olmayan ortamlarda oluşturun.  
  
 Visual Studio MSBuild yüklemek ve yönetilen projeler derlemek için kullanır. Proje dosyaları (.csproj, .vbproj, vcxproj ve diğerleri) Visual Studio IDE kullanarak bir projeyi derlerken yürütülen MSBuild XML kodu içerir. Visual Studio projeleri gerekli tüm ayarları almak ve işlemler tipik geliştirme iş yapmak için derleme, ancak genişletme veya Visual Studio içinde veya bir XML düzenleyicisini kullanarak bunları değiştirmek.  
  
 C++ için MSBuild hakkında bilgi için bkz: [MSBuild (Visual C++)](/cpp/build/msbuild-visual-cpp).  
  
 Visual Studio IDE yerine bir MSBuild komut satırını kullanarak derlemeler çalıştırdığınızda, aşağıdaki örneklerde gösterilmiştir.  
  
-   Visual Studio yüklü değil.  
  
-   MSBuild 64-bit sürümünü kullanmak istiyorsunuz. MSBuild bu sürümü genellikle gerekli değildir, ancak daha fazla belleğe erişmeye MSBuild sağlar.  
  
-   İçinde birden çok işlem derleme çalıştırmak isteyebilirsiniz. Ancak, C++ ve C# projeleri üzerinde aynı sonucu elde etmek için IDE kullanabilirsiniz.  
  
-   Derleme Sistemi değiştirmek istediğiniz. Örneğin, aşağıdaki eylemleri etkinleştirmek isteyebilirsiniz:  
  
    -   Derleyici düşmeden önce dosyaları önişle.  
  
    -   Derleme çıktı farklı bir konuma kopyalayın.  
  
    -   Sıkıştırılmış dosyalar yapı çıkışlarından oluşturun.  
  
    -   İşlem Sonrası adımı uygulayın. Örneğin, farklı bir sürüm ile bir derlemeyi damga isteyebilirsiniz.  
  
 Visual Studio IDE içinde kod yazabilirsiniz ancak MSBuild kullanarak, çalışma oluşturur. Başka bir alternatif olarak, geliştirme bilgisayarınızda IDE kodda derleme ancak birden çok geliştiricilerden tümleşiktir kodu oluşturmak için MSBuild komut satırında kullanın.  
  
> [!NOTE]
>  Team Foundation Build otomatik olarak derleme, test ve uygulamanızı dağıtmak için kullanabilirsiniz. Otomatik olarak derlemeleri geliştiricileri (örneğin, bir sürekli tümleştirme stratejisinin parçası olarak) kodunuzu iade ettiğinizde çalıştırabilir veya bir zamanlama (örneğin, bir gecelik yapı doğrulama testleri yapı) according, yapı sistem olabilir. Team Foundation Build kodunuzu MSBuild kullanarak derler. Daha fazla bilgi için bkz: [uygulamayı derlediğinizde](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692).  
  
 Bu konu MSBuild genel bir bakış sağlar. Giriş bir öğretici için bkz: [izlenecek yol: MSBuild kullanma](../msbuild/walkthrough-using-msbuild.md).  
  
 **Bu konudaki**  
  
-   [Bir komut isteminde MSBuild kullanma](#BKMK_CommandPrompt)  
  
-   [Proje dosyası](#BKMK_ProjectFile)  
  
    -   [Özellikleri](#BKMK_Properties)  
  
    -   [Öğeleri](#BKMK_Items)  
  
    -   [Görevler](#BKMK_Tasks)  
  
    -   [Hedefleri](#BKMK_Targets)  
  
-   [Yapı günlükleri](#BKMK_BuildLogs)  
  
-   [Visual Studio'da MSBuild kullanma](#BKMK_VisualStudio)  
  
-   [Çoklu sürüm desteği](#BKMK_Multitargeting)  
  
##  <a name="BKMK_CommandPrompt"></a>Bir komut isteminde MSBuild kullanma  
 Çalıştırmak için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bir komut isteminde, bir proje dosyası MSBuild.exe için uygun komut satırı seçenekleri ile birlikte geçirin. Komut satırı seçenekleri özelliklerini ayarlamak için belirli hedefler yürütün ve yapı işlemini denetleyen diğer seçenekleri sağlar. Örneğin, dosyayı oluşturmak için aşağıdaki komut satırı sözdizimi kullanırsınız `MyProj.proj` ile `Configuration` özelliğini `Debug`.  
  
```  
MSBuild.exe MyProj.proj /property:Configuration=Debug  
```  
  
 Hakkında daha fazla bilgi için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] komut satırı seçenekleri bkz [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md).  
  
> [!IMPORTANT]
>  Bir proje indirmeden önce kodu güvenilirliğini belirler.  
  
##  <a name="BKMK_ProjectFile"></a>Proje dosyası  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]kolay ve Genişletilebilir bir XML tabanlı proje dosyası biçimi kullanır. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Proje dosyası biçimi oluşturulacak olan öğeleri açıklayan geliştiriciler sağlar ve ayrıca nasıl bunlar farklı işletim sistemleri ve yapılandırmalar için oluşturulacak. Ayrıca, proje dosyası biçimi ayrı dosyalara oluşturmak ve böylece derlemeler üründeki farklı projeler arasında tutarlı bir şekilde gerçekleştirilebilir geliştiriciler Yazar yeniden kullanılabilir derleme kuralları olanak sağlar.  
  
 Aşağıdaki bölümlerde bazı temel öğelerinin açıklanmaktadır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası biçimi. Temel Proje dosyasının nasıl oluşturulacağı hakkında bir öğretici için bkz: [izlenecek yol: sıfırdan MSBuild proje dosyası oluşturma](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md).  
  
###  <a name="BKMK_Properties"></a>Özellikleri  
 Özellikler derlemeleri yapılandırmak için kullanılan anahtar/değer çiftlerini temsil eder. Özellikler, bir alt öğesi olarak özelliğinin adı olan bir öğeyi oluşturarak bildirildiğinde bir [PropertyGroup](../msbuild/propertygroup-element-msbuild.md) öğesi. Örneğin, aşağıdaki kod adlı bir özellik oluşturur `BuildDir` değerine sahip `Build`.  
  
```xml  
<PropertyGroup>  
    <BuildDir>Build</BuildDir>  
</PropertyGroup>  
```  
  
 Girerek bir özellik koşullu tanımlayabilirsiniz bir `Condition` öğesinde özniteliği. Koşullu öğeler içeriğini için koşulu değerlendirir yoksayılır `true`. Aşağıdaki örnekte, `Configuration` öğesi henüz tanımlanmamışsa tanımlanır.  
  
```xml  
<Configuration  Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
```  
  
 Özellikler başvurulabilir proje dosyası biçiminde bir sözdizimi kullanarak (*PropertyName*). Örneğin, kullanarak önceki örneklerde özelliklerinde başvurusu yapabilir `$(BuildDir)` ve `$(Configuration)`.  
  
 Özellikleri hakkında daha fazla bilgi için bkz: [MSBuild özellikleri](../msbuild/msbuild-properties.md).  
  
###  <a name="BKMK_Items"></a>Öğeleri  
 Öğeleri yapı sistemine girdiler ve genellikle dosyaları temsil eder. Öğeleri öğesi türlerine, kullanıcı tanımlı öğeyi adlarına göre gruplandırılır. Bu öğe türleri parametre olarak bireysel öğeleri Yapı işleminin adımları gerçekleştirmek için kullandığınız görevler için kullanılabilir.  
  
 Öğeler bir alt öğesi olarak öğesi türünün adı olan bir öğeyi oluşturarak proje dosyasında bildirildiğinde bir [ItemGroup](../msbuild/itemgroup-element-msbuild.md) öğesi. Örneğin, aşağıdaki kod adlı bir öğe türü oluşturur `Compile`, iki dosya içerir.  
  
```xml  
<ItemGroup>  
    <Compile Include = "file1.cs"/>  
    <Compile Include = "file2.cs"/>  
</ItemGroup>  
```  
  
 Öğe türleri başvuruda bulunabilir proje dosyası sözdizimini kullanarak @(*ItemType*). Örneğin, örnekteki öğesi türünü kullanarak başvuruda `@(Compile)`.  
  
 MSBuild içinde öğe ve öznitelik adları büyük/küçük harf duyarlıdır. Ancak, özelliği, öğe ve meta veri adlarının değildir. Aşağıdaki örnek, öğe türü oluşturur `Compile`, `comPile`, veya herhangi diğer büyük/küçük harf ve öğe türü "one.cs;two.cs" değeri verir.  
  
```xml  
<ItemGroup>  
  <Compile Include="one.cs" />  
  <comPile Include="two.cs" />  
</ItemGroup>  
```  
  
 Öğeler joker karakterler kullanarak bildirilebilir ve daha gelişmiş yapılandırma senaryoları için ek meta veriler içerebilir. Öğeleri hakkında daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).  
  
###  <a name="BKMK_Tasks"></a>Görevler  
 Görevlerdir birimleri yürütülebilir dosyasının kod [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeler derleme işlemleri gerçekleştirmek için kullanın. Örneğin, bir görev, girdi dosyalarını derlemek veya bir dış aracı çalıştırın. Görevler yeniden kullanılabilir ve bunlar farklı projelerde farklı geliştiriciler tarafından paylaşılabilir.  
  
 Görev Yürütme mantığını yönetilen kodda yazılır ve eşlenmiş [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] kullanarak [UsingTask](../msbuild/usingtask-element-msbuild.md) öğesi. Arabirimini uygulayan bir yönetilen türü yazarak kendi görev yazabilirsiniz <xref:Microsoft.Build.Framework.ITask> arabirimi. Görevler yazma hakkında daha fazla bilgi için bkz: [görev yazma](../msbuild/task-writing.md).  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]gereksinimlerinize uyacak şekilde değiştirebilirsiniz ortak görevleri içerir.  Örnekler [kopya](../msbuild/copy-task.md), dosyaları kopyalar [MakeDir](../msbuild/makedir-task.md), dizinleri, oluşturur ve [Csc](../msbuild/csc-task.md), Visual C# kaynak kodu dosyaları derler. Kullanım bilgileri ile birlikte kullanılabilir görevler listesi için bkz: [görev başvurusu](../msbuild/msbuild-task-reference.md).  
  
 Bir görev yürütülür bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bir alt öğesi olarak görev adı olan bir öğeyi oluşturarak proje dosyası bir [hedef](../msbuild/target-element-msbuild.md) öğesi. Görevleri genellikle öğesinin özniteliklerini geçirilen parametreleri kabul edin. Her ikisi de [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] özellikleri ve öğeleri parametre olarak kullanılır. Örneğin, aşağıdaki çağrıları kod [MakeDir](../msbuild/makedir-task.md) görev ve değeri geçirir `BuildDir` önceki örnekte bildirildi özelliği.  
  
```xml  
<Target Name="MakeBuildDirectory">  
    <MakeDir  Directories="$(BuildDir)" />  
</Target>  
```  
  
 Görevler hakkında daha fazla bilgi için bkz: [görevleri](../msbuild/msbuild-tasks.md).  
  
###  <a name="BKMK_Targets"></a>Hedefleri  
 Hedefleri görevleri belirli bir sırada gruplamak ve proje dosyası bölümlerini yapı işlemine giriş noktaları olarak kullanıma sunar. Hedefler, genellikle okunabilirliğini artırmak ve genişletme için izin vermek için mantıksal bölümlere gruplandırılır. Derleme adımları hedefleri yeni her hedef kodun bu bölümü kopyalama olmadan diğer hedeflerden yapılandırma işleminin bir parçası çağrısı olanak sağlar. Örneğin, birkaç giriş noktaları oluşturma işlemine oluşturulacak başvuruları gerektiriyorsa, derlemeler başvuruları bir hedef oluşturmak ve ardından hedefleyen burada istedi her giriş noktasından çalıştırın.  
  
 Hedefleri kullanarak proje dosyasında bildirildiğinde [hedef](../msbuild/target-element-msbuild.md) öğesi. Örneğin, aşağıdaki kod adlı bir hedef oluşturur `Compile`, ardından çağıran [Csc](../msbuild/csc-task.md) önceki örnekte bildirildi öğe listesinden olan görev.  
  
```xml  
<Target Name="Compile">  
    <Csc Sources="@(Compile)" />  
</Target>  
```  
  
 Daha gelişmiş senaryolarda hedefleri birbirine arasındaki ilişkileri açıklar ve böylece bu hedef güncel ise yapı işleminin tüm bölümleri atlanabilir bağımlılık analiz gerçekleştirmek için kullanılabilir. Hedefleri hakkında daha fazla bilgi için bkz: [hedefleri](../msbuild/msbuild-targets.md).  
  
##  <a name="BKMK_BuildLogs"></a>Yapı günlükleri  
 Derleme hataları, uyarıları ve iletileri konsol veya başka bir çıkış aygıtı oturum açabilir. Daha fazla bilgi için bkz: [yapı günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md) ve [Msbuild'de günlük kaydı](../msbuild/logging-in-msbuild.md).  
  
##  <a name="BKMK_VisualStudio"></a>Visual Studio'da MSBuild kullanma  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]kullanan [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] yönetilen projeleri hakkında yapılandırma bilgileri depolamak için proje dosyası biçimi. Proje eklenen veya değiştirilen kullanarak ayarları [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] arabirimi yansıtılır. * oluşturulan proj dosyasını her proje için. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]barındırılan bir örneğini kullanan [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] yönetilen projeler derlemek için. Bir yönetilen projenin oluşturulabilir, yani [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] veya bir komut isteminde (olsa bile [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklü değilse), ve sonuçları aynı olacaktır.  
  
 Visual Studio'da MSBuild kullanma hakkında bir öğretici için bkz: [izlenecek yol: MSBuild kullanma](../msbuild/walkthrough-using-msbuild.md).  
  
##  <a name="BKMK_Multitargeting"></a>Çoklu sürüm desteği  
 Visual Studio kullanarak bir uygulamayı .NET Framework'ün birkaç sürümlerini herhangi biri üzerinde çalışacak şekilde derleyebilirsiniz. Örneğin, bir uygulamayı .NET Framework 2.0 32 bit platformda çalışacak şekilde derleyebilir ve .NET Framework 4. 5 ' 64-bit platformu üzerinde çalıştırmak için aynı uygulama derleyebilirsiniz. Birden fazla framework derleme becerisini çoklu sürüm desteği olarak adlandırılır.  
  
 Çoklu sürüm desteği avantajlarından bazıları şunlardır:  
  
-   Önceki .NET Framework sürümleri, örneğin, sürüm 2.0, 3.0 ve 3.5 hedefleyen uygulamalar geliştirebilirsiniz.  
  
-   .NET Framework, örneğin, Silverlight dışında çerçeveleri hedefleyebilirsiniz.  
  
-   Hedef alabilirsiniz bir *framework profili*, bir hedef framework'ün önceden tanımlanmış bir alt kümesidir.  
  
-   Geçerli .NET Framework sürümü için bir hizmet paketi yayımlanırsa hedefleyebilir.  
  
-   Çoklu sürüm desteği uygulama hedef framework ve platform kullanılabilir olan işlevsellik kullanan güvence altına alır.  
  
 Daha fazla bilgi için bkz: [çoklu sürüm desteği](../msbuild/msbuild-multitargeting-overview.md).  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[İzlenecek yol: sıfırdan MSBuild proje dosyası oluşturma](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)|Temel Proje dosyasını artımlı olarak, yalnızca bir metin düzenleyicisi kullanarak oluşturmanız gösterilmektedir.|  
|[İzlenecek yol: MSBuild kullanma](../msbuild/walkthrough-using-msbuild.md)|MSBuild yapı taşlarını tanıtır ve yazma, yönetmek ve Visual Studio IDE kapatmadan MSBuild projelerine hata ayıklama gösterilmektedir.|  
|[MSBuild kavramları](../msbuild/msbuild-concepts.md)|MSBuild dört temellerini sunar: özellikler, öğeleri, hedefler ve görevler.|  
|[Öğeleri](../msbuild/msbuild-items.md)|Genel kavramları açıklar [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] dosya biçimi ve nasıl parçaları bir araya getireceğinizi.|  
|[MSBuild özellikleri](../msbuild/msbuild-properties.md)|Özellikler ve özellik koleksiyonları tanıtır. Yapılandırmak için kullanılan anahtar/değer çiftlerinin derlemeler özelliklerdir.|  
|[Hedefleri](../msbuild/msbuild-targets.md)|Belirli bir sırada görevleri gruplandırın ve bölümler komut satırında çağrılacak derleme işleminin etkinleştirmek açıklanmaktadır.|  
|[Görevler](../msbuild/msbuild-tasks.md)|Bir birim tarafından kullanılan yürütülebilir kod oluşturmayı gösteren [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] atomik yapı işlemleri gerçekleştirmek için.|  
|[Koşullar](../msbuild/msbuild-conditions.md)|Nasıl kullanılacağı açıklanır `Condition` MSBuild öğenin özniteliği.|  
|[Gelişmiş kavramlar](../msbuild/msbuild-advanced-concepts.md)|Toplu işleme, Dönüşümlerin, çoklu sürüm desteği ve diğer gelişmiş teknikleri gerçekleştirmek sayısını gösterir.|  
|[Msbuild'de günlük kaydı](../msbuild/logging-in-msbuild.md)|Derleme olayları, iletileri ve hata günlüğünü açıklar.|  
|[Ek kaynaklar](../msbuild/additional-msbuild-resources.md)|MSBuild hakkında daha fazla bilgi için topluluk ve Destek kaynakları listeler.|  
  
## <a name="reference"></a>Başvuru  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)  
 Başvuru bilgileri içeren konulara bağlantılar.  
  
 [Sözlük](msbuild-glossary.md) yaygın MSBuild koşulları tanımlar.
