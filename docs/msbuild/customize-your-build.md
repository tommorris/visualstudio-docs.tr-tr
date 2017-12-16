---
title: "Yapınızın özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 06/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bceb3b-14fb-455c-805a-63acefa4b3ed
caps.latest.revision: "13"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: ed63e19334c2c1c40cd5ac353974d7a1dbdc5764
ms.sourcegitcommit: e951faab601f5c05ad6606d8fd0cd2059fc4cc25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="customize-your-build"></a>Yapınızın özelleştirme
MSBuild 15. sürümden önceki sürümler çözümünüz projelerine yeni, özel bir özellik sağlamak istiyorsanız çözümdeki her proje dosyası el ile bu özellik için bir başvuru ekleyin içeriyor. Ya da özellik .props dosyasında tanımlayın ve başka şeylerin çözümdeki her projeye .props dosyasında açıkça alma gerekiyordu.

Bununla birlikte, artık, yeni bir özellik her projeye tek bir adımda, depo kökündeki tek dosyalı çağrılan Directory.Build.props tanımlayarak ekleyebilirsiniz. MSBuild çalıştığında, Microsoft.Common.props Directory.Build.props dosyası için dizin yapısını arar (ve Microsoft.Common.targets Directory.Build.targets için görünür). Bulursa, özelliği alır. Directory.Build.props projeler bir dizini altında özelleştirmeleri sağlayan bir kullanıcı tarafından tanımlanan bir dosyadır.

## <a name="directorybuildprops-example"></a>Directory.Build.props örneği
Örneğin, tüm projeleriniz yeni Roslyn erişmek için etkinleştirmek istiyorsanız **/ belirleyici** özelliği (hangi gösterilir Roslyn CoreCompile hedef özelliği tarafından `$(Deterministic)`), aşağıdakileri yapabilirsiniz.

1. Yeni bir dosya Directory.Build.props olarak adlandırılan, depo kök dizininde oluşturun.
2. Aşağıdaki XML dosyasına ekleyin.

  ```xml
  <Project>
    <PropertyGroup>
      <Deterministic>true</Deterministic>
    </PropertyGroup>
  </Project>
  ```
3. MSBuild çalıştırın. Projenizin varolan içeri aktarmalar Microsoft.Common.props ve Microsoft.Common.targets dosyasını bulun ve içe aktarın.

## <a name="search-scope"></a>Arama kapsamı
Directory.Build.props dosyası için arama yaparken MSBuild Directory.Build.props dosyasını bulduktan sonra durdurma dizin yapısından yukarı doğru proje konumunuz ($(MSBuildProjectFullPath)) anlatılmaktadır. Örneğin, $(MSBuildProjectFullPath) c:\users\username\code\test\case1 olduysa, MSBuild var. arama başlamalıdır ve sonra arama yukarı kadar dizin yapısını aşağıdaki dizin yapısını olduğu gibi bir Directory.Build.props dosya bulunan .

```
c:\users\username\code\test\case1
c:\users\username\code\test
c:\users\username\code
c:\users\username
c:\users
c:\
```
Çözüm dosyası için Directory.Build.props ilgisiz konumudur.

## <a name="import-order"></a>İçeri aktarma sırası

Daha sonra tanımlanan özellikler için kullanılabilir; bu nedenle Directory.Build.props çok erken Microsoft.Common.props içe aktarılır. Bu nedenle, henüz tanımlanmamış (ve dolayısıyla için boş değerlendirecek) özelliklerine başvuran kaçının.

Directory.Build.targets .targets dosyaları NuGet paketleri içeri aktardıktan sonra Microsoft.Common.targets alınır. Bu nedenle, özellikleri ve yapı mantığı çoğunda tanımlanmış hedefleri geçersiz kılmak için kullanılabilir, ancak bazen proje dosyası içinde özelleştirmeler son içeri aktardıktan sonra yapmanız gerekebilir.

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

Tüm projeleri için ortak olan özellikler için uygun olabilir `(1)`, ortak özelliklerini `src` projeleri `(2-src)`ve ortak özelliklerini `test` projeleri `(2-test)`.

Msbuild doğru "İç" dosyaları birleştirmek için (`2-src` ve `2-test`) "dış" dosyasıyla (`1`), bulduğu sonra msbuild dikkate almanız gerekir bir `Directory.Build.props` dosyasını durdurur daha fazla tarama. Taramaya devam et ve dış dosyasına birleştirmek için bu iki iç dosyalarıyla koyun:

`<Import Project="$([MSBuild]::GetPathOfFileAbove('Directory.Build.props', '$(MSBuildThisFileDirectory)../'))" />`

Msbuild'ın genel yaklaşım özetini aşağıdaki gibidir:

- Belirli bir proje için ilk msbuild bulur `Directory.Build.props` yukarı isteğe bağlı olarak çözümü yapısında öndeğerlerini birleştirir ve daha fazla bilgi için taramayı durdurur
- Bulunan ve ardından birleştirildiği için birden çok düzeyi isteyip istemediğinizi [ `<Import...>` ](http://docs.microsoft.com/visualstudio/msbuild/property-functions#msbuild-getpathoffileabove) (yukarıda gösterilen) "İç" dosyasından "dış" dosyası
- "Dış" dosya kendisi olursa Ayrıca, üzerinde bir şey içeri sonra taramayı var. durdurur
- Tarama ve birleştirme işlemi denetlemek için kullandığı `$(DirectoryBuildPropsPath)` ve`$(ImportDirectoryBuildProps)`

Ya da daha basit bir şekilde: ilk `Directory.Build.props` , herhangi bir şey içe aktarmaz olduğu yere msbuild durdurur.

## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)   
