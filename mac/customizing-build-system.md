---
title: "Derleme Sistemi özelleştirme | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 6958B102-8527-4B40-BC65-3505DB63F9D3
ms.openlocfilehash: 2d17a952c58e5ef7e593ee7aeb1980e09a376800
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="customizing-the-build-system"></a>Derleme Sistemi özelleştirme

Microsoft tarafından geliştirilen bir yapı altyapısı MSbuild öncelikle .NET uygulamaları oluşturma için izin veren. Mono Framework'ün de kendi adlı Microsoft Build Engine ile uyarlamasını olduğu **xbuild**. Ancak, xbuild çıkışı, tüm işletim sistemlerinde MSBuild kullanma lehinde aşamalı.

**MSbuild** öncelikle için yapı sistem Visual Studio projeleri için Mac için kullanılır 

MSBuild gibi kaynak dosyaları, giriş kümesini gerçekleştirerek çalışır ve bunları yürütülebilir dosyaları gibi çıkışlarına dönüştüren ve bu çıkış derleyici gibi araçları çağırarak erişir. 


## <a name="msbuild-file"></a>MSBuild dosyası

MSBuild tanımlayan bir proje dosyası adlı bir XML dosyası kullanır *öğeleri* projenizin (örneğin, görüntü kaynaklar gibi) bir parçası ve *özellikleri* projenizi derleme için gerekli. Bu proje dosyası her zaman biten bir dosya uzantısına sahip olacaktır `proj`, gibi `.csproj` C# projeleri için. 

### <a name="viewing-the-msbuild-file"></a>MSBuild dosyasını görüntüleme
Bu dosya, proje adına sağ tıklayıp seçerek bulabilir **Finder ortaya**. Bu tüm dosya ve klasörler, projenize ilgili görüntüler dahil olmak üzere `.csproj` aşağıda gösterildiği gibi dosya:

![](media/customizing-build-system-image1.png)

Ayrıca görüntüleyebilirsiniz `.csproj` Mac için Visual Studio'da yeni bir sekmede, proje adına tıklayarak ve göz **Araçlar > Düzenle dosya**:

![](media/customizing-build-system-image2.png)

### <a name="composition-of-the-msbuild-file"></a>MSBuild dosyası oluşturma

Zorunlu bir kök tüm MSBuild dosyalarını içerecek `Project` öğesi, aşağıda gösterilmektedir:

```
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="14.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
</Project>
```

Genellikle, projenin de alacak bir `.targets` işlemek ve çeşitli dosyaları derleme anlatmaktadır kuralları çoğunu içeren dosya. Bu genellikle alt görünür, `proj` dosya ve C# projeleri için aşağıdaki gibi görünür:

```
<Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />
```

Hedef dosya, yalnızca başka bir MSBuild dosyadır. Bu dosya tarafından birden çok proje yeniden kullanılabilir MSBuild kodunu içerir. Örneğin, `Microsoft.CSharp.targets` tarafından temsil edilen bir dizinde bulunan dosya `MSBuildBinPath` özelliği (veya değişken), C# derlemeleri C# kaynak dosyalarından oluşturmaya yönelik mantık içerir.

### <a name="items-and-properties"></a>Öğeleri ve özellikleri

Msbuild'de iki temel veri türü vardır: *öğeleri* ve *özellikleri*, aşağıdaki daha ayrıntılı olarak açıklanmıştır.

#### <a name="properties"></a>Özellikler

Derleyici seçenekleri gibi derleme etkileyen ayarları depolamak için kullanılan anahtar/değer çiftleri özelliklerdir.

Bunlar bir PropertyGroup kullanarak ayarlayın ve herhangi bir sayıda özellikler içerebilir PropertiesGroups herhangi bir sayıda içerebilir. 

Örneğin, basit bir konsol uygulaması PropertyGroup aşağıdakine benzeyebilir:

```
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

Örneğin aşağıdaki kod parçacığında başlatma ekranlar iOS oluşturur. Tür bunlar `BundleResource`, görüntü yolu olarak spec ile:

```
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


