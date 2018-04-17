---
title: 'Nasıl yapılır: Gereci için Web.Config dosyalarını değiştirme ve dinamik olarak derlenmiş ASP.NET Web uygulamalarında profil | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: a92e5692-2183-4ae3-9431-b067c6a7aab4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 427a0d0de82ba5957422fdd9b2db6067ece2f4f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-modify-webconfig-files-to-instrument-and-profile-dynamically-compiled-aspnet-web-applications"></a>Nasıl yapılır: Dinamik Olarak Derlenmiş ASP.NET Web Uygulamalarını İzlemek ve Profilini Oluşturmak için Web.Config Dosyalarını Değiştirme
Kullanabileceğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ayrıntılı zamanlama verileri, .NET bellek ayırma verileri ve .NET nesne yaşam süresi verilerini dinamik olarak toplamak için profil oluşturma araçları izleme yöntemini derlenmiş [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulamaları.  
  
 Bu konu, araçları ve, profil oluşturma etkinleştirmek için web.config yapılandırma dosyasını değiştirmek açıklar [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulamaları.  
  
> [!NOTE]
>  Örnekleme profili oluşturma yöntemi kullandığınızda veya önceden derlenmiş işaretlemesini istediğinizde web.config dosyasını değiştirmeniz gerekmez [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] modülü.  
  
 Kök web.config dosyasının **yapılandırma** öğesi. İzleme ve dinamik olarak derlenmiş profil için [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması, ekleyin veya aşağıdaki öğeleri değiştirmeniz gerekir:  
  
-   A **yapılandırma/çalışma zamanı/assemblyBinding/dependentAssembly** profil denetimleri Microsoft.VisualStudio.Enterprise.ASPNetHelper derleme tanımlayan öğesi. **DependentAssembly** öğesi iki alt öğeleri içerir: **assemblyIdentity** ve **codeBase**.  
  
-   A **configuration/system.web/compilation** hedef derleme için profil oluşturucu işlem sonrası derleme adımı tanımlayan öğesi.  
  
-   İki **ekleme** profil oluşturma Araçlar konumunu tanımlamak öğeleri eklenir **configuration/appSettings** bölümü.  
  
 Uygulamanın yapılandırmayı geri yüklemek için kullanabileceğiniz özgün web.config dosyasının bir kopyasını oluşturmanızı öneririz.  
  
### <a name="to-add-the-aspnethelper-assembly-as-a-configurationruntimeassemblybindingdependentassembly-element"></a>Bir yapılandırma/çalışma zamanı/assemblyBinding/dependentAssembly öğesi olarak ASPNetHelper derleme eklemek için  
  
1.  Gerekirse, ekleyin **çalışma zamanı** öğesi bir alt öğesi olarak **yapılandırma** öğesi; Aksi halde, sonraki adıma geçin.  
  
     **Çalışma zamanı** öğesi özniteliklere sahip değildir. **Yapılandırma** öğesi yalnızca bir tane olabilir **çalışma zamanı** alt öğesi.  
  
2.  Gerekirse, ekleyin **assemblyBinding** öğesi bir alt öğesi olarak **çalışma zamanı** öğesi; Aksi halde, sonraki adıma geçin.  
  
     **Çalışma zamanı** öğesi yalnızca bir tane olabilir **assemblyBinding** öğesi.  
  
3.  Aşağıdaki öznitelik adı ekleyin ve değerini **assemblyBinding** öğe:  
  
    |Öznitelik adı|Öznitelik değeri|  
    |--------------------|---------------------|  
    |**Xmlns**|**urn: şemaları-microsoft-com:asm.v1**|  
  
4.  Ekleme bir **dependentAssembly** öğesi bir alt öğesi olarak **assemblyBinding** öğesi.  
  
     **DependentAssembly** öğesi özniteliklere sahip değildir.  
  
5.  Ekleme bir **assemblyIdentity** öğesi bir alt öğesi olarak **dependentAssembly** öğesi.  
  
6.  Aşağıdaki öznitelik adları ve değerleri ekleme **assemblyIdentity** öğe:  
  
    |Öznitelik adı|Öznitelik değeri|  
    |--------------------|---------------------|  
    |**Adı**|**Microsoft.VisualStudio.Enterprise.ASPNetHelper**|  
    |**PublicKeyToken**|**b03f5f7f11d50a3a**|  
    |**Kültür**|**Nötr**|  
  
7.  Ekleme bir **codeBase** öğesi bir alt öğesi olarak **dependentAssembly** öğesi.  
  
8.  Aşağıdaki öznitelik adları ve değerleri ekleme **codeBase** öğe:  
  
    |Öznitelik adı|Öznitelik değeri|  
    |--------------------|---------------------|  
    |**Sürüm**|**10.0.0.0**|  
    |**href**|`PathToASPNetHelperDll`|  
  
     `PathToASPNetHelperDll` Microsoft.VisualStudio.Enterprise.ASPNetHelper.dll dosya URL'sidir. Varsa [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] varsayılan konumda yüklü **href** değeri olmalıdır `C:/Program%20Files/Microsoft%20Visual%20Studio%202010.0/Common7/IDE/PrivateAssemblies/Microsoft.VisualStudio.Enterprise.ASPNetHelper.DLL`  
  
```  
    <configuration>  
        <runtime>  
            <assemblyBinding   
                xmlns="urn:schemas-microsoft-com:asm.v1"  
            >  
                <dependentAssembly>  
                    <assemblyIdentity                         name="Microsoft.VisualStudio.Enterprise.ASPNetHelper"   
                        publicKeyToken="b03f5f7f11d50a3a"                         culture="neutral"   
                    />  
                    <codeBase   
                        version="10.0.0.0"  
                        href="file:///C:/Program%20Files/Microsoft%20Visual%20Studio%2010.0/Common7/IDE/PrivateAssemblies/Microsoft.VisualStudio.Enterprise.ASPNetHelper.DLL"   
                    />  
                </dependentAssembly>  
            </assemblyBinding>  
        </runtime>  
```  
  
### <a name="to-add-the-profiler-post-process-step-to-the-configurationsystemwebcompilation-element"></a>Profil Oluşturucu işlem sonrası adımı configuration/system.web/compilation öğesine eklemek için  
  
1.  Gerekirse, ekleyin **system.web** öğesi bir alt öğesi olarak **yapılandırma** öğesi; Aksi halde, sonraki adıma geçin.  
  
     **System.web** öğesi özniteliklere sahip değildir. **Yapılandırma** öğesi yalnızca bir tane olabilir **system.web** alt öğesi.  
  
2.  Gerekirse, ekleyin **derleme** öğesi bir alt öğesi olarak **system.web** öğesi; Aksi halde, sonraki adıma geçin.  
  
     **System.web** öğesi yalnızca bir tane olabilir **derleme** alt öğesi.  
  
3.  Var olan tüm özniteliklerini kaldırmak **derleme** öğesini ve aşağıdaki öznitelik adı ve değeri ekleyin:  
  
    |Öznitelik adı|Öznitelik değeri|  
    |--------------------|---------------------|  
    |**assemblyPostProcessorType**|**Microsoft.VisualStudio.Enterprise.Common.AspPerformanceInstrumenter, Microsoft.VisualStudio.Enterprise.ASPNetHelper, sürüm 10.0.0.0, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a**|  
  
```  
    <configuration>  
        <runtime>  
        . . .  
        </runtime>  
        <system.web>  
            <compilation  
                assemblyPostProcessorType="Microsoft.VisualStudio.Enterprise.Common.AspPerformanceInstrumenter,  
                    Microsoft.VisualStudio.Enterprise.ASPNetHelper,  
                    Version=10.0.0.0,  
                    Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"   
            />  
        </system.web>  
    <configuration>  
```  
  
### <a name="to-add-profiler-location-settings-to-the-configurationappsettings-element"></a>Profil Oluşturucu konumu ayarları configuration/appSettings öğesine eklemek için  
  
1.  Gerekirse, ekleyin **appSettings** öğesi bir alt öğesi olarak **yapılandırma** öğesi; Aksi halde, sonraki adıma geçin.  
  
     **AppSettings** öğesi özniteliklere sahip değildir. **Yapılandırma** öğesi yalnızca bir tane olabilir **appSettings** alt öğesi.  
  
2.  Ekleme bir **ekleme** öğesi bir alt öğesi olarak **appSettings** öğesi.  
  
3.  Aşağıdaki öznitelik adları ve değerleri ekleme **ekleme** öğe:  
  
    |Öznitelik adı|Öznitelik değeri|  
    |--------------------|---------------------|  
    |**Anahtarı**|**Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrLocation**|  
    |**value**|`PerformanceToolsFolder` **\VSInstr.exe**|  
  
4.  Başka bir tane eklemek **ekleme** öğesi bir alt öğesi olarak **appSettings** öğesi.  
  
5.  Aşağıdaki öznitelik adları ve değerleri için ekleyin **ekleme** öğe:  
  
    |Öznitelik adı|Öznitelik değeri|  
    |--------------------|---------------------|  
    |**Anahtarı**|**Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrTools**|  
    |**value**|`PerformanceToolsFolder`|  
  
     `PerformanceToolsFolder` Profil Oluşturucu yürütülebilir dosyalar yoludur. Varsa [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklü olduğu varsayılan konumda değer olacaktır **C:\Program Files\Microsoft Visual Studio 10.0\Team Araçlar\Performans araçları**  
  
```  
    <configuration>  
        <runtime>  
        . . .  
        </runtime>  
        . . .  
        <system.web>  
        </system.web>  
        <appSettings>  
            <add  
                key="Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrLocation"  
                value="C:\Program Files\Microsoft Visual Studio 10.0\Team Tools\Performance Tools\vsinstr.exe"  
        />  
            <add  
                key="Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrTools"  
                value="C:\Program Files\Microsoft Visual Studio 10.0\Team Tools\Performance Tools\"  
            />  
        </appSettings>  
    </configuration>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki izleme ve, profil olanak sağlayan bir tam web.config dosyasıdır dinamik olarak derlenmiş [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulamaları. Bu örnek, herhangi bir değişiklik yapılmadan önce dosya ayarlarında olduğunu varsayar.  
  
```  
<?xml version="1.0"?>  
    <configuration>  
        <runtime>  
            <assemblyBinding   
                xmlns="urn:schemas-microsoft-com:asm.v1"  
            >  
                <dependentAssembly>  
                    <assemblyIdentity   
                        name="Microsoft.VisualStudio.Enterprise.ASPNetHelper"   
                        publicKeyToken="b03f5f7f11d50a3a"  
                        culture="neutral"   
                    />  
                    <codeBase   
                        version="10.0.0.0"  
                        href="file:///C:/Program%20Files/Microsoft%20Visual%20Studio%2010.0/Common7/IDE/PrivateAssemblies/Microsoft.VisualStudio.Enterprise.ASPNetHelper.DLL"   
                    />  
                </dependentAssembly>  
            </assemblyBinding>  
        </runtime>  
        <system.web>  
            <compilation  
                assemblyPostProcessorType="Microsoft.VisualStudio.Enterprise.Common.AspPerformanceInstrumenter,  
                    Microsoft.VisualStudio.Enterprise.ASPNetHelper,  
                    Version=10.0.0.0,  
                    Culture=neutral,  
                    PublicKeyToken=b03f5f7f11d50a3a"   
            />  
        </system.web>  
        <appSettings>  
            <add  
                key="Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrLocation"  
                value="C:\Program Files\Microsoft Visual Studio 10.0\Team Tools\Performance Tools\vsinstr.exe"  
            />  
            <add  
                key="Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrTools"  
                value="C:\Program Files\Microsoft Visual Studio 10.0\Team Tools\Performance Tools\"  
            />  
        </appSettings>  
    </configuration>  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: dinamik olarak derlenmiş bir ASP.NET uygulamasını izleme ve ayrıntılı zamanlama verileri toplama](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-detailed-timing-data-with-the-profiler.md)   
 [Nasıl yapılır: dinamik olarak derlenmiş bir ASP.NET uygulamasını izleme ve bellek verileri toplama](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)