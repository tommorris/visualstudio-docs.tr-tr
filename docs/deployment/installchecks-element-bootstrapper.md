---
title: '&lt;InstallChecks&gt; öğe (Önyükleyici) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <InstallChecks> element [bootstrapper]
ms.assetid: ad329c87-b0ad-4304-84de-ae9496514c42
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51fcfd8aaa0048cac3fb9a33c7974132655de87a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31566179"
---
# <a name="ltinstallchecksgt-element-bootstrapper"></a>&lt;InstallChecks&gt; öğe (Önyükleyici)
`InstallChecks` Öğesi tarafından desteklenen tüm uygulama için uygun önkoşulların yüklendiğinden emin olmak için yerel bilgisayara karşı testleri çeşitli başlatılıyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<InstallChecks>  
    <AssemblyCheck   
        Property  
        Name  
        PublicKeyToken  
        Version  
        Language  
        ProcessorArchitecture  
    />  
    <RegistryCheck  
        Property  
        Key  
        Value  
    />  
    <ExternalCheck   
        PackageFile  
        Property  
        Arguments  
    />  
    <FileCheck   
        Property  
        FileName  
        SearchPath  
        SpecialFolder  
        SearchDepth  
    />  
    <MsiProductCheck   
        Property  
        Product  
        Feature  
    />  
    <RegistryFileCheck   
        Property  
        Key  
        Value  
        FileName  
        SearchDepth  
    />  
</InstallChecks>  
```  
  
## <a name="assemblycheck"></a>AssemblyCheck  
 Bu öğe bir isteğe bağlı bir alt öğesi olan `InstallChecks`. Her örneği için `AssemblyCheck`, önyükleyici öğesi tarafından tanımlanan derleme genel derleme önbelleğinde (GAC) olduğundan emin olun. Öğe içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Property`|Gerekli. Sonucu depolamak için özelliğinin adı. Bu özellik altındaki bir testten başvurulabilir `InstallConditions` alt öğesi olarak `Command` öğesi. Daha fazla bilgi için bkz: [ \<komutları > öğesi](../deployment/commands-element-bootstrapper.md).|  
|`Name`|Gerekli. Denetlenecek derlemenin tam adı.|  
|`PublicKeyToken`|Gerekli. Ortak anahtarın kısaltılmış form derleme güçlü olarak adlandırılmamış bu ile ilişkilendirilmiş. GAC içinde depolanan tüm derlemelerin bir ad, bir sürüm ve bir ortak anahtar gerekir.|  
|`Version`|Gerekli. Derleme sürümü.<br /><br /> Biçimi sürüm numarasına sahip \< *ana sürüm*>.\< *alt sürüm*>.\< *sürüm yapı*>.\< *düzeltme sürümü*>.|  
|`Language`|İsteğe bağlı. Yerelleştirilmiş bir derleme dili. Varsayılan değer `neutral`.|  
|`ProcessorArchitecture`|İsteğe bağlı. Bu yükleme tarafından hedeflenen bilgisayar işlemcisi. Varsayılan değer `msil`.|  
  
## <a name="externalcheck"></a>ExternalCheck  
 Bu öğe bir isteğe bağlı bir alt öğesi olan `InstallChecks`. Her örneği için `ExternalCheck`, önyükleyici adlandırılmış dış program ayrı bir işlemde yürütür ve çıkış kodu tarafından gösterilen özellik depolamak `Property`. `ExternalCheck` karmaşık bağımlılık denetimlerini uygulamak için veya bir bileşen varlığını denetlemek için tek yolu, örneği olduğunda yararlıdır.  
  
 `ExternalCheck` öğe içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Property`|Gerekli. Sonucu depolamak için özelliğinin adı. Bu özellik altındaki bir testten başvurulabilir `InstallConditions` alt öğesi olarak `Command` öğesi. Daha fazla bilgi için bkz: [ \<komutları > öğesi](../deployment/commands-element-bootstrapper.md).|  
|`PackageFile`|Gerekli. Yürütmek için dış program. Program Kurulum dağıtım paketinin bir parçası olması gerekir.|  
|`Arguments`|İsteğe bağlı. Sağlayan komut satırı bağımsız değişkenleri tarafından adlı yürütülebilir `PackageFile`.|  
  
## <a name="filecheck"></a>FileCheck  
 Bu öğe bir isteğe bağlı bir alt öğesi olan `InstallChecks`. Her örneği için `FileCheck`, önyükleyici adlandırılmış dosyanın var olduğundan ve dosyanın sürüm numarasını döndürür olup olmadığını belirler. Dosya bir sürüm numarası yoksa önyükleyici tarafından adlı özelliği ayarlar `Property` 0. Dosya mevcut değilse `Property` herhangi bir değere ayarlı değil.  
  
 `FileCheck` öğe içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Property`|Gerekli. Sonucu depolamak için özelliğinin adı. Bu özellik altındaki bir testten başvurulabilir `InstallConditions` alt öğesi olarak `Command` öğesi. Daha fazla bilgi için bkz: [ \<komutları > öğesi](../deployment/commands-element-bootstrapper.md).|  
|`FileName`|Gerekli. Bulunacak dosyasının adı.|  
|`SearchPath`|Gerekli. Disk veya dosyayı aramak bir klasör. Bu göreli bir yol olmalıdır `SpecialFolder` atanır; Aksi halde, mutlak bir yol olmalıdır.|  
|`SpecialFolder`|İsteğe bağlı. Windows veya için özel bir önemi olan bir klasörü [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Yorumlamak için varsayılan değer `SearchPath` mutlak bir yol olarak. Geçerli değerler şunlardır:<br /><br /> `AppDataFolder`. Bu uygulama veri klasörü [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama; geçerli kullanıcı için belirli.<br /><br /> `CommonAppDataFolder`. Tüm kullanıcılar tarafından kullanılan uygulama veri klasörü.<br /><br /> `CommonFilesFolder`. Geçerli kullanıcı için ortak dosyalar klasörü.<br /><br /> `LocalDataAppFolder`. Gezici olmayan uygulamalar için veri klasörü.<br /><br /> `ProgramFilesFolder`. 32-bit uygulamalar için standart Program dosyaları klasörü.<br /><br /> `StartUpFolder`. Sistem başlangıcında başlatılan tüm uygulamaları içeren klasör.<br /><br /> `SystemFolder`. 32-bit sistem DLL'leri içeren klasör.<br /><br /> `WindowsFolder`. Windows Sistem yüklemesini içeren klasör.<br /><br /> `WindowsVolume`. Sürücü veya Windows Sistem yüklemesini içeren bölüm.|  
|`SearchDepth`|İsteğe bağlı. Derinliğinde adlandırılmış dosya alt klasörleri aramak için. Arama derinliği ilk olur. Aramayı belirtilen en üst düzey klasöre sınırlar 0 varsayılandır `SpecialFolder` ve **SearchPath**.|  
  
## <a name="msiproductcheck"></a>MsiProductCheck  
 Bu öğe bir isteğe bağlı bir alt öğesi olan `InstallChecks`. Her örneği için `MsiProductCheck`, önyükleyici belirtilen Microsoft Windows Installer yükleme tamamlanana kadar çalıştırılıp çalıştırılmadığını görmek için kontrol eder. Özellik değeri bu yüklenen ürünün durumuna bağlı olarak ayarlanır. Ürününün yüklü olduğu, pozitif bir değer gösterir 0 veya -1 gösterir, yüklü değil. (Lütfen Windows Installer SDK MsiQueryFeatureState daha fazla bilgi için bkz.) . Windows Installer bilgisayarda yüklü değilse `Property` ayarlı değil.  
  
 `MsiProductCheck` öğe içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Property`|Gerekli. Sonucu depolamak için özelliğinin adı. Bu özellik altındaki bir testten başvurulabilir `InstallConditions` alt öğesi olarak `Command` öğesi. Daha fazla bilgi için bkz: [ \<komutları > öğesi](../deployment/commands-element-bootstrapper.md).|  
|`Product`|Gerekli. Yüklü ürün için GUID.|  
|`Feature`|İsteğe bağlı. Yüklenen uygulamanın belirli bir özellik için GUID.|  
  
## <a name="registrycheck"></a>RegistryCheck  
 Bu öğe bir isteğe bağlı bir alt öğesi olan `InstallChecks`. Her örneği için `RegistryCheck`, önyükleyici belirtilen kayıt defteri anahtarının var olup var veya belirtilen değere olup olmadığını denetler.  
  
 `RegistryCheck` öğe içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Property`|Gerekli. Sonucu depolamak için özelliğinin adı. Bu özellik altındaki bir testten başvurulabilir `InstallConditions` alt öğesi olarak `Command` öğesi. Daha fazla bilgi için bkz: [ \<komutları > öğesi](../deployment/commands-element-bootstrapper.md).|  
|`Key`|Gerekli. Kayıt defteri anahtarı adı.|  
|`Value`|İsteğe bağlı. Almak için kayıt defteri değeri adı. Varsayılan değer metnin döndürmek için varsayılandır. `Value` bir dize veya bir DWORD olması gerekir.|  
  
## <a name="registryfilecheck"></a>RegistryFileCheck  
 Bu öğe bir isteğe bağlı bir alt öğesi olan `InstallChecks`. Her örneği için `RegistryFileCheck`, ilk yol dosyayı belirtilen kayıt defteri anahtarından almaya önyükleyici belirtilen dosya sürümünü alır. Kayıt defteri değer olarak belirtilen bir dizindeki dosyayı aramak istiyorsanız, bu özellikle yararlıdır.  
  
 `RegistryFileCheck` öğe içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Property`|Gerekli. Sonucu depolamak için özelliğinin adı. Bu özellik altındaki bir testten başvurulabilir `InstallConditions` alt öğesi olarak `Command` öğesi. Daha fazla bilgi için bkz: [ \<komutları > öğesi](../deployment/commands-element-bootstrapper.md).|  
|`Key`|Gerekli. Kayıt defteri anahtarı adı. Değeri bir dosya yolu olarak sürece yorumlanır `File` özniteliği olarak ayarlanmış. Bu anahtar mevcut değilse `Property` ayarlı değil.|  
|`Value`|İsteğe bağlı. Almak için kayıt defteri değeri adı. Varsayılan değer metnin döndürmek için varsayılandır. `Value` bir dize olmalıdır.|  
|`FileName`|İsteğe bağlı. Bir dosya adı. Belirtilmişse, kayıt defteri anahtarından alınan değer bir dizin yolu olarak kabul edilir ve bu ad ona eklenir. Belirtilmezse, kayıt defterinden döndürülen değer dosyasının tam yolunu olduğu varsayılır.|  
|`SearchDepth`|İsteğe bağlı. Derinliğinde adlandırılmış dosya alt klasörleri aramak için. Arama derinliği ilk olur. Varsayılan kayıt defteri anahtarının değeri tarafından belirtilen en üst düzey klasörü için arama kısıtlayan 0 ' dır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Altındaki öğeler `InstallChecks` testi tanımlamak, bunları yürütülmez. Testleri çalıştırmak için oluşturmalısınız `Command` öğeleri altında `Commands` öğesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde gösterilmektedir `InstallChecks` şekliyle öğe için ürün dosyasında kullanılır [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
```  
<InstallChecks>  
    <ExternalCheck Property="DotNetInstalled" PackageFile="dotnetchk.exe" />  
    <RegistryCheck Property="IEVersion" Key="HKLM\Software\Microsoft\Internet Explorer" Value="Version" />  
</InstallChecks>  
```  
  
## <a name="installconditions"></a>InstallConditions  
 Zaman `InstallChecks` olan değerlendirilemiyor özellikleri oluşturdukları. Özellikleri tarafından kullanılan `InstallConditions` bir paket yüklemek, atlama başarısız veya olup olmadığını belirlemek için. Aşağıdaki tabloda `InstallConditions`:  
  
|||  
|-|-|  
|`FailIf`|Varsa `FailIf` koşulu doğru olarak değerlendirir, paket başarısız olur. Koşulların geri kalanını değerlendirilmez.|  
|`BypassIf`|Varsa `BypassIf` koşulu doğru olarak değerlendirir, paket atlanır. Koşulların geri kalanını değerlendirilmez.|  
  
## <a name="predefined-properties"></a>Önceden tanımlanmış özellikler  
 Aşağıdaki tabloda `BypassIf` ve `FailIf` öğeleri:  
  
|Özellik|Notlar|Olası değerler|  
|--------------|-----------|---------------------|  
|`Version9X`|Bir Windows 9 X işletim sisteminin sürüm numarası.|4.10 Windows 98 =|  
|`VersionNT`|Windows NT tabanlı bir işletim sisteminin sürüm numarası.|Major.Minor.ServicePack<br /><br /> 5.0 = Windows 2000<br /><br /> 5.1.0 Windows XP =<br /><br /> 5.1.2 Windows XP Professional SP2 =<br /><br /> 5.2.0 Windows Server 2003 =|  
|`VersionNT64`|64-bit Windows NT tabanlı bir işletim sisteminin sürüm numarası.|Daha önce açıklanan olarak aynı.|  
|`VersionMsi`|Windows Installer hizmeti sürüm numarası.|2.0 Windows Installer 2.0 =|  
|`AdminUser`|Bir kullanıcı bir Windows NT tabanlı işletim sistemi üzerinde yönetici ayrıcalıklarına sahip olup olmadığını belirtir.|0 = yönetici ayrıcalığı yok<br /><br /> 1 = yönetici ayrıcalıkları|  
  
 Örneğin, Windows 95 çalıştıran bir bilgisayara yükleme engellemek için aşağıdaki gibi kod kullanın:  
  
```  
<!-- Block install on Windows 95 -->  
    <FailIf Property="Version9X" Compare="VersionLessThan" Value="4.10" String="InvalidPlatform"/>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Komutlar > öğesi](../deployment/commands-element-bootstrapper.md)   
 [Ürün ve Paket Şema Başvurusu](../deployment/product-and-package-schema-reference.md)