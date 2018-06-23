---
title: Yapınızın özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bceb3b-14fb-455c-805a-63acefa4b3ed
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ed794a50df41e6a8c6817a9e10d93edb7606b0e6
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326832"
---
# <a name="customize-your-build"></a>Derlemenizi özelleştirme

Standart kullanmak MSBuild projelerine yapı işlemi (içeri aktarma `Microsoft.Common.props` ve `Microsoft.Common.targets`) yapı işleminizin özelleştirmek için kullanılan birkaç genişletilebilirlik kancaları sahip.

## <a name="adding-arguments-to-command-line-msbuild-invocations-for-your-project"></a>Projeniz için komut satırı MSBuild çağrılarına bağımsız değişkenleri ekleme

A `Directory.Build.rsp` dosyasını veya kaynak dizin yukarıda projenizin komut satırı derlemeleri için uygulanır. Ayrıntılar için bkz [MSBuild yanıt dosyaları](../msbuild/msbuild-response-files.md#directorybuildrsp).

## <a name="directorybuildprops-and-directorybuildtargets"></a>Directory.Build.props ve Directory.Build.targets

MSBuild 15. sürümden önceki sürümler çözümünüz projelerine yeni, özel bir özellik sağlamak istiyorsanız çözümdeki her proje dosyası el ile bu özellik için bir başvuru ekleyin içeriyor. Veya özelliğinde tanımlamak zorunda kalındı bir *.props* dosya ve açıkça alma *.props* başka şeylerin çözümdeki her projeye dosyasında.

Bununla birlikte, artık yeni bir özellik tek bir adımda her proje bir tek dosyalı çağrılan içinde tanımlayarak ekleyebileceğiniz *Directory.Build.props* kök klasöründe kaynağınız içerir. MSBuild çalıştığında, *Microsoft.Common.props* directory yapınızı arar *Directory.Build.props* dosyası (ve *Microsoft.Common.targets* arar *Directory.Build.targets*). Bulursa, özelliği alır. *Directory.Build.props* bir dizini altındaki projelerine özelleştirmeleri sağlar kullanıcı tanımlı bir dosya.

### <a name="directorybuildprops-example"></a>Directory.Build.props örneği

Örneğin, tüm projeleriniz yeni Roslyn erişmek için etkinleştirmek istiyorsanız **/ belirleyici** özelliği (Roslyn açığa `CoreCompile` hedef özelliği tarafından `$(Deterministic)`), aşağıdakileri yapabilirsiniz.

1. Yeni bir dosya olarak adlandırılan, depo kök dizininde oluşturun *Directory.Build.props*.
2. Aşağıdaki XML dosyasına ekleyin.

  ```xml
  <Project>
    <PropertyGroup>
      <Deterministic>true</Deterministic>
    </PropertyGroup>
  </Project>
  ```
3. MSBuild çalıştırın. Projenizin varolan aktarımlarının *Microsoft.Common.props* ve *Microsoft.Common.targets* dosyasını bulun ve içe aktarın.

### <a name="search-scope"></a>Arama kapsamı

Ararken bir *Directory.Build.props* dosya, MSBuild anlatılmaktadır dizin yapısını yukarı doğru proje konumdan (`$(MSBuildProjectFullPath)`), onu bulduktan sonra durdurma bir *Directory.Build.props* dosya. Örneğin, varsa, `$(MSBuildProjectFullPath)` olan *c:\users\username\code\test\case1*MSBuild başlangıç var. arama ve ardından arama dizin yapısını yukarı kadar bulunan bir *Directory.Build.props* aşağıdaki dizin yapısını olduğu gibi dosya.

```
c:\users\username\code\test\case1
c:\users\username\code\test
c:\users\username\code
c:\users\username
c:\users
c:\
```

Çözüm dosyası konumu için ilgisiz *Directory.Build.props*.

### <a name="import-order"></a>İçeri aktarma sırası

*Directory.Build.props* uygulamasında çok erken alınan *Microsoft.Common.props*, daha sonra tanımlanan özellikleri için kullanılamaz. Bu nedenle, henüz tanımlanmamış (ve dolayısıyla için boş değerlendirecek) özelliklerine başvuran kaçının.

*Directory.Build.targets* üzerinden içe aktarılan *Microsoft.Common.targets* aldıktan sonra *.targets* NuGet paketlerini dosyalarından. Bu nedenle, özellikleri ve yapı mantığı çoğunda tanımlanmış hedefleri geçersiz kılmak için kullanılabilir, ancak bazen proje dosyası içinde özelleştirmeler son içeri aktardıktan sonra yapmanız gerekebilir.

### <a name="use-case-multi-level-merging"></a>Kullanım örneği: çok düzeyli birleştirme

Bu standart çözümü yapı olduğunu varsayalım:

```
\
  MySolution.sln
  Directory.Build.props     (1)
  \src
    Directory.Build.props   (2-src)
    \Project1
    \Project2
  \test
    Directory.Build.props   (2-test)
    \Project1Tests
    \Project2Tests
```

Tüm projeleri için ortak olan özellikler için uygun olabilir *(1)*, ortak özelliklerini *src* projeleri *(2-src)* ve ortak özelliklerini  *Test* projeleri *(2-test)*.

MSBuild doğru "İç" dosyaları birleştirmek için (*2-src* ve *2 test*) "dış" dosyasıyla (*1*), bir kez MSBuild bir bulduğunudikkatealmanızgerekir*Directory.Build.props* dosyasını durdurur daha fazla tarama. Taramaya devam et ve dış dosyasına birleştirmek için bu iki iç dosyalarıyla koyun:

`<Import Project="$([MSBuild]::GetPathOfFileAbove('Directory.Build.props', '$(MSBuildThisFileDirectory)../'))" />`

MSBuild'ın genel yaklaşım özetini aşağıdaki gibidir:

- Belirli bir proje için ilk MSBuild bulur *Directory.Build.props* yukarı isteğe bağlı olarak çözümü yapısında öndeğerlerini birleştirir ve daha fazla bilgi için taramayı durdurur
- Bulunan ve ardından birleştirildiği için birden çok düzeyi isteyip istemediğinizi [ `<Import...>` ](../msbuild/property-functions.md#msbuild-getpathoffileabove) (yukarıda gösterilen) "İç" dosyasından "dış" dosyası
- "Dış" dosya kendisi olursa Ayrıca, üzerinde bir şey içeri sonra taramayı var. durdurur
- Tarama ve birleştirme işlemi denetlemek için kullandığı `$(DirectoryBuildPropsPath)` ve `$(ImportDirectoryBuildProps)`

Ya da daha basit bir şekilde: ilk *Directory.Build.props* , herhangi bir şey içe aktarmaz olduğu yere MSBuild durdurur.

## <a name="msbuildprojectextensionspath"></a>MSBuildProjectExtensionsPath

Varsayılan olarak, `Microsoft.Common.props` alır `$(MSBuildProjectExtensionsPath)$(MSBuildProjectFile).*.props` ve `Microsoft.Common.targets` alır `$(MSBuildProjectExtensionsPath)$(MSBuildProjectFile).*.targets`. Varsayılan değer olan `MSBuildProjectExtensionsPath` olan `$(BaseIntermediateOutputPath)`, `obj/`. Bu NuGet paketleri ile teslim mantığı yapı başvurmak için kullandığı mekanizmasıdır diğer bir deyişle, geri yükleme sırasında oluşturduğu `{project}.nuget.g.props` paket içeriğini başvuran dosyaları.

Bu genişletilebilirlik mekanizmasını özelliği ayarlanarak devre dışı bırakılabilir `ImportProjectExtensionProps` için `false` içinde bir `Directory.Build.props` veya almadan önce `Microsoft.Common.props`.

> [!NOTE]
> MSBuildProjectExtensionsPath içeri aktarmalar devre dışı bırakma NuGet paketlerini projenize uygulama teslim yapı mantığı engeller. Bazı NuGet paketleri kendi işlevini gerçekleştirmesi için yapı mantığı gerektirir ve bu devre dışı bırakıldığında gereksiz işlenir.

## <a name="user-file"></a>.kullanıcı dosyası

Microsoft.Common.CurrentVersion.targets alır `$(MSBuildProjectFullPath).user` yanındaki projenizi ek uzantıya sahip bir dosya oluşturabilmesi için varolup olmadığını. Böylece gelecekteki maintainers bu uzantı mekanizması hakkında bilmek zorunda değilsiniz projesini kendisini değiştirme, kaynak denetimine planladığınız uzun vadeli değişiklikleri için tercih edilir.

## <a name="msbuildextensionspath-and-msbuilduserextensionspath"></a>MSBuildExtensionsPath ve MSBuildUserExtensionsPath

> [!WARNING]
> Bu uzantı mekanizmalarını kullanarak yinelenebilir derlemeleri makinelerde almak zorlaştıran. Kaynak Denetim sisteminiz denetlenir ve temelinizde tüm geliştiriciler arasında paylaşılan bir yapılandırması kullanmayı deneyin.

Kurala göre birçok yapı mantığı dosyaları alma çekirdek

```xml
$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\{TargetFileName}\ImportBefore\*.targets
```

içerikleri önce ve

```xml
$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\{TargetFileName}\ImportAfter\*.targets
```

Daha sonra. Bu yapı mantığı ortak proje türleri büyütmek yüklü SDK sağlar.

Aynı dizin yapısını içinde aranır `$(MSBuildUserExtensionsPath)`, kullanıcıya özgü klasör olduğu `%LOCALAPPDATA%\Microsoft\MSBuild`. Bu klasöre yerleştirilen dosyaları, kullanıcının kimlik bilgileriyle çalıştırmak karşılık gelen proje türündeki tüm yapılar için içeri aktarılacak. Kullanıcı Uzantıları desenin içeri aktarma dosyasında sonra adlı özelliklerini ayarlayarak devre dışı bırakılabilir `ImportUserLocationsByWildcardBefore{ImportingFileNameWithNoDots}`. Örneğin, ayarlama `ImportUserLocationsByWildcardBeforeMicrosoftCommonProps` için `false` alma önleyen `$(MSBuildUserExtensionsPath)\$(MSBuildToolsVersion)\Imports\Microsoft.Common.props\ImportBefore\*`.

## <a name="customizing-the-solution-build"></a>Çözüm derleme özelleştirme

> [!IMPORTANT]
> Bu şekilde çözümü derleme özelleştirme geçerlidir ile yalnızca komut satırı derlemeleri `MSBuild.exe`. Bu **yok** derlemeleri Visual Studio içinde uygulanır.

MSBuild bir çözüm dosyası oluşturduğunda, ilk proje dosyasına dahili çevirir ve, oluşturur. Oluşturulan proje dosyası alır `before.{solutionname}.sln.targets` önce tüm aracıların tanımlama ve `after.{solutionname}.sln.targets` yükleneceğini hedefleri hedefleri içeri aktardıktan sonra dahil olmak üzere `$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\SolutionFile\ImportBefore` ve `$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\SolutionFile\ImportAfter` dizinleri.

Örneğin, bir özel günlük iletisi oluşturma işleminden sonra yazmak için yeni bir hedef tanımlayabilirsiniz `MyCustomizedSolution.sln` adlı dizinde bir dosya oluşturarak `after.MyCustomizedSolution.sln.targets` içeren

```xml
<Project>
 <Target Name="EmitCustomMessage" AfterTargets="Build">
   <Message Importance="High" Text="The solution has completed the Build target" />
 </Target>
</Project>
```

## <a name="see-also"></a>Ayrıca Bkz.

 [MSBuild kavramları](../msbuild/msbuild-concepts.md) [MSBuild başvurusu](../msbuild/msbuild-reference.md)
