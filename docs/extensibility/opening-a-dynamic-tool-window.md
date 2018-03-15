---
title: "Dinamik aracı penceresini açma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tool windows, dynamic
ms.assetid: 21547ba7-6e81-44df-9277-265bf34f877a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 197bda3f825d0e709c1bc9ae08d8f0018b8b07c5
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="opening-a-dynamic-tool-window"></a>Dinamik aracı penceresini açma
Araç pencereleri genellikle bir menü veya eşdeğer bir kısayol komutundan açılır. Bazen, Bununla birlikte, belirli bir kullanıcı Arabirimi bağlam uygular ve UI bağlamı Artık uygulanmadığında kapatır zaman açıldığını bir araç penceresi gerekebilir. Bu tür araç pencereleri adlı *dinamik* veya *otomatik görünür*.  
  
> [!NOTE]
>  Önceden tanımlanmış UI bağlamları listesi için bkz: <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT>. İçin  
  
 Başlangıçta dinamik araç penceresi açmak istediğiniz ve oluşturma başarısız mümkündür, uygulamanız gereken <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx> arabirim ve hata koşulları test <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx.QueryShowTool%2A> yöntemi. Başlangıçta açılmalıdır dinamik araç penceresi sahip olduğunuzu bilmeniz Kabuğu sırayla eklemelisiniz `SupportsDynamicToolOwner` paket kaydınızı değere (1 olarak ayarlayın). Bu değer, standart bir parçası değil <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>, bunu eklemek için özel bir öznitelik oluşturmanız gerekir. Özel öznitelikler hakkında daha fazla bilgi için bkz: [uzantı kaydetmek için özel bir kayıt özniteliği kullanılarak](../extensibility/registering-and-unregistering-vspackages.md#using-a-custom-registration-attribute-to-register-an-extension).  
  
 Kullanım <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> araç penceresi açın. Araç penceresi gerektiğinde oluşturulur.  
  
> [!NOTE]
>  Kullanıcı tarafından dinamik araç penceresi kapatılabilir. Kullanıcı araç penceresi yeniden açabilirsiniz şekilde menü komutu oluşturmak istiyorsanız, menü komutu araç penceresi ve aksi durumda devre dışı açar UI bağlamda etkinleştirilmiş olmalıdır.  
  
### <a name="to-open-a-dynamic-tool-window"></a>Dinamik aracı penceresini açmak için  
  
1.  Adlı VSIX proje oluşturma **DynamicToolWindow** ve adlı bir aracı pencere öğesi şablonu Ekle **DynamicWindowPane.cs**. Daha fazla bilgi için bkz: [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
2.  DynamicWindowPanePackage.cs dosyasında DynamicWindowPanePackage bildirimi bulun. Ekleme <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> ve <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute> araç penceresi kaydetmek için öznitelikler.  
  
    ```vb  
    [ProvideToolWindow(typeof(DynamicWindowPane)]  
    [ProvideToolWindowVisibility(typeof(DynamicWindowPane), VSConstants.UICONTEXT.SolutionExists_string)]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [ProvideToolWindow(typeof(DynamicToolWindow.DynamicWindowPane))]  
    [Guid(DynamicWindowPanePackage.PackageGuidString)]  
    public sealed class DynamicWindowPanePackage : Package  
    {. . .}  
    ```  
  
     Yukarıdaki öznitelikleri Visual Studio açılamaz ve kapandığında, kalıcı yapılmaz, geçici bir pencere olarak DynamicWindowPane adlı araç penceresi kaydedin. DynamicWindowPane açıldığında her <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExists_string> uygular ve aksi durumda kapalı.  
  
3.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenmesi gerekir. Araç penceresi görmemeniz gerekir.  
  
4.  Deneysel örneğinde bir projeyi açın. Araç penceresi görüntülenmesi gerekir.