---
title: "Özellik işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 02/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MSBuild, property functions
ms.assetid: 2253956e-3ae0-4bdc-9d3a-4881dfae4ddb
caps.latest.revision: "33"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 46df0fc4be6abf639f939b5145765f0ba41b0b8c
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="property-functions"></a>Özellik İşlevleri
.NET Framework sürüm 4 ve 4.5, özellik işlevleri MSBuild komut değerlendirmek için kullanılabilir. Özellik işlevleri özellikleri görünür her yerde kullanılabilir. Görevler, farklı özellik işlevleri dışında hedefleri kullanılabilen ve tüm hedef çalışmadan önce değerlendirilir.  

 MSBuild görevleri kullanmadan sistem saatini okumak, dizeleri karşılaştırmak, normal ifadeler eşleşen ve derleme betiğinizin başka eylemler gerçekleştirebilir. MSBuild dize ve numarası dizeye dönüştürmek ve diğer dönüşümleri gerektiği gibi yapın dener.  

## <a name="property-function-syntax"></a>Özellik işlev sözdizimi  
 Özellik işlevleri üç tür bunlar; Her işlevi farklı sözdizimi vardır:  

-   Dize (örnek) özellik işlevleri  

-   Statik özellik işlevleri  

-   MSBuild özellik işlevleri  

### <a name="string-property-functions"></a>Dize özelliği işlevleri  
 Tüm yapı özelliği yalnızca dize değerlerini değerlerdir. Herhangi bir özelliğin değerini üzerinde çalışması için dize (örnek) yöntemlerini kullanabilirsiniz. Örneğin, bu kod kullanarak bir tam yol temsil eden bir derleme özelliğinden sürücü adı (ilk üç karakter) ayıklayın:  

 `$(ProjectOutputFolder.Substring(0,3))`  

### <a name="static-property-functions"></a>Statik özellik işlevleri  
 Derleme betiğinizin statik özellikleri ve yöntemleri birçok sistem sınıfların erişebilir. Bir statik özellik değerini almak için aşağıdaki sözdizimini kullanın nerede *sınıfı* sistem sınıfı adı ve *özelliği* özelliği adıdır.  

 `$([Class]::Property)`  

 Örneğin, bir derleme özelliği için geçerli tarih ve saati ayarlamak için aşağıdaki kodu kullanabilirsiniz.  

 `<Today>$([System.DateTime]::Now)</Today>`  

 Statik bir yöntemi çağırmak için aşağıdaki sözdizimini kullanın nerede *sınıfı* sistem sınıfı adı *yöntemi* yöntemi adıdır ve *(parametre)* parametre listesi yöntem:  

 `$([Class]::Method(Parameters))`  

 Örneğin, bir derleme özelliği için yeni bir GUID ayarlamak için bu betiği kullanabilirsiniz:  

 `<NewGuid>$([System.Guid]::NewGuid())</NewGuid>`  

 Statik özelliğe işlevlerde herhangi bir statik yöntemi veya özelliği bu sistem sınıfların kullanabilirsiniz:  

-   System.Byte  

-   System.Char  

-   System.Convert'i  

-   System.DateTime  

-   System.Decimal  

-   System.Double  

-   System.Enum  

-   System.Guid  

-   System.Int16  

-   System.Int32  

-   System.Int64  

-   System.IO.Path  

-   System.Math  

-   System.Runtime.InteropServices.OSPlatform

-   System.Runtime.InteropServices.RuntimeInformation

-   System.UInt16  

-   System.UInt32  

-   System.UInt64  

-   System.SByte  

-   System.Single  

-   System.String  

-   System.StringComparer  

-   System.TimeSpan  

-   System.Text.RegularExpressions.Regex  

-   Microsoft.Build.Utilities.ToolLocationHelper  

 Ayrıca, aşağıdaki statik yöntemlerini ve özelliklerini kullanabilirsiniz:  

-   System.Environment::CommandLine  

-   System.Environment::ExpandEnvironmentVariables  

-   System.Environment::GetEnvironmentVariable  

-   System.Environment::GetEnvironmentVariables  

-   System.Environment::GetFolderPath  

-   System.Environment::GetLogicalDrives  

-   System.IO.Directory::GetDirectories  

-   System.IO.Directory::GetFiles  

-   System.IO.Directory::GetLastAccessTime  

-   System.IO.Directory::GetLastWriteTime  

-   System.IO.Directory::GetParent  

-   System.IO.File::Exists  

-   System.IO.File::GetCreationTime  

-   System.IO.File::GetAttributes  

-   System.IO.File::GetLastAccessTime  

-   System.IO.File::GetLastWriteTime  

-   System.IO.File::ReadAllText  

### <a name="calling-instance-methods-on-static-properties"></a>Statik özellikler örnek yöntemleri çağırma  
 Bir nesne örneği döndüren statik özelliğe erişirse, bu nesnenin örnek yöntemleri çağırabilirsiniz. Örnek yöntemi çağırmak için aşağıdaki sözdizimini kullanın nerede *sınıfı* sistem sınıfı adı *özelliği* özellik adı *yöntemi* adıdır yöntemi, ve *(parametre)* yöntemi için parametre listesidir:  

 `$([Class]::Property.Method(Parameters))`  

 Sınıfın adını içeren ad tam olarak nitelenmiş olmalıdır.  

 Örneğin, bir derleme özelliği geçerli tarihi bugün ayarlamak için aşağıdaki kodu kullanabilirsiniz.  

 `<Today>$([System.DateTime]::Now.ToString("yyyy.MM.dd"))</Today>`  

### <a name="msbuild-property-functions"></a>MSBuild özellik işlevleri  
 Aritmetik, bitwise sağlamak için çeşitli statik yöntemlerin yapınızın erişilebilir mantıksal ve kaçış karakteri desteği. Aşağıdaki sözdizimini kullanarak bu yöntemlere erişme nerede *yöntemi* yöntemi adıdır ve *parametreleri* yöntemi için parametre listesi.  

 `$([MSBuild]::Method(Parameters))`  

 Örneğin, birlikte sayısal değerlere sahip iki özellik eklemek için aşağıdaki kodu kullanın.  

 `$([MSBuild]::Add($(NumberOne), $(NumberTwo))`  

 MSBuild özelliği işlevlerin bir listesi aşağıda verilmiştir:  

|İşlev imzası|Açıklama|  
|------------------------|-----------------|  
|double (double, çift b) Ekle|İki çiftleri ekleyin.|  
|uzun (uzun uzun a, b) ekleyin|İki Integer ekleyin.|  
|double (double, çift b) çıkarma|İki double çıkarın.|  
|uzun (uzun uzun a, b) çıkarma|İki Integer çıkarın.|  
|double (double, çift b) çarpın|İki double çarpın.|  
|uzun (uzun uzun b) çarpın|İki Integer çarpın.|  
|double (double, çift b) bölün|İki double bölün.|  
|uzun (uzun uzun b) bölün|İki Integer bölün.|  
|çift (double, çift b) mod|İki double.|  
|uzun (uzun uzun Modulo b)|İki Integer.|  
|dize Escape(string unescaped)|MSBuild kaçış kurallarına göre dizeye kaçış karakteri.|  
|Unescape (Atlanan dizesini) dize|MSBuild kaçış kurallarına göre dize unescape.|  
|int BitwiseOr (int ilk, int saniye)|Bit tabanlı gerçekleştirmek `OR` ilk ve ikinci (ilk &#124; saniye).|  
|int BitwiseAnd (int ilk, int saniye)|Bit tabanlı gerçekleştirmek `AND` ilk ve ikinci (ilk ve ikinci).|  
|int BitwiseXor (int ilk, int saniye)|Bit tabanlı gerçekleştirmek `XOR` ilk ve ikinci (ilk ^ ikinci).|  
|int BitwiseNot(int first)|Bit tabanlı gerçekleştirmek `NOT` (~ ilk).|  
|bool IsOsPlatform (dize platformString)|Geçerli işletim sistemi platformu olup olmadığını belirtin `platformString`. `platformString`bir üyesi olmalıdır <xref:System.Runtime.InteropServices.OSPlatform>.|
|bool IsOSUnixLike|Geçerli işletim sistemi bir Unix sistem geçerlidir.|
|dize NormalizePath (params dize [] yolu)|Sağlanan yol Kurallaştırılan tam yolunu alır ve geçerli işletim sistemi için doğru dizin ayırıcı karakteri içeren sağlar.|
|dize NormalizeDirectory (params dize [] yolu)|Sağlanan dizin Kurallaştırılan tam yolunu alır ve doğru dizin ayırıcı karakter geçerli içerdiği sağlar sağlarken, işletim sistemi eğik sahiptir.|
|dize EnsureTrailingSlash(string path)|Verilen yolu bir ekleme sondaki eğik çizgi yoksa. Yol boş bir dize ise, değiştirmez.|
|GetPathOfFileAbove (dize dosya, dize startingDirectory) dize|Bir dosyayı arar geçerli yapı dosyanın konumuna göre veya dayanarak `startingDirectory`, belirtildiği takdirde.|
|GetDirectoryNameOfFileAbove (dize startingDirectory, dize fileName)|Belirtilen dizin veya bu dizinin üstündeki dizin yapısını bir konumda bir dosyasını bulun.|
|Makerelatıve (dize ana yolu, dize yolu) dize|Yapar `path` göreli `basePath`. `basePath`mutlak bir dizin olmalıdır. Varsa `path` olamaz göreli yapılan, onu verbatim döndürülür. Benzer şekilde `Uri.MakeRelativeUri`.|
|ValueOrDefault (dize conditionValue, dize defaultValue) dize|Yalnızca parametresi 'conditionValue' else boş ise, dize 'defaultValue' parametresinde dönmek, değer conditionValue dönün.|

##  <a name="nested-property-functions"></a>İç içe özellik işlevleri  
 Aşağıdaki örnekte gösterildiği gibi daha karmaşık işlevleri forma özellik işlevleri birleştirebilirsiniz.  

 `$([MSBuild]::BitwiseAnd(32, $([System.IO.File]::GetAttributes(tempFile))))`  

 Bu örnek değerini döndürür <xref:System.IO.FileAttributes> `Archive` bit (32 ya da 0) yolu tarafından verilen dosyasının `tempFile`. Özellik işlevleri içinde ada göre numaralandırılmış veri değerleri bulunamaz dikkat edin. Sayısal değer (32) yerine kullanılmalıdır.  

 Meta veriler iç içe özellik işlevlerde da görüntülenebilir. Daha fazla bilgi için bkz: [Batching](../msbuild/msbuild-batching.md).  

##  <a name="msbuild-doestaskhostexist"></a>MSBuild DoesTaskHostExist  
 `DoesTaskHostExist` MSBuild özelliği işlevinde görev ana bilgisayar için belirtilen çalışma zamanı ve mimari değerleri şu anda yüklü olup olmadığını döndürür.  

 Bu özellik işlev sözdizimi aşağıdaki gibidir:  

```  
$[MSBuild]::DoesTaskHostExist(string theRuntime, string theArchitecture)  
```  

##  <a name="msbuild-ensuretrailingslash"></a>MSBuild EnsureTrailingSlash  
 `EnsureTrailingSlash` MSBuild özelliği işlevinde, zaten yoksa eğik ekler.  

 Bu özellik işlev sözdizimi aşağıdaki gibidir:  

```  
$([MSBuild]::EnsureTrailingSlash('$(PathProperty)'))
```  

##  <a name="msbuild-getdirectorynameoffileabove"></a>MSBuild GetDirectoryNameOfFileAbove  
 MSBuild `GetDirectoryNameOfFileAbove` özelliği işlevi, bir dosya yolu geçerli dizinde yukarıda dizinlerde arar.  

 Bu özellik işlev sözdizimi aşağıdaki gibidir:  

```  
$[MSBuild]::GetDirectoryNameOfFileAbove(string ThePath, string TheFile)  
```  

 Aşağıdaki kod, bu söz dizimini örneğidir.  

```xml  
<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), EnlistmentInfo.props))\EnlistmentInfo.props" Condition=" '$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), EnlistmentInfo.props))' != '' " />  
```  

##  <a name="msbuild-getpathoffileabove"></a>MSBuild GetPathOfFileAbove  
 `GetPathOfFileAbove` MSBuild özelliği işlevinde Bunun hemen önceki dosyasının yolunu döndürür. Arama için işlevsel olarak eşdeğerdir

 ```<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), dir.props))\dir.props" />```

 Bu özellik işlev sözdizimi aşağıdaki gibidir:  

```  
$([MSBuild]::GetPathOfFileAbove(dir.props)  
```  

##  <a name="msbuild-getregistryvalue"></a>MSBuild GetRegistryValue  
 MSBuild `GetRegistryValue` özelliği işlevi bir kayıt defteri anahtarı değerini döndürür. Bu işlev, iki bağımsız değişkeni, anahtar adı ve değer adını alır ve kayıt defteri anahtarından değer döndürür. Değer adı belirtmezseniz, varsayılan değeri döndürülür.  

 Aşağıdaki örnekler, bu işlev nasıl kullanıldığını gösterir:  

```  
$([MSBuild]::GetRegistryValue(`HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\10.0\Debugger`, ``))                                  // default value  
$([MSBuild]::GetRegistryValue(`HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\10.0\Debugger`, `SymbolCacheDir`))  
$([MSBuild]::GetRegistryValue(`HKEY_LOCAL_MACHINE\SOFTWARE\(SampleName)`, `(SampleValue)`))             // parens in name and value  

```  

##  <a name="msbuild-getregistryvaluefromview"></a>MSBuild GetRegistryValueFromView  
 MSBuild `GetRegistryValueFromView` özelliği işlevi alır sistem kayıt defteri verilerini verilen kayıt defteri anahtarı, değer ve bir veya daha fazla kayıt defteri görünümleri sıralı. Bulunan kadar anahtar ve değer, her kayıt defteri görünümünde sırayla aranır.  

 Bu özellik işlev sözdizimi aşağıdaki gibidir:  

 [MSBuild\]:: GetRegistryValueFromView (dize keyName, dize değer adı, nesne defaultValue, params nesne [] görünümler)  

 Windows 64-bit işletim sisteminde 32-bit uygulamalar HKEY_LOCAL_MACHINE\Software kayıt defteri görünümünü sunan bir HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node kayıt defteri anahtarı korur.  

 Varsayılan olarak, 32-bit kayıt defteri görünüm WOW64 üzerinde çalışan 32 bit bir uygulama erişir ve 64 bit bir uygulama 64-bit kayıt defteri görünüm erişir.  

 Aşağıdaki kayıt defteri görünümleri kullanılabilir:  

|Kayıt görünümü|Tanım|  
|-------------------|----------------|  
|RegistryView.Registry32|32 bit uygulama kayıt defteri görüntüleyin.|  
|RegistryView.Registry64|64-bit uygulama kayıt defteri görünümü.|  
|RegistryView.Default|Uygulamanın üzerinde çalıştığı işlem eşleştirir kayıt defteri görünüm.|  

 Bir örnek verilmiştir.  

 `$([MSBuild]::GetRegistryValueFromView('HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SDKs\Silverlight\v3.0\ReferenceAssemblies', 'SLRuntimeInstallPath', null, RegistryView.Registry64, RegistryView.Registry32))`  

 64-bit kayıt defteri görünümünde, ardından 32-bit kayıt defteri görünümünde ilk arayan ReferenceAssemblies anahtarının SLRuntimeInstallPath verilerini alır.  

##  <a name="msbuild-makerelative"></a>MSBuild Makerelatıve  
 MSBuild `MakeRelative` özelliği işlevi ilk yol göre ikinci yol göreli yolunu döndürür. Her yol, bir dosya veya klasör olabilir.  

 Bu özellik işlev sözdizimi aşağıdaki gibidir:  

```  
$[MSBuild]::MakeRelative($(FileOrFolderPath1), $(FileOrFolderPath2))  
```  

 Aşağıdaki kod, bu söz dizimini örneğidir.  

```xml  
<PropertyGroup>  
    <Path1>c:\users\</Path1>  
    <Path2>c:\users\username\</Path2>  
</PropertyGroup>  

<Target Name = "Go">  
    <Message Text ="$([MSBuild]::MakeRelative($(Path1), $(Path2)))" />  
    <Message Text ="$([MSBuild]::MakeRelative($(Path2), $(Path1)))" />  
</Target>  

<!--  
Output:  
   username\  
   ..\  
-->  
```  

##  <a name="msbuild-valueordefault"></a>MSBuild ValueOrDefault  
 MSBuild `ValueOrDefault` özelliği işlevi ilk bağımsız değişken null veya boş olmadığı sürece döndürür. İlk bağımsız değişken null veya boş ise, işlevi ikinci bağımsız değişkeni döndürür.  

 Aşağıdaki örnek, bu işlev nasıl kullanıldığını gösterir.  

```xml  
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  

    <PropertyGroup>  
        <Value1>$([MSBuild]::ValueOrDefault(`$(UndefinedValue)`, `a`))</Value1>  
        <Value2>$([MSBuild]::ValueOrDefault(`b`, `$(Value1)`))</Value2>  
    </PropertyGroup>  

    <Target Name="MyTarget">  
        <Message Text="Value1 = $(Value1)" />  
        <Message Text="Value2 = $(Value2)" />  
    </Target>  
</Project>  

<!--  
Output:   
  Value1 = a  
  Value2 = b  
-->  
```

## <a name="see-also"></a>Ayrıca Bkz.
[MSBuild özellikleri](../msbuild/msbuild-properties.md)   
[MSBuild genel bakış](../msbuild/msbuild.md)
