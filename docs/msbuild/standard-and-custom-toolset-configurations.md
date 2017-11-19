---
title: "Standart ve özel araç takımı yapılandırmaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, custom toolset configurations
- MSBuild, msbuild.exe.config
ms.assetid: 15a048c8-5ad3-448e-b6e9-e3c5d7147ed2
caps.latest.revision: "31"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: a1b0b6e2cc44193a684c6f411df908b0a54d31f1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="standard-and-custom-toolset-configurations"></a>Standart ve Özel Araç Takımı Yapılandırmaları
MSBuild araç takımı görevleri, hedefler ve bir uygulama projesi oluşturmak için kullanabileceğiniz araçları başvurular içeriyor. Standart bir araç takımı MSBuild içerir, ancak özel Toolsets de oluşturabilirsiniz. Bir araç takımı belirtme hakkında daha fazla bilgi için bkz: [araç takımı (ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md)  
  
## <a name="standard-toolset-configurations"></a>Standart araç takımı yapılandırmaları  
 MSBuild 12.0 aşağıdaki standart Toolsets içerir:  
  
|ToolsVersion|Araç takımı yolu (MSBuildToolsPath veya MSBuildBinPath yapı özelliğinde belirtildiği şekilde)|  
|------------------|--------------------------------------------------------------------------------------------|  
|2,0|*Windows yükleme yolu*\Microsoft.Net\Framework\v2.0.50727\|  
|3.5|*Windows yükleme yolu*\Microsoft.NET\Framework\v3.5\|  
|4.0|*Windows yükleme yolu*\Microsoft.NET\Framework\v4.0.30319\|  
|12.0|*% ProgramFiles %*\MSBuild\12.0\bin|  
  
 `ToolsVersion` Değerini belirleyen araç takımı tarafından kullanılan Visual Studio'nun oluşturduğu bir proje. İçinde [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)] varsayılan değer "12.0" (olsun, proje dosyasında belirtilen hangi sürümü), ancak kullanarak bu özniteliği geçersiz kılabilirsiniz **/toolsversion** geçiş komut isteminde. Bu öznitelik ve belirtmek üzere diğer yöntemler hakkında bilgi için `ToolsVersion`, bkz: [ToolsVersion ayarlarını geçersiz kılma](../msbuild/overriding-toolsversion-settings.md).  
  
 Varsa `ToolsVersion` belirlenmezse, kayıt defteri anahtarı **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSBuild\\< sürüm numarası\>\DefaultToolsVersion** tanımlar `ToolsVersion`, olduğu her zaman 2.0.  
  
 Aşağıdaki kayıt defteri anahtarlarını MSBuild.exe yükleme yolunu belirtin.  
  
|Kayıt Defteri Anahtarı|Anahtar adı|Dize anahtar değeri|  
|------------------|--------------|----------------------|  
|\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSBuild\ToolsVersions\2.0\|MSBuildToolsPath|.NET framework 2.0 yükleme yolu|  
|\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ MSBuild\ToolsVersions\3.5\|MSBuildToolsPath|.NET framework 3.5 yükleme yolu|  
|\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ MSBuild\ToolsVersions\4.0\|MSBuildToolsPath|.NET framework 4 yükleme yolu|  
|\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ MSBuild\ToolsVersions\12.0\|MSBuildToolsPath|MSBuild yükleme yolu|  
  
### <a name="sub-toolsets"></a>Sub toolsets  
 Önceki tabloda kayıt defteri anahtarını bir alt anahtarı varsa, MSBuild, bir alt araç takımı yolunu üst araç takımı yolunda geçersiz kılabilir belirlemek için kullanır. Aşağıdaki alt anahtarını bir örnek verilmiştir:  
  
 \HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSBuild\ToolsVersions\12.0\12.0  
  
 Herhangi bir özellik hem temel araç takımı hem de seçilen alt toolset tanımlanmışsa, alt takımında özellik tanımları kullanılır. Örneğin, MSBuild 4.0 araç takımı tanımlar `SDK40ToolsPath` SDK ancak 4.0\11.0 MSBuild için 7.0a işaret edecek şekilde araç takımı için 8.0a işaret etmek için aynı özelliği tanımlar SDK. Varsa `VisualStudioVersion` ayarlanmamış, `SDK40ToolsPath` varsa ancak 7.0a işaret eden `VisualStudioVersion` özelliği 8.0a için bunun yerine noktasında olduğu 11.0 için ayarlanır.  
  
 `VisualStudioVersion` Derleme özelliği, bir alt araç takımı etkin hale olup olmadığını belirtir. Örneğin, bir `VisualStudioVersion` "12.0" değerini MSBuild 12.0 alt toolset belirtir. Daha fazla bilgi için alt toolsets bölümüne bakın [araç takımı (ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md).  
  
> [!NOTE]
>  Bu ayarları değiştirmekten kaçının öneririz. Bununla birlikte, kendi ayarları ekleyin ve bilgisayar genelinde özel araç takımı tanımları, sonraki bölümde açıklandığı gibi tanımlayın.  
  
## <a name="custom-toolset-definitions"></a>Özel araç takımı tanımları  
 Standart bir araç takımı yapı gereksinimlerinizi karşılamak değil, özel bir araç takımı oluşturabilirsiniz. Örneğin, hangi olmalıdır oluşturmak için ayrı bir sistemi yapı laboratuvarı senaryo olabilir [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projeleri. Özel araç takımı kullanarak özel değerler atayabilirsiniz `ToolsVersion` özniteliği projeleri oluşturduğunuzda ya da MSBuild.exe çalıştırın. Bunu yaparak, ayrıca kullanabileceğiniz `$(MSBuildToolsPath)` bu dizine yanı sıra, bu araç takımı kullanan herhangi bir proje için kullanılabilmesi için kendi özel araç takımı özellikleri tanımlamaya .targets dosyaları aktarmak için özellik.  
  
 Özel araç takımı MSBuild.exe (veya MSBuild altyapısı, kullanmakta olduğunuz ise barındıran özel aracı) yapılandırma dosyasında belirtin. Örneğin, ToolsVersion 12.0 varsayılan davranışını geçersiz kılmak istediğinizde, aşağıdaki araç takımı tanımını MSBuild.exe için yapılandırma dosyası içerebilir.  
  
```xml  
<msbuildToolsets default="12.0">  
   <toolset toolsVersion="12.0">  
      <property name="MSBuildToolsPath"   
        value="C:\SpecialPath" />  
   </toolset>  
</msbuildToolsets>  
```  
  
 `<msbuildToolsets>`Ayrıca yapılandırma dosyasında şu şekilde tanımlanması gerekir.  
  
```xml  
<configSections>  
   <section name="msbuildToolsets"         
       Type="Microsoft.Build.BuildEngine.ToolsetConfigurationSection,   
       Microsoft.Build.Engine, Version=12.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a"  
   </section>  
</configSections>  
```  
  
> [!NOTE]
>  Doğru okumaya `<configSections>` ilk alt bölümde olmalıdır `<configuration>` bölümü.  
  
 `ToolsetConfigurationSection`Tüm MSBuild ana bilgisayar tarafından özel yapılandırma için kullanılabilir bir özel yapılandırma bölümüdür. Özel araç takımı kullanırsanız, bir ana bilgisayar yapılandırma dosyası girdileri sağlamak dışında yapı altyapısı başlatılamadı bir şey yapmanız gerekmez. Kayıt defterinde girişleri tanımlayarak MSBuild.exe için geçerli bilgisayar genelinde Toolsets belirtebilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ve MSBuild, tüm ana bilgisayarlar.  
  
> [!NOTE]
>  Bir yapılandırma dosyası için ayarları tanımlıyorsa bir `ToolsVersion` , önceden tanımlanmış kayıt defterinde, iki tanımları birleştirilmez. Yapılandırma dosyası tanımında önceliği ve ayarları kayıt defterine için alan `ToolsVersion` göz ardı edilir.  
  
 Aşağıdaki özellikler değerine belirli `ToolsVersion` diğer bir deyişle kullanılan projeleri:  
  
-   **$(MSBuildBinPath)** ayarlanır `ToolsPath` kayıt defteri veya yapılandırma dosyasında belirtilen değeri burada `ToolsVersion` tanımlanır. `$(MSBuildToolsPath)` Kayıt defteri veya yapılandırma dosyası ayarı çekirdek görev ve hedeflerini konumunu belirtir. Proje dosyasında bu $(MSBuildBinPath) özelliği ve ayrıca $(MSBuildToolsPath) özelliği eşler.  
  
-   `$(MSBuildToolsPath)`yapılandırma dosyasında belirtilen MSBuildToolsPath özelliği tarafından sağlanan ayrılmış bir özelliktir. (Bu özellik değiştirir `$(MSBuildBinPath)`. Ancak, `$(MSBuildBinPath)` ileriye doğru uyumluluk için gerçekleştirilir.) Özel araç takımı ya da tanımlamanız gerekir `$(MSBuildToolsPath)` veya `$(MSBuildBinPath)` ancak ikisi birden değil, her ikisi de aynı değere sahip değilse.  
  
 Ayrıca, MSBuildToolsPath özelliği eklemek için kullandığınız aynı sözdizimini kullanarak, ToolsVersion özgü özel özellikleri yapılandırma dosyasına ekleyebilirsiniz. Bu özel özellikler proje dosyasını kullanılabilir hale getirmek için yapılandırma dosyasında belirtilen değerin adıyla aynı adı kullanın. Yapılandırma dosyasında toolsets ancak olmayan alt toolsets tanımlayabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araç Takımı (ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md)