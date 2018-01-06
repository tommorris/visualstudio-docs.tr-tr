---
title: "GenerateBootstrapper görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#GenerateBootstrapper
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateBootstrapper task
- GenerateBootstrapper task [MSBuild]
ms.assetid: ca3ba2c6-d2ea-41f2-b7e3-0fc2b0730460
caps.latest.revision: "13"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 036f519529f0226c56b711096abc91e4ebf97d3a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="generatebootstrapper-task"></a>GenerateBootstrapper Görevi
Algılama, indirin ve bir uygulama ve ön yükleme için otomatik bir yol sağlar. Uygulama yapma tüm bileşenler için ayrı yükleyicileri tümleştiren tek bir yükleyici görür.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `GenerateBootstrapper` görev.  
  
-   `ApplicationFile`  
  
     İsteğe bağlı `String` parametresi.  
  
     Önyükleyici tüm önkoşulları yüklendikten sonra uygulama yüklemesini başlatmak için kullanacağı dosyayı belirtir. Bir derleme hatası ne sonuçlanır `BootstrapperItems` veya `ApplicationFile` parametresi.  
  
-   `ApplicationName`  
  
     İsteğe bağlı `String` parametresi.  
  
     Önyükleyici yükleyecek uygulamanın adını belirtir. Bu ad, yükleme sırasında önyükleyici kullanır kullanıcı arabiriminde görüntülenir.  
  
-   `ApplicationRequiresElevation`  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, hedef bilgisayarda yüklü olduğunda bileşen yükseltilmiş izinleriyle çalıştırılır.  
  
-   `ApplicationUrl`  
  
     İsteğe bağlı `String` parametresi.  
  
     Uygulamanın yükleyici barındırma Web konumunu belirtir.  
  
-   `BootstrapperComponentFiles`  
  
     İsteğe bağlı `String[]` çıkış parametresi.  
  
     Yerleşik önyükleyici paketi dosyalarının konumunu belirtir.  
  
-   `BootstrapperItems`  
  
     İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.  
  
     Önyükleyici oluşturmak için ürünleri belirtir. Bu parametreye geçirilen öğe aşağıdaki söz dizimini olmalıdır:  
  
    ```xml  
    <BootstrapperItem  
        Include="ProductCode">  
        <ProductName>  
            ProductName  
        </ProductName>  
    </BootstrapperItem>  
    ```  
  
     `Include` Özniteliği yüklü olması bir önkoşul adını temsil etmek için kullanılır. `ProductName` Öğe meta verisi isteğe bağlıdır ve yapı altyapısı tarafından kolay ad kullanılacak durumda paketi bulunamadı. Bu öğeler gerekli olmayan [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] sürece giriş parametreleri yok `ApplicationFile` belirtilir. Uygulamanız için yüklenmesi gereken her önkoşul için bir öğe içermesi gerekir.  
  
     Bir derleme hatası ne sonuçlanır `BootstrapperItems` veya `ApplicationFile` parametresi.  
  
-   `BootstrapperKeyFile`  
  
     İsteğe bağlı `String` çıkış parametresi.  
  
     Setup.exe yerleşik konumunu belirtir  
  
-   `ComponentsLocation`  
  
     İsteğe bağlı `String` parametresi.  
  
     Yüklemek yükleme önkoşulları aramak önyükleyici için bir konum belirtir. Bu parametre aşağıdaki değerlere sahip olabilir:  
  
    -   `HomeSite`: Önkoşul bileşeni satıcı tarafından barındırılan olduğunu gösterir.  
  
    -   `Relative`: Preqrequisite uygulama aynı konumda olduğunu gösterir.  
  
    -   `Absolute`: Tüm bileşenleri merkezi bir URL'de bulunan olduğunu gösterir. Bu değer ile birlikte kullanılmalıdır `ComponentsUrl` giriş parametresi.  
  
     Varsa `ComponentsLocation` belirtilmezse, `HomeSite` varsayılan olarak kullanılır.  
  
-   `ComponentsUrl`  
  
     İsteğe bağlı `String` parametresi.  
  
     Yükleme önkoşulları içeren URL'yi belirtir.  
  
-   `CopyComponents`  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, belirtilen yol için tüm çıktı dosyaları önyükleyici kopyalar `OutputPath` parametresi. Değerlerini `BootstrapperComponentFiles` parametresi tüm tabanlı bu yolda. Varsa `false`, dosyalar kopyalanmaz ve `BootstrapperComponentFiles` değerler değerine göre temel `Path` parametresi.  Bu parametrenin varsayılan değeri `true`.  
  
-   `Culture`  
  
     İsteğe bağlı `String` parametresi.  
  
     UI önyükleyici kullanılmak ve yükleme önkoşulları kültürü belirtir. Belirtilen kültür kullanılamıyor olması durumunda görev değerini kullanır `FallbackCulture` parametresi.  
  
-   `FallbackCulture`  
  
     İsteğe bağlı `String` parametresi.  
  
     UI bootstraper kullanılmak ve yükleme önkoşulları ikincil kültürü belirtir.  
  
-   `OutputPath`  
  
     İsteğe bağlı `String` parametresi.  
  
     Kopya Setup.exe'yi ve tüm paket dosyaları için konumu belirtir.  
  
-   `Path`  
  
     İsteğe bağlı `String` parametresi.  
  
     Tüm kullanılabilir önkoşul konumunu belirtir.  
  
-   `SupportUrl`  
  
     İsteğe bağlı `String` parametresi.  
  
     Önyükleyici yüklemenin başarısız olması sağlamak için URL'yi belirtir  
  
-   `Validate`  
  
     İsteğe bağlı `Boolean` parametresi.  
  
     Varsa `true`, önyükleyici belirtilen giriş önyükleyici öğeleri XSD doğrulaması gerçekleştirir. Bu parametrenin varsayılan değeri `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `GenerateBootstrapper` sahip olması gereken bir uygulamayı yüklemek için görev [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] bir önkoşul olarak yüklü.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <BootstrapperFile Include="Microsoft.Net.Framework.2.0">  
            <ProductName>Microsoft .NET Framework 2.0</ProductName>  
        </BootstrapperFile>  
    </ItemGroup>  
  
    <Target Name="BuildBootstrapper">  
        <GenerateBootstrapper  
            ApplicationFile="WindowsApplication1.application"  
            ApplicationName="WindowsApplication1"  
            ApplicationUrl="http://mycomputer"  
            BootstrapperItems="@(BootstrapperFile)"  
            OutputPath="C:\output" />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)