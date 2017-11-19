---
title: "ToolsVersion ayarlarını geçersiz kılma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, overriding ToolsVersion setting
- MSBuild, building solutions with
ms.assetid: ccd42c07-0fb6-4e8b-9ebb-a6a6db18aa2e
caps.latest.revision: "24"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 5072e552d0e8527caeb95edc65d8717bece036c9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="overriding-toolsversion-settings"></a>ToolsVersion Ayarlarını Geçersiz Kılma
Projeler ve çözümler üç yöntemden biri için araç kümesi değiştirebilirsiniz:  
  
1.  kullanarak `/ToolsVersion` geçiş (veya `/tv`, kısaca) proje ya da komut satırından çözüm oluşturduğunuzda  
  
2.  ayarlayarak `ToolsVersion` parametresi MSBuild görevi  
  
3.  ayarlayarak `$(ProjectToolsVersion)` bir çözüm içindeki bir proje üzerinde özelliği. Bu proje diğer projeleri farklı bir araç takımının sürüm ile bir çözümde oluşturmanıza olanak sağlar.  
  
## <a name="override-the-toolsversion-settings-of-projects-and-solutions-on-command-line-builds"></a>Projeler ve çözümler komut satırı derlemeleri üzerinde ToolsVersion ayarlarını geçersiz kıl  
 Visual Studio projeleri normalde proje dosyasında belirtilen ToolsVersion ile oluşturmanıza karşın, kullanabileceğiniz `/ToolsVersion` (veya `/tv`) değeri geçersiz kılmak ve tüm projeleri ve bunların proje için proje oluşturmak için komut satırında geçiş farklı bir araç takımı bağımlılıklarla. Örneğin:  
  
```  
msbuild.exe someproj.proj /tv:12.0 /p:Configuration=Debug  
```  
  
 Bu örnekte, tüm projeleri ToolsVersion 12.0 kullanılarak oluşturulur. (Ancak, bu konunun devamındaki "Öncelik sırasını" bölümüne bakın.)  
  
 Kullanırken `/tv` komut satırında geçiş, isteğe bağlı olarak kullanabileceğiniz `$(ProjectToolsVersion)` bunları çözümdeki diğer projeler daha farklı bir ToolsVersion değerle oluşturmak için bireysel projelerine özellik.  
  
## <a name="override-the-toolsversion-settings-using-the-toolsversion-parameter-of-the-msbuild-task"></a>MSBuild Görevinin ToolsVersion Parametresini Kullanarak ToolsVersion Ayarlarını Geçersiz Kılma  
 MSBuild görevi başka bir yapı bir proje için birincil araçtır. Adlı bir isteğe bağlı görev parametre sağladığı projede belirtilen olandan farklı bir ToolsVersion sahip bir proje oluşturmak MSBuild görevini etkinleştirmek için `ToolsVersion`. Aşağıdaki örnek, bu parametre kullanımı gösterilmiştir:  
  
1.  Adlı bir dosya oluşturun `projectA.proj` ve aşağıdaki kodu içeren:  
  
    ```xml  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
    ToolsVersion="12.0">  
  
        <Target Name="go" >   
            <Message Text="projectA.proj" />  
            <Message Text="MSBuildToolsVersion: $(MSBuildToolsVersion)" />  
            <Message Text="MSBuildToolsPath:    $(MSBuildToolsPath)" />  
  
            <MSBuild Projects="projectB.proj"  
                ToolsVersion="2.0"  
                Targets="go" />  
        </Target>  
    </Project>  
    ```  
  
2.  Adlı başka bir dosya oluşturmak `projectB.proj` ve aşağıdaki kodu içeren:  
  
    ```xml  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
    ToolsVersion="12.0">  
  
        <Target Name="go">  
            <Message Text="projectB.proj" />  
            <Message Text="MSBuildToolsVersion: $(MSBuildToolsVersion)" />  
            <Message Text="MSBuildToolsPath:    $(MSBuildToolsPath)" />  
        </Target>  
    </Project>  
    ```  
  
3.  Bir komut isteminde aşağıdaki komutu girin:  
  
    ```  
    msbuild projectA.proj /t:go /toolsversion:3.5  
    ```  
  
4.  Şu çıktı görünür. İçin `projectA`, `/toolsversion:3.5` komut satırında ayarını geçersiz kılar `ToolsVersion=12.0` ayarı `Project` etiketi.  
  
     `ProjectB`bir görev tarafından çağrılan `projectA`. Bu göreve sahip `ToolsVersion=2.0`, hangi geçersiz kılar diğer `ToolsVersion` ayarlarını `projectB`.  
  
    ```  
    Output:  
      projectA.proj  
      MSBuildToolsVersion: 3.5  
      MSBuildToolsPath:    C:\Windows\Microsoft.NET\Framework\v3.5  
  
      projectB.proj  
      MSBuildToolsVersion: 2.0  
      MSBuildToolsPath:    C:\Windows\Microsoft.NET\Framework\v2.0.50727  
    ```  
  
## <a name="order-of-precedence"></a>Öncelik Sırası  
 Yüksekten en düşüğe öncelik sırasını belirlemek için kullanılan `ToolsVersion` değil:  
  
1.  `ToolsVersion` Varsa proje oluşturmak için kullanılan MSBuild görevi özniteliği.  
  
2.  `/toolsversion` (Veya `/tv`) varsa msbuild.exe komutta kullanılan anahtar.  
  
3.  Varsa ortam değişkeni `MSBUILDTREATALLTOOLSVERSIONSASCURRENT` ayarlanır ve ardından geçerli kullanmak `ToolsVersion`.  
  
4.  Varsa ortam değişkeni `MSBUILDTREATHIGHERTOOLSVERSIONASCURRENT` ayarlanır ve `ToolsVersion` tanımlanan dosya geçerli projede büyük `ToolsVersion`, geçerli kullanmak `ToolsVersion`.  
  
5.  Varsa ortam değişkeni `MSBUILDLEGACYDEFAULTTOOLSVERSION` ayarlanan veya `ToolsVersion` aşağıdaki adımları kullanılır, ayarlı değil:  
  
    1.  `ToolsVersion` Özniteliği [proje](../msbuild/project-element-msbuild.md) proje dosyası öğesidir. Bu öznitelik yoksa, geçerli sürümü olduğu varsayılır.  
  
    2.  Varsayılan Araçları sürüm MSBuild.exe.config dosyasında.  
  
    3.  Kayıt defterinde varsayılan Araçları sürüm. Daha fazla bilgi için bkz: [standart ve özel araç takımı yapılandırmaları](../msbuild/standard-and-custom-toolset-configurations.md).  
  
6.  Varsa ortam değişkeni `MSBUILDLEGACYDEFAULTTOOLSVERSION` aşağıdaki adımları kullanılır, ayarlı değil:  
  
    1.  Varsa ortam değişkeni `MSBUILDDEFAULTTOOLSVERSION` ayarlanmış bir `ToolsVersion` var, bunu kullanın.  
  
    2.  Varsa `DefaultOverrideToolsVersion` olan MSBuild.exe.config ayarlamak, bunu kullanın.  
  
    3.  Varsa `DefaultOverrideToolsVersion` olduğundan kayıt defterinde ayarlama, bunu kullanın.  
  
    4.  Aksi takdirde geçerli kullanın `ToolsVersion`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çoklu sürüm desteği](../msbuild/msbuild-multitargeting-overview.md)   
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [Araç Takımı (ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md)   
 [Standart ve özel araç takımı yapılandırmaları](../msbuild/standard-and-custom-toolset-configurations.md)