---
title: "Bir uzantısı ile VSPackage oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0cc5e08-4897-44f2-8309-e3478f1f999e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: df971bdf72ff52cfa6343b6237de072238087ac4
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="creating-an-extension-with-a-vspackage"></a>Uzantı VSPackage ile oluşturma
Bu kılavuzda VSIX proje oluşturma ve bir VSPackage proje öğesi ekleme gösterilmektedir. Bir ileti kutusu göstermek için kullanıcı Arabirimi Kabuk hizmeti almak için VSPackage kullanacağız.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-vspackage"></a>Bir VSPackage oluşturma  
  
1.  Adlı VSIX proje oluşturma **FirstPackage**. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C# / genişletilebilirlik**.  
  
2.  Proje açıldığında adlı bir Visual Studio Paketi öğesi şablonu Ekle **FirstPackage**. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# / genişletilebilirlik** seçip **Visual Studio Paketi**. İçinde **adı** alan penceresinin alt kısmında, komut dosyası adı Değiştir **FirstPackage.cs**.  
  
3.  Projeyi derleyin ve hata ayıklamayı Başlat.  
  
     Visual Studio'nun deneysel örneği görüntülenir. Deneysel örneği hakkında daha fazla bilgi için bkz: [deneysel örneği](../extensibility/the-experimental-instance.md).  
  
4.  Deneysel örneğinde açmak **Araçlar / Uzantılar ve güncelleştirmeler** penceresi. Görmeniz gerekir **FirstPackage** burada uzantı. (Açarsanız **Uzantılar ve güncelleştirmeler** Visual Studio, çalışma örneğinde, görmezsiniz **FirstPackage**).  
  
## <a name="loading-the-vspackage"></a>VSPackage yükleniyor  
 Olduğundan yüklemek neden hiçbir şey bu noktada uzantısı, yüklemez. (Bir araç penceresi açma menü komutu,'ı tıklatarak), kullanıcı Arabirimi ile veya belirli bir kullanıcı Arabirimi bağlamında VSPackage yükleyeceğini belirterek etkileşim kurarken, genellikle bir uzantı yükleyebilirsiniz. VSPackages ve kullanıcı Arabirimi bağlamları yükleme hakkında daha fazla bilgi için bkz: [yüklenirken VSPackages](../extensibility/loading-vspackages.md). Bu yordam için bir çözüm açık olduğunda bir VSPackage yükleme göstereceğiz.  
  
1.  FirstPackage.cs dosyasını açın. FirstPackage sınıfının bildirimini arayın. Varolan öznitelikleri şununla değiştirin:  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    [Guid(FirstPackage.PackageGuidString)]  
    public sealed class FirstPackage : Package  
    ```  
  
2.  Bize VSPackage yükledi bilmeniz olanak sağlayan bir ileti ekleyelim. VSPackage bir yalnızca tarihli sonra Visual Studio Hizmetleri elde edebilirsiniz çünkü VSPackage'nın önce Initialize() yöntemini Bunu yapmak için kullanırız. (Hizmetleri alma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir hizmet elde](../extensibility/how-to-get-a-service.md).) FirstPackage önce Initialize() yöntemini alır kod ile değiştirin <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> hizmet, alır <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> arabirimi ve çağrıları kendi <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowMessageBox%2A> yöntemi.  
  
    ```csharp  
    protected override void Initialize()  
    {  
        base.Initialize();  
  
        IVsUIShell uiShell = (IVsUIShell)GetService(typeof(SVsUIShell));  
        Guid clsid = Guid.Empty;  
        int result;  
        Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(uiShell.ShowMessageBox(  
            0,  
            ref clsid,  
            "FirstPackage",  
             string.Format(CultureInfo.CurrentCulture, "Inside {0}.Initialize()", this.GetType().FullName),  
            string.Empty,  
            0,  
            OLEMSGBUTTON.OLEMSGBUTTON_OK,  
            OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST,  
            OLEMSGICON.OLEMSGICON_INFO,  
            0,  
            out result));  
    }  
    ```  
  
3.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir.  
  
4.  Bir çözüm deneysel örneğinde açın. Bildiren bir ileti kutusu görmeniz gerekir **içinde ilk paket Initialize()**.