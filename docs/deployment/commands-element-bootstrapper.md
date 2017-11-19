---
title: "&lt;Komutları&gt; öğe (Önyükleyici) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords: <Commands> element [bootstrapper]
ms.assetid: e61d5787-fe1f-4ebf-b0cf-0d7909be7ffb
caps.latest.revision: "13"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: ac8580a1b930d4ad18db9eebb275e4eb67d80c62
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="ltcommandsgt-element-bootstrapper"></a>&lt;Komutları&gt; öğe (Önyükleyici)
`Commands` Öğesi uygulayan altındaki öğeler tarafından açıklanan testleri `InstallChecks` öğesi ve hangi paket bildirir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] önyükleyici sınama başarısız olursa yüklemelisiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Commands  
    Reboot  
>  
    <Command  
        PackageFile  
        Arguments  
        EstimatedInstallSeconds  
        EstimatedDiskBytes  
        EstimatedTempBytes  
        Log  
    >  
        <InstallConditions>  
            <BypassIf   
                Property  
                Compare  
                Value  
                Schedule  
            />  
            <FailIf   
                Property  
                Compare  
                Value  
                String  
                Schedule  
            />  
        </InstallConditions>  
        <ExitCodes>  
            <ExitCode   
                Value  
                Result  
                String  
            />  
        </ExitCodes>  
    </Command>  
</Commands>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `Commands` Öğesi gereklidir. Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Reboot`|İsteğe bağlı. Paketlerin herhangi bir yeniden başlatma çıkış kodu döndürmesi durumunda sistemin yeniden başlatılıp başlatılmayacağını belirler. Aşağıdaki listede, geçerli değerleri gösterir:<br /><br /> `Defer`. Yeniden başlatma gelecekteki bir süreye kadar ertelenir.<br /><br /> `Immediate`. Paketlerden birini bir yeniden başlatma çıkış kodu döndürdü, hemen bir yeniden başlatma neden olur.<br /><br /> `None`. Herhangi bir yeniden başlatma isteğinin yoksayılmasına neden olur.<br /><br /> Varsayılan, `Immediate` değeridir.|  
  
## <a name="command"></a>Komut  
 `Command` Öğesi bir alt öğedir `Commands` öğesi. A `Commands` öğesi bir veya daha fazla olabilir `Command` öğeleri. Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`PackageFile`|Gerekli. Bir veya daha fazla tarafından belirtilen koşullar yüklemek için paketin adı gereken `InstallConditions` false döndürür. Paket kullanarak aynı dosyada tanımlanmalıdır bir `PackageFile` öğesi.|  
|`Arguments`|İsteğe bağlı. Paket dosyasına geçirilecek komut satırı bağımsız değişkenleri kümesi.|  
|`EstimatedInstallSeconds`|İsteğe bağlı. Tahmini süre, saniye cinsinden, paketi yüklemek için yönlendirir. Bu değer kullanıcı için önyükleyici görüntüler ilerleme çubuğu boyutunu belirler. Varsayılan 0; Bu durumda tahmin belirtilen hiçbir zaman'dır.|  
|`EstimatedDiskBytes`|İsteğe bağlı. Tahmini disk miktarını, paket yükleme sonrasında kaplar bayt cinsinden tamamlandı. Bu değer, kullanıcıya önyükleyici görüntüler sabit disk alanı gereksinimleri, kullanılır. Varsayılan durumlarda önyükleyici tüm sabit disk alanı gereksinimleri görüntülemez 0 ' dır.|  
|`EstimatedTempBytes`|İsteğe bağlı. Paket gerektirir bayt cinsinden geçici disk alanı tahmini miktarı.|  
|`Log`|İsteğe bağlı. Paket, paketin kök dizini göreli oluşturur günlük dosyası yolu.|  
  
## <a name="installconditions"></a>InstallConditions  
 `InstallConditions` Bir alt öğedir `Command` öğesi. Her `Command` öğesi en fazla bir olabilir `InstallConditions` öğesi. Öyle değilse `InstallConditions` öğesi yoksa, tarafından belirtilen paket `Condition` her zaman çalışır.  
  
## <a name="bypassif"></a>BypassIf  
 `BypassIf` Bir alt öğedir `InstallConditions` öğesi ve komut değil yürütülmelidir altında pozitif bir koşulu açıklar. Her `InstallConditions` öğesi sıfır veya daha fazla olabilir `BypassIf` öğeleri.  
  
 `BypassIf`Aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Property`|Gerekli. Test edilecek özelliğin adı. Özelliği daha önce alt öğesi tarafından tanımlanmış gerekir `InstallChecks` öğesi. Daha fazla bilgi için bkz: [ \<InstallChecks > öğesi](../deployment/installchecks-element-bootstrapper.md).|  
|`Compare`|Gerekli. Gerçekleştirmek karşılaştırma türü. Aşağıdaki listede, geçerli değerleri gösterir:<br /><br /> `ValueEqualTo`, `ValueNotEqualTo`, `ValueGreaterThan`, `ValueGreaterThanOrEqualTo`, `ValueLessThan`, `ValueLessThanOrEqualTo`, `VersionEqualTo`, `VersionNotEqualTo`, `VersionGreaterThan`, `VersionGreaterThanOrEqualTo`, `VersionLessThan`, `VersionLessThanOrEqualTo`, `ValueExists`, `ValueNotExists`|  
|`Value`|Gerekli. Özellikle Karşılaştırılacak değer.|  
|`Schedule`|İsteğe bağlı. Adı bir `Schedule` bu kuralın ne zaman değerlendirilmelidir tanımlayan etiket.|  
  
## <a name="failif"></a>FailIf  
 `FailIf` Bir alt öğedir `InstallConditions` öğesi ve altında yüklemenin durması gereken pozitif bir koşulu açıklar. Her `InstallConditions` öğesi sıfır veya daha fazla olabilir `FailIf` öğeleri.  
  
 `FailIf`Aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Property`|Gerekli. Test edilecek özelliğin adı. Özelliği daha önce alt öğesi tarafından tanımlanmış gerekir `InstallChecks` öğesi. Daha fazla bilgi için bkz: [ \<InstallChecks > öğesi](../deployment/installchecks-element-bootstrapper.md).|  
|`Compare`|Gerekli. Gerçekleştirmek karşılaştırma türü. Aşağıdaki listede, geçerli değerleri gösterir:<br /><br /> `ValueEqualTo`, `ValueNotEqualTo`, `ValueGreaterThan`, `ValueGreaterThanOrEqualTo`, `ValueLessThan`, `ValueLessThanOrEqualTo`, `VersionEqualTo`, `VersionNotEqualTo`, `VersionGreaterThan`, `VersionGreaterThanOrEqualTo`, `VersionLessThan`, `VersionLessThanOrEqualTo`, `ValueExists`, `ValueNotExists`|  
|`Value`|Gerekli. Özellikle Karşılaştırılacak değer.|  
|`String`|İsteğe bağlı. Hata sonrasında kullanıcıya görüntülenecek metin.|  
|`Schedule`|İsteğe bağlı. Adı bir `Schedule` bu kuralın ne zaman değerlendirilmelidir tanımlayan etiket.|  
  
## <a name="exitcodes"></a>ExitCodes  
 `ExitCodes` Bir alt öğedir `Command` öğesi. `ExitCodes` Öğesi içeren bir veya daha fazla `ExitCode` yükleme paketinden yanıt olarak bir çıkış kodu yapmalısınız belirlemek öğeleri. Bir olabilir isteğe bağlı `ExitCode` öğesinin altında bir `Command` öğesi. `ExitCodes`öznitelikleri yok.  
  
## <a name="exitcode"></a>exitCode  
 `ExitCode` Bir alt öğedir `ExitCodes` öğesi. `ExitCode` Öğesi belirler yükleme paketinden yanıt olarak bir çıkış kodu yapmalısınız. `ExitCode`Aşağıdaki özniteliklere sahiptir ve alt öğeleri içerir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Value`|Gerekli. Bu çıkış kodu değerini `ExitCode` öğesine uygular.|  
|`Result`|Gerekli. Yükleme bu çıkış koduna nasıl tepki vermelidir. Aşağıdaki listede, geçerli değerleri gösterir:<br /><br /> `Success`. Paket başarıyla yüklendi olarak işaretler.<br /><br /> `SuccessReboot`. Paketi başarıyla yüklendi olarak işaretler ve sistemin yeniden yönlendirir.<br /><br /> `Fail`. Paket başarısız olarak işaretler.<br /><br /> `FailReboot`. Paket başarısız olarak işaretler ve sistemin yeniden yönlendirir.|  
|`String`|İsteğe bağlı. Bu çıkış koduna yanıtta kullanıcıya görüntülenecek değer.|  
|`FormatMessageFromSystem`|İsteğe bağlı. Çıkış kodu ile ilişkili sistem tarafından sağlanan hata iletisini kullanın veya sağlanan değer kullanmayı belirler `String`. Geçerli değerler `true`, başka bir deyişle, sistem tarafından sağlanan hata kullanılacak ve `false`, yani tarafından sağlanan dizeyi kullanmak `String`. Varsayılan, `false` değeridir. Bu özellik ise `false`, ancak `String` ayarlanmazsa sistem tarafından sağlanan hata kullanılacaktır.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, .NET Framework 2.0 yükleme komutları tanımlar.  
  
```  
<Commands Reboot="Immediate">  
    <Command PackageFile="instmsia.exe"  
             Arguments= ' /q /c:"msiinst /delayrebootq"'  
             EstimatedInstallSeconds="20" >  
        <InstallConditions>  
           <BypassIf Property="VersionNT" Compare="ValueExists"/>  
             BypassIf Property="VersionMsi" Compare="VersionGreaterThanOrEqualTo" Value="2.0"/>  
        </InstallConditions>  
        <ExitCodes>  
            <ExitCode Value="0" Result="SuccessReboot"/>  
            <ExitCode Value="1641" Result="SuccessReboot"/>  
            <ExitCode Value="3010" Result="SuccessReboot"/>  
            <DefaultExitCode Result="Fail" FormatMessageFromSystem="true" String="GeneralFailure" />  
        </ExitCodes>  
    </Command>  
    <Command PackageFile="WindowsInstaller-KB884016-v2-x86.exe"  
             Arguments= '/quiet /norestart'   
             EstimatedInstallSeconds="20" >  
      <InstallConditions>  
          <BypassIf Property="Version9x" Compare="ValueExists"/>  
          <BypassIf Property="VersionNT" Compare="VersionLessThan" Value="5.0.3"/>  
          <BypassIf Property="VersionMsi" Compare="VersionGreaterThanOrEqualTo" Value="3.0"/>  
          <FailIf Property="AdminUser" Compare="ValueEqualTo" Value="false" String="AdminRequired"/>  
      </InstallConditions>  
      <ExitCodes>  
          <ExitCode Value="0" Result="Success"/>  
          <ExitCode Value="1641" Result="SuccessReboot"/>  
          <ExitCode Value="3010" Result="SuccessReboot"/>  
          <DefaultExitCode Result="Fail" FormatMessageFromSystem="true" String="GeneralFailure" />  
      </ExitCodes>  
    </Command>  
    <Command PackageFile="dotnetfx.exe"   
         Arguments=' /q:a /c:"install /q /l"'   
         EstimatedInstalledBytes="21000000"   
         EstimatedInstallSeconds="300">  
  
        <!-- These checks determine whether the package is to be installed -->  
        <InstallConditions>  
            <!-- Either of these properties indicates the .NET Framework is already installed -->  
            <BypassIf Property="DotNetInstalled" Compare="ValueNotEqualTo" Value="0"/>  
  
            <!-- Block install if user does not have adminpermissions -->  
            <FailIf Property="AdminUser" Compare="ValueEqualTo" Value="false" String="AdminRequired"/>  
  
            <!-- Block install on Windows 95 -->  
            <FailIf Property="Version9X" Compare="VersionLessThan" Value="4.10" String="InvalidPlatformWin9x"/>  
  
            <!-- Block install on Windows 2000 SP 2 or less -->  
            <FailIf Property="VersionNT" Compare="VersionLessThan" Value="5.0.3" String="InvalidPlatformWinNT"/>  
  
            <!-- Block install if Internet Explorer 5.01 or later is not present -->  
            <FailIf Property="IEVersion" Compare="ValueNotExists" String="InvalidPlatformIE" />  
            <FailIf Property="IEVersion" Compare="VersionLessThan" Value="5.01" String="InvalidPlatformIE" />  
  
            <!-- Block install if the operating system does not support x86 -->  
            <FailIf Property="ProcessorArchitecture" Compare="ValueNotEqualTo" Value="Intel" String="InvalidPlatformArchitecture" />  
       </InstallConditions>  
  
        <ExitCodes>  
            <ExitCode Value="0" Result="Success"/>  
            <ExitCode Value="3010" Result="SuccessReboot"/>  
            <ExitCode Value="4097" Result="Fail" String="AdminRequired"/>  
            <ExitCode Value="4098" Result="Fail" String="WindowsInstallerComponentFailure"/>  
            <ExitCode Value="4099" Result="Fail" String="WindowsInstallerImproperInstall"/>  
            <ExitCode Value="4101" Result="Fail" String="AnotherInstanceRunning"/>  
            <ExitCode Value="4102" Result="Fail" String="OpenDatabaseFailure"/>  
            <ExitCode Value="4113" Result="Fail" String="BetaNDPFailure"/>  
            <DefaultExitCode Result="Fail" FormatMessageFromSystem="true" String="GeneralFailure" />  
        </ExitCodes>  
  
    </Command>  
</Commands>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ürün ve paket şema başvurusu](../deployment/product-and-package-schema-reference.md)   
 [\<InstallChecks > öğesi](../deployment/installchecks-element-bootstrapper.md)