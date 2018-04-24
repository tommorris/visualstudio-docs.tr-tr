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
ms.openlocfilehash: dae51959313a7108c54466dff08b3641525818cd
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="customize-your-build"></a>Yapınızın özelleştirme
MSBuild 15. sürümden önceki sürümler çözümünüz projelerine yeni, özel bir özellik sağlamak istiyorsanız çözümdeki her proje dosyası el ile bu özellik için bir başvuru ekleyin içeriyor. Veya özelliğinde tanımlamak zorunda kalındı bir *.props* dosya ve açıkça alma *.props* başka şeylerin çözümdeki her projeye dosyasında.

Bununla birlikte, artık yeni bir özellik tek bir adımda her proje bir tek dosyalı çağrılan içinde tanımlayarak ekleyebileceğiniz *Directory.Build.props* , depo kökündeki. MSBuild çalıştığında, *Microsoft.Common.props* directory yapınızı arar *Directory.Build.props* dosyası (ve *Microsoft.Common.targets* arar *Directory.Build.targets*). Bulursa, özelliği alır. *Directory.Build.props* bir dizini altındaki projelerine özelleştirmeleri sağlar kullanıcı tanımlı bir dosya.

## <a name="directorybuildprops-example"></a>Directory.Build.props örneği
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

## <a name="search-scope"></a>Arama kapsamı
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

## <a name="import-order"></a>İçeri aktarma sırası

*Directory.Build.props* uygulamasında çok erken alınan *Microsoft.Common.props*, daha sonra tanımlanan özellikleri için kullanılamaz. Bu nedenle, henüz tanımlanmamış (ve dolayısıyla için boş değerlendirecek) özelliklerine başvuran kaçının.

*Directory.Build.targets* üzerinden içe aktarılan *Microsoft.Common.targets* aldıktan sonra *.targets* NuGet paketlerini dosyalarından. Bu nedenle, özellikleri ve yapı mantığı çoğunda tanımlanmış hedefleri geçersiz kılmak için kullanılabilir, ancak bazen proje dosyası içinde özelleştirmeler son içeri aktardıktan sonra yapmanız gerekebilir.

## <a name="use-case-multi-level-merging"></a>Kullanım örneği: çok düzeyli birleştirme

Bu standart çözümü yapı olduğunu varsayalım:

````
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
````

Tüm projeleri için ortak olan özellikler için uygun olabilir *(1)*, ortak özelliklerini *src* projeleri *(2-src)* ve ortak özelliklerini  *Test* projeleri *(2-test)*.

MSBuild doğru "İç" dosyaları birleştirmek için (*2-src* ve *2 test*) "dış" dosyasıyla (*1*), bir kez MSBuild bir bulduğunudikkatealmanızgerekir*Directory.Build.props* dosyasını durdurur daha fazla tarama. Taramaya devam et ve dış dosyasına birleştirmek için bu iki iç dosyalarıyla koyun:

`<Import Project="$([MSBuild]::GetPathOfFileAbove('Directory.Build.props', '$(MSBuildThisFileDirectory)../'))" />`

MSBuild'ın genel yaklaşım özetini aşağıdaki gibidir:

- Belirli bir proje için ilk MSBuild bulur *Directory.Build.props* yukarı isteğe bağlı olarak çözümü yapısında öndeğerlerini birleştirir ve daha fazla bilgi için taramayı durdurur
- Bulunan ve ardından birleştirildiği için birden çok düzeyi isteyip istemediğinizi [ `<Import...>` ](../msbuild/property-functions.md#msbuild-getpathoffileabove) (yukarıda gösterilen) "İç" dosyasından "dış" dosyası
- "Dış" dosya kendisi olursa Ayrıca, üzerinde bir şey içeri sonra taramayı var. durdurur
- Tarama ve birleştirme işlemi denetlemek için kullandığı `$(DirectoryBuildPropsPath)` ve `$(ImportDirectoryBuildProps)`

Ya da daha basit bir şekilde: ilk *Directory.Build.props* , herhangi bir şey içe aktarmaz olduğu yere MSBuild durdurur.

## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)   
