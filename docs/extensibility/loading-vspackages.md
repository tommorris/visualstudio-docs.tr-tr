---
title: "VSPackages yükleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, loading
ms.assetid: f4c3dcea-5051-4065-898f-601269649d92
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 94db8d3bb95e254a3fa528a424048162916fce99
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="loading-vspackages"></a>VSPackages yükleniyor
Yalnızca işlevleri gerekli olduğunda VSPackages Visual Studio'ya yüklenir. Örneğin, Visual Studio Proje Fabrika veya VSPackage uygulayan bir hizmeti kullanan bir VSPackage yüklenir. Bu özellik, mümkün olduğunda performansını artırmak kullanılan Gecikmeli yükleme adı verilir.  
  
> [!NOTE]
>  Visual Studio VSPackage yüklemeden bir VSPackage sunar komutları gibi belirli VSPackage bilgileri belirleyebilirsiniz.  
  
 Bir çözüm açık olduğunda VSPackages belirli kullanıcı arabirimi (UI) bağlamında autoload için örneğin, ayarlanabilir. <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> Özniteliği bu bağlamda ayarlar.  
  
### <a name="autoloading-a-vspackage-in-a-specific-context"></a>Belirli bir bağlamda VSPackage Autoloading  
  
-   Ekleme `ProvideAutoLoad` özniteliği VSPackage öznitelikleri:  
  
    ```csharp  
    [DefaultRegistryRoot(@"Software\Microsoft\VisualStudio\14.0")]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    [Guid("00000000-0000-0000-0000-000000000000")] // your specific package GUID  
    public class MyAutoloadedPackage : Package  
    {. . .}  
    ```  
  
     Numaralandırılmış alanlarını bkz <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> UI bağlamları ve GUID değerlerinin listesi.  
  
-   Bir kesme noktası kümesinde <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yöntemi.  
  
-   VSPackage derleyin ve hata ayıklamayı Başlat.  
  
-   Bir çözüm yükleyin veya oluşturun.  
  
     VSPackage yükler ve kesme noktasında durur.  
  
## <a name="forcing-a-vspackage-to-load"></a>Yüklemek için bir VSPackage zorlama  
 Bazı durumlarda bir VSPackage yüklenmesi için başka bir VSPackage zorlamanız gerekebilir. Örneğin, bir basit VSPackage büyük VSPackage CMDUIContext kullanılabilir olmayan bağlamda yük.  
  
 Kullanabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackage%2A> yüklemek için bir VSPackage zorlamak için yöntem.  
  
-   Bu kod içine ekleme <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yüklemek için başka bir VSPackage zorlar VSPackage yöntemi:  
  
    ```csharp  
    IVsShell shell = GetService(typeof(SVsShell)) as IVsShell;  
    if (shell == null) return;  
  
    IVsPackage package = null;  
    Guid PackageToBeLoadedGuid =   
        new Guid(Microsoft.PackageToBeLoaded.GuidList.guidPackageToBeLoadedPkgString);  
    shell.LoadPackage(ref PackageToBeLoadedGuid, out package);  
  
    ```  
  
     VSPackage başlatıldığında zorla `PackageToBeLoaded` yüklenemiyor.  
  
     Zorla yüklenmesini VSPackage iletişimi için kullanılmaması gerekir. Kullanım [kullanma ve servisleri](../extensibility/using-and-providing-services.md) yerine.  
  
## <a name="using-a-custom-attribute-to-register-a-vspackage"></a>Bir VSPackage kaydolmak için özel bir öznitelik kullanma  
 Belirli durumlarda Uzantınız için yeni bir kayıt öznitelik oluşturmanız gerekebilir. Kayıt öznitelikleri yeni kayıt defteri anahtarlarını eklemek veya mevcut anahtarlarına yeni değerler eklemek için kullanabilirsiniz. Yeni öznitelik öğesinden türetilmelidir <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>, ve geçersiz kılmanız gerekir <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> ve <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> yöntemleri.  
  
## <a name="creating-a-registry-key"></a>Bir kayıt defteri anahtarı oluşturma  
 Aşağıdaki kodda özel öznitelik oluşturur bir **özel** kaydedilmekte olan VSPackage anahtarı altında alt anahtar.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + @"}\Custom");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
    }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveKey(@"Packages\" + context.ComponentType.GUID + @"}\Custom");  
}  
  
```  
  
## <a name="creating-a-new-value-under-an-existing-registry-key"></a>Varolan bir kayıt defteri anahtarı altında yeni bir değer oluşturma  
 Mevcut bir anahtarı için özel değerler ekleyebilirsiniz. Aşağıdaki kod bir VSPackage kayıt anahtarı için yeni bir değer ekleme gösterir.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + "}");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
                }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveValue(@"Packages\" + context.ComponentType.GUID, "NewCustom");  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackages](../extensibility/internals/vspackages.md)