---
title: VSPackages yükleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, loading
ms.assetid: f4c3dcea-5051-4065-898f-601269649d92
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 008cd31bc3d9f909477089e608393f596bfb0682
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackage’lar](../extensibility/internals/vspackages.md)
