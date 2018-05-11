---
title: Derleme Sistemi özelleştirme
description: Bu makalede MSBuild kısa bir giriş yapı Mac için Visual Studio tarafından kullanılan sistem olduğu
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 6958B102-8527-4B40-BC65-3505DB63F9D3
ms.openlocfilehash: 16f14d1acb31612d2997937b9aa34f918b6376d6
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
# <a name="customizing-the-build-system"></a>Derleme Sistemi özelleştirme

Microsoft tarafından geliştirilen bir yapı altyapısı MSbuild öncelikle .NET uygulamaları oluşturma için izin veren. Mono Framework'ün de adlı Microsoft Build Engine ile kendi uyarlamasını olduğu **xbuild**. Ancak, xbuild çıkışı, tüm işletim sistemlerinde MSBuild kullanma lehinde aşamalı.

**MSbuild** öncelikle için yapı sistem Visual Studio projeleri için Mac için kullanılır 

MSBuild gibi kaynak dosyaları girişleri, bir dizi gerçekleştirerek çalışır ve bunları yürütülebilir dosyalar gibi çıkışlarına dönüştürür. Bu çıktı derleyici gibi araçları çağırarak erişir. 


## <a name="msbuild-file"></a>MSBuild dosyası

MSBuild tanımlayan bir proje dosyası adlı bir XML dosyası kullanır *öğeleri* projenizin (örneğin, görüntü kaynaklar gibi) bir parçası ve *özellikleri* projenizi derleme için gerekli. Bu proje dosyası her zaman biten bir dosya uzantısına sahip olacaktır `proj`, gibi `.csproj` C# projeleri için. 

### <a name="viewing-the-msbuild-file"></a>MSBuild dosyasını görüntüleme

Proje adına sağ tıklayıp seçerek MSBuild dosyasını bulun **Finder ortaya**. Tüm dosya ve klasörler, projenize ilgili Bulucu pencere görüntüler dahil olmak üzere `.csproj` aşağıdaki görüntüde gösterildiği gibi dosya:

![Bulucu csproj konumda](media/customizing-build-system-image1.png)

Görüntülenecek `.csproj` Mac için Visual Studio'da yeni bir sekmede, proje adına sağ tıklayın ve göz **Araçlar > Düzenle dosya**:

![Kaynak düzenleyicisinde csproj açma](media/customizing-build-system-image2.png)

### <a name="composition-of-the-msbuild-file"></a>MSBuild dosyası oluşturma

Zorunlu bir kök tüm MSBuild dosyalarını içerecek `Project` öğesi, şu şekilde:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="14.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
</Project>
```

Genellikle, projenin de alacak bir `.targets` dosyası. Bu dosya işleme ve çeşitli dosyaları derleme anlatmaktadır kuralları çoğunu içerir. Alma işlemi genellikle alt görünür, `proj` dosya ve C# projeleri için şöyle bir şey bakın:

```xml
<Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />
```

Hedef dosya, yalnızca başka bir MSBuild dosyadır. Bu dosya tarafından birden çok proje yeniden kullanılabilir MSBuild kodunu içerir. Örneğin, `Microsoft.CSharp.targets` tarafından temsil edilen bir dizinde bulunan dosya `MSBuildBinPath` özelliği (veya değişken), C# derlemeleri C# kaynak dosyalarından oluşturmaya yönelik mantık içerir.

### <a name="items-and-properties"></a>Öğeleri ve özellikleri

Msbuild'de iki temel veri türü vardır: *öğeleri* ve *özellikleri*, hangi aşağıdaki bölümlerde daha ayrıntılı açıklanmıştır.

#### <a name="properties"></a>Özellikler

Derleyici seçenekleri gibi derleme etkileyen ayarları depolamak için kullanılan anahtar/değer çiftleri özelliklerdir.

Bunlar bir PropertyGroup kullanarak ayarlayın ve herhangi bir sayıda özellikler içerebilir PropertiesGroups herhangi bir sayıda içerebilir. 

Örneğin, basit bir konsol uygulaması PropertyGroup aşağıdaki XML gibi görünebilir:

```xml
<PropertyGroup>
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
        <Platform Condition=" '$(Platform)' == '' ">x86</Platform>
        <ProjectGuid>{E248730E-1393-43CC-9183-FFA42F63BE81}</ProjectGuid>
        <OutputType>Exe</OutputType>
        <RootNamespace>refactoring</RootNamespace>
        <AssemblyName>refactoring</AssemblyName>
        <TargetFrameworkVersion>v4.5</TargetFrameworkVersion>
    </PropertyGroup>
```

Özellikler başvurulabilir için gelen kullanarak ifadeleri `$()` sözdizimi. Örneğin, `$(Foo)` değeri olarak değerlendirilecek `Foo` özelliği. Özelliği ayarlı değil, herhangi bir hata olmadan boş bir dize olarak değerlendirir.

#### <a name="items"></a>Öğeler

Öğeler girişleri postalarla listeler ya da ayarlar gibi yapı sistemine bir yol sağlar ve genellikle dosyaları temsil eder. Her öğe bir öğe olan *türü*, öğeyi *spec*ve isteğe bağlı rasgele *meta verileri*. Not MSBuild tek tek öğelere işletmek değil, tüm öğeleri üzerinde sürdüğünü bir öğe türü adı verilen *ayarlayın*

Öğe bildirme tarafından oluşturulan bir `ItemGroup`. Herhangi bir sayıda öğe içerebilir ItemGroups herhangi bir sayıda olabilir. 

Örneğin, aşağıdaki kod parçacığını başlatma ekranlar iOS oluşturur. Başlatma ekranlar yapı türüne sahip `BundleResource`, görüntü yolu olarak spec ile:

```xml
 <ItemGroup>
    <BundleResource Include="Resources\Default-568h%402x.png" />
    <BundleResource Include="Resources\Default%402x.png" />
    <BundleResource Include="Resources\Default.png" />
    <BundleResource Include="Resources\Default-Portrait.png" />
    <BundleResource Include="Resources\Default-Portrait%402x.png" />
    <BundleResource Include="Resources\Default-Landscape%402x.png" />
  </ItemGroup>
 ```

 Kümeleri kullanarak ifadeler başvurulabilen öğesi `@()` sözdizimi. Örneğin, `@(BundleResource)` BundleResource öğelerin tümünü anlamına gelir BundleResource öğesi kümesi olarak değerlendirilir. Bu türde öğe varsa, herhangi bir hata boş olur.

## <a name="resources-for-learning-msbuild"></a>MSBuild öğrenme için kaynaklar

MSBuild hakkında daha ayrıntılı bilgi edinmek için aşağıdaki kaynaklara kullanılabilir:

* [MSDN - genel bakış](https://msdn.microsoft.com/library/dd393574.aspx)
* [MSDN - kavramları](https://msdn.microsoft.com/library/dd637714.aspx)
