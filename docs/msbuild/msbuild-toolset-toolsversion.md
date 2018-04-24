---
title: MSBuild araç takımı (ToolsVersion) | Microsoft Docs
ms.custom: ''
ms.date: 01/31/2018
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, multitargeting
- targeting a specific .NET framework [MSBuild]
- MSBuild, targeting a specific .NET framework
- multitargeting [MSBuild]
ms.assetid: 40040ee7-4620-4043-a6d8-ccba921421d1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e8d46c8d3e076e194369cce2e01325f53aa6a36
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="msbuild-toolset-toolsversion"></a>MSBuild Araç Takımı (ToolsVersion)
MSBuild araç takımı görevleri, hedefler ve araçları, bir uygulama oluşturmak için kullanır. Genellikle, MSBuild araç takımı microsoft.common.tasks dosya, microsoft.common.targets dosya ve csc.exe ve vbc.exe gibi derleyicileri içerir. Çoğu Toolsets, .NET Framework'ün birden fazla sürümünü ve birden fazla sistem platformu uygulamaları derlemek için kullanılabilir. Ancak, MSBuild 2.0 araç takımı, yalnızca .NET Framework 2.0 hedeflemek için kullanılabilir.  
  
## <a name="toolsversion-attribute"></a>ToolsVersion özniteliği  
 Araç takımında yer belirtin `ToolsVersion` özniteliği [proje](../msbuild/project-element-msbuild.md) proje öğesi. Aşağıdaki örnek proje MSBuild 15.0 araç setini kullanarak oluşturulması belirtir.  
  
```xml  
<Project ToolsVersion="15.0" ... </Project>  
``` 

> [!NOTE] 
> Bazı proje türleri kullan `sdk` yerine özniteliği `ToolsVersion`. Daha fazla bilgi için bkz: [paketleri, meta verileri ve çerçeveleri](/dotnet/core/packages) ve [csproj eklemeler biçimlendirmek için .NET Core](/dotnet/core/tools/csproj).
  
## <a name="how-the-toolsversion-attribute-works"></a>ToolsVersion özniteliği nasıl çalışır?  
 Visual Studio'da bir proje oluşturduğunuzda veya mevcut bir proje yükseltme adlı bir öznitelik `ToolsVersion` otomatik olarak eklenir projede dosya ve değerine karşılık gelen Visual Studio sürümü dahil MSBuild sürümü. Daha fazla bilgi için bkz: [belirli bir .NET Framework sürümü hedefleme](../ide/targeting-a-specific-dotnet-framework-version.md).  
  
 Zaman bir `ToolsVersion` değeri bir proje dosyasında tanımlanmış, MSBuild Projesi için kullanılabilir araç takımı özelliklerinin değerlerini belirlemek için bu değeri kullanır. Bir araç takımı özelliği `$(MSBuildToolsPath)`, .NET Framework Araçları yolunu belirtir. Yalnızca bu araç takımı özelliği (veya `$(MSBuildBinPath)`), gereklidir.  
  
 Visual Studio 2013'ten başlayarak, MSBuild araç takımının sürüm Visual Studio sürüm numarası aynı değil. Bu araç takımı Visual Studio'dan ve proje dosyasında belirtilen araç takımının sürüm ne olursa olsun komut satırında MSBuild varsayılan değeri.  Bu davranış, /ToolsVersion bayrağı kullanılarak geçersiz kılınabilir. Daha fazla bilgi için bkz: [ToolsVersion ayarlarını geçersiz kılma](../msbuild/overriding-toolsversion-settings.md).  
  
 Aşağıdaki örnekte, MSBuild kullanarak Microsoft.CSharp.targets dosyayı bulur `MSBuildToolsPath` ayrılmış özelliği.  
  
```xml  
<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />  
```  
  
 Değeri değiştirebilirsiniz `MSBuildToolsPath` özel araç takımı tanımlayarak. Daha fazla bilgi için bkz: [standart ve özel araç takımı yapılandırmaları](../msbuild/standard-and-custom-toolset-configurations.md)  
  
 Ne zaman komut satırında bir çözümü oluşturmak ve belirtin bir `ToolsVersion` msbuild.exe için tüm proje ve proje proje bağımlılıklarını göre yerleşik olan `ToolsVersion`, çözümdeki her projeye kendi belirtse dahi `ToolsVersion`. Tanımlamak için `ToolsVersion` değeri bir proje başına temelinde, bkz: [ToolsVersion ayarlarını geçersiz kılma](../msbuild/overriding-toolsversion-settings.md).  
  
 `ToolsVersion` Özniteliği proje geçiş için de kullanılır. Visual Studio 2010'da Visual Studio 2008 projesine açarsanız, örneğin, proje dosyası ToolsVersion içerecek şekilde güncelleştirilmiştir "4.0" =. Ardından bu projeyi Visual Studio 2008'de açmaya çalışırsanız, yükseltilen tanımıyor `ToolsVersion` ve bu nedenle öznitelik hala 3.5 ayarlandı ancak gibi projesi oluşturur.  
  
 Visual Studio 2010 ve Visual Studio 2012 ToolsVersion 4.0 kullanın. Visual Studio 2013 ToolsVersion 12.0 birini kullanır. ToolsVersion 14.0 Visual Studio 2015 ve Visual Studio 2017 ToolsVersion 15.0 kullanır. Çoğu durumda, Visual Studio değişiklik yapmadan birden fazla sürümünü projesinde açabilirsiniz. Visual Studio her zaman doğru araç takımı kullanır, ancak kullanılan sürümü proje dosyasında sürüm eşleşmiyorsa size bildirilecek. Çoğu durumda Toolsets uyumlu neredeyse her durumda, bu uyarıyı zararsız aynıdır.  
  
 Bu konunun ilerleyen bölümlerinde açıklanan, alt-toolsets otomatik olarak kullanmak için Araçlar hangi kümesi yapı çalıştırıldığı bağlamına dayalı geçiş yapmak MSBuild izin verir. Örneğin, Visual Studio 2012'de, Visual Studio 2010'da, açıkça proje dosyası değiştirmek zorunda kalmadan çalıştırıldığında çalıştırıldığında MSBuild daha yeni bir araç kümesi kullanır.  
  
## <a name="toolset-implementation"></a>Araç takımı uygulama  
 Bir araç takımı, çeşitli araçları, hedefler ve araç takımı yapmak görevleri yollarını seçerek uygulayın. MSBuild tanımlar araç takımı araçları aşağıdaki kaynaklardan gelen:  
  
-   .NET Framework klasör.  
  
-   Ek yönetilen araçları.  
  
 Yönetilen Araçlar ResGen.exe ve TlbImp.exe içerir.  
  
 MSBuild araç takımı erişmek için iki yöntem sunar:  
  
-   Araç takımı özelliklerini kullanarak  
  
-   Kullanarak <xref:Microsoft.Build.Utilities.ToolLocationHelper> yöntemleri  
  
 Araç takımı özelliklerini araçları yollarını belirtin. MSBuild Visual Studio 2017'dan başlayarak, sabit bir konumdaki artık yok. Varsayılan olarak, Visual Studio yükleme konumuna göre MSBuild\15.0\Bin klasöründe bulunur. Önceki sürümlerde, MSBuild değerini kullanır `ToolsVersion` araç takımı özelliklerini ayarlamak için kayıt defteri anahtarındaki bilgiler ilgili kayıt defteri anahtarını ve ardından kullanır bulmak için proje dosyasında özniteliği. Örneğin, varsa `ToolsVersion` değerine sahip `12.0`, sonra da MSBuild araç takımı özelliklerini bu kayıt defteri anahtarı göre ayarlar: HKLM\Software\Microsoft\MSBuild\ToolsVersions\12.0.  
  
 Bu araç takımı özellikleri şunlardır:  
  
-   `MSBuildToolsPath` MSBuild ikili dosyalarının yolunu belirtir.  
  
-   `SDK40ToolsPath` MSBuild için ek yönetilen araçları yolunu belirtir (hangi 4.0 veya 4.5 olabilir) 4.x.  
  
-   `SDK35ToolsPath` MSBuild 3.5 için ek yönetilen araçları yolunu belirtir.  
  
 Alternatif olarak, araç takımı program aracılığıyla yöntemlerini çağırarak belirleyebilirsiniz <xref:Microsoft.Build.Utilities.ToolLocationHelper> sınıfı. Sınıfı, bu yöntemleri içerir:  
  
-   <xref:Microsoft.Build.Utilities.ToolLocationHelper.GetPathToDotNetFramework%2A> .NET Framework klasörünün yolunu döndürür.  
  
-   <xref:Microsoft.Build.Utilities.ToolLocationHelper.GetPathToDotNetFrameworkFile%2A> .NET Framework klasöründe bir dosyanın yolunu döndürür.  
  
-   <xref:Microsoft.Build.Utilities.ToolLocationHelper.GetPathToDotNetFrameworkSdk%2A> Yönetilen Araçları klasörünün yolunu döndürür.  
  
-   <xref:Microsoft.Build.Utilities.ToolLocationHelper.GetPathToDotNetFrameworkSdkFile%2A> genellikle yönetilen Araçları klasöründe bulunan bir dosyanın yolunu döndürür.  
  
-   <xref:Microsoft.Build.Utilities.ToolLocationHelper.GetPathToBuildTools%2A> derleme araçları yolunu döndürür.  
  
### <a name="sub-toolsets"></a>Sub toolsets  
 MSBuild 15.0 önceki sürümler için MSBuild, temel Araçlar yolunu belirtmek için bir kayıt defteri anahtarı kullanır. Bir alt anahtarı varsa, MSBuild ek araçlarını içeren bir alt-toolset yolunu belirtmek için kullanır. Bu durumda, her iki anahtarı tanımlı özellik tanımları birleştirerek araç takımı tanımlanır.  
  
> [!NOTE]
>  Araç takımı özellik adları çakışıyorsa, alt anahtar yolu için tanımlanan değer kök anahtar yolunu tanımlanan değerini geçersiz kılar.  
  
 Sub toolsets varken etkin hale `VisualStudioVersion` özelliği oluşturun. Bu özellik, bu değerlerden birini alabilir:  
  
-   .NET Framework 4 alt toolset "10.0" belirtir  
  
-   .NET Framework 4.5 alt toolset "11.0" belirtir  
  
-   .NET Framework 4.5.1 alt toolset "12,0" belirtir 
  
 Sub toolsets 10.0 ve 11.0 ToolsVersion 4.0 ile birlikte kullanılmalıdır. Sonraki sürümlerde, alt-araç takımının sürüm ve ToolsVersion eşleşmelidir.  
  
 Bir derleme sırasında MSBuild otomatik olarak belirler ve için varsayılan bir değer ayarlar `VisualStudioVersion` zaten tanımlanmışsa özelliği.  
  
 MSBuild için aşırı sağlar `ToolLocationHelper` ekleme yöntemleri bir `VisualStudioVersion` değeri bir parametre olarak numaralandırılır  
  
 Sub toolsets .NET Framework 4. 5 ' kullanılmaya başlanmıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Standart ve özel araç takımı yapılandırmaları](../msbuild/standard-and-custom-toolset-configurations.md)   
 [Çoklu sürüm desteği](../msbuild/msbuild-multitargeting-overview.md)
