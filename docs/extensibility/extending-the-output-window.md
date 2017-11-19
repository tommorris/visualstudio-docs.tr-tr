---
title: "Çıktı penceresi genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Output window, about Output window
ms.assetid: b02fa88c-f92a-4ff6-ba5f-2eb4d48a643a
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8e183413446bbca2ffed0642619ab63538fae0f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-the-output-window"></a>Çıktı penceresi genişletme
**Çıkış** penceresi okuma/yazma metin bölmeleri kümesidir. Visual Studio olan bu yerleşik bölmeler: **yapı**, hangi projelerinde iletileri derlemeleri hakkında iletişim kurmak ve **genel**, burada [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] iletileri IDE hakkında iletişim kurar. Projeleri almak için bir başvuru **yapı** bölmesinde otomatik olarak ile <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg> arabirim yöntemleri ve Visual Studio sunar doğrudan erişim **genel** bölmesi aracılığıyla <xref:Microsoft.VisualStudio.Shell.Interop.SVsGeneralOutputWindowPane> hizmet. Yerleşik bölmeler yanı sıra, oluşturabilir ve kendi özel bölmeleri yönetebilirsiniz.  
  
 Kontrol edebilirsiniz **çıkış** penceresi doğrudan ile <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane> arabirimleri. <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> Tarafından sunulan arabirimi <xref:Microsoft.VisualStudio.Shell.Interop.SVsOutputWindow> hizmet, oluşturulmasını, alınmasını ve yok etme yöntemlerini tanımlar **çıkış** pencere bölmeleri. <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> Arabirimi bölmelerini gösterme, bölmelerini gizleme ve bunların metin düzenleme için yöntemleri tanımlar. Denetlemeye yönelik alternatif bir yol **çıkış** penceredir aracılığıyla <xref:EnvDTE.OutputWindow> ve <xref:EnvDTE.OutputWindowPane> Visual Studio Otomasyon nesne modelinde. Bu nesneler neredeyse tüm işlevselliğini kapsülleyen <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane> arabirimleri. Ayrıca, <xref:EnvDTE.OutputWindow> ve <xref:EnvDTE.OutputWindowPane> nesneleri listeleme kolaylaştırmak için üst düzey bazı işlevler eklemek **çıkış** pencere bölmeleri ve bölmeleri metni almak için.  
  
## <a name="creating-an-extension-that-uses-the-output-pane"></a>Çıkış bölmesini kullanan bir uzantısı oluşturma  
 Çıkış bölmesinde farklı yönlerini uygular bir uzantı yapabilirsiniz.  
  
1.  Adlı VSIX proje oluşturma `TestOutput` menü komutu ile adlı **TestOutput**. Daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Aşağıdaki başvurular ekleyin:  
  
    1.  EnvDTE  
  
    2.  EnvDTE80  
  
3.  TestOutput.cs içinde aşağıdaki ekleme deyimini kullanarak:  
  
    ```f#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  TestOutput.cs içinde ShowMessageBox yöntemi silin. Aşağıdaki yöntem saplama ekleyin:  
  
    ```csharp  
    private void OutputCommandHandler(object sender, EventArgs e)  
    {  
    }  
    ```  
  
5.  TestOutput oluşturucuda komut işleyici için OutputCommandHandler değiştirin. Komutları ekler bölümü aşağıda verilmiştir:  
  
    ```csharp  
    OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
    if (commandService != null)  
    {  
        CommandID menuCommandID = new CommandID(MenuGroup, CommandId);  
        EventHandler eventHandler = OutputCommandHandler;  
        MenuCommand menuItem = new MenuCommand(eventHandler, menuCommandID);  
        commandService.AddCommand(menuItem);  
    }  
    ```  
  
6.  Aşağıdaki bölümler çıkış bölmesi postalarla farklı yolu gösterilmektedir farklı yöntemler vardır. Bu yöntemlere OutputCommandHandler() yönteminin gövdesi çağırabilirsiniz. Örneğin, aşağıdaki kod, sonraki bölümde verilen CreatePane() yöntemi ekler.  
  
    ```csharp  
    private void OutputCommandHandler(object sender, EventArgs e)  
    {  
        CreatePane(new Guid(), "Created Pane", true, false);  
    }  
    ```  
  
## <a name="creating-an-output-window-with-ivsoutputwindow"></a>Çıktı penceresi IVsOutputWindow ile oluşturma  
 Bu örnekte yeni bir oluşturulacağını gösterir **çıkış** kullanarak pencere bölmesine <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow> arabirimi.  
  
```csharp  
void CreatePane(Guid paneGuid, string title,   
    bool visible, bool clearWithSolution)  
{  
    IVsOutputWindow output =   
        (IVsOutputWindow)GetService(typeof(SVsOutputWindow));  
    IVsOutputWindowPane pane;  
  
    // Create a new pane.  
    output.CreatePane(  
        ref paneGuid,   
        title,   
        Convert.ToInt32(visible),   
        Convert.ToInt32(clearWithSolution));  
  
    // Retrieve the new pane.  
    output.GetPane(ref paneGuid, out pane);  
  
     pane.OutputString("This is the Created Pane \n");  
}  
```  
  
 Bu yöntem tıkladığınızda önceki bölümde verilen uzantısı eklerseniz **çağırma TestOutput** görmelisiniz komut **çıkış** bildiren bir üstbilgiyle penceresi **Göster çıktı gelen: CreatedPane** ve sözcükleri **bu oluşturulan bölmesidir** bölmesinde.  
  
## <a name="creating-an-output-window-with-outputwindow"></a>Çıktı penceresi OutputWindow ile oluşturma  
 Bu örnek nasıl oluşturulacağını gösterir bir **çıkış** kullanarak pencere bölmesine <xref:EnvDTE.OutputWindow> nesnesi.  
  
```csharp  
void CreatePane(string title)  
{  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    OutputWindowPanes panes =  
        dte.ToolWindows.OutputWindow.OutputWindowPanes;  
  
    try  
    {  
        // If the pane exists already, write to it.  
        panes.Item(title);  
    }  
    catch (ArgumentException)  
    {  
        // Create a new pane and write to it.  
        return panes.Add(title);  
    }  
}  
```  
  
 Ancak <xref:EnvDTE.OutputWindowPanes> koleksiyonu almak olanak tanır bir **çıkış** pencere bölmesine başlığını tarafından bölmesinde başlıkları garanti edilmez benzersiz olmalıdır. Başlık benzersizliğini doubt kullanırsanız <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow.GetPane%2A> doğru bölmesi GUID'sine tarafından alma yöntemi.  
  
 Bu yöntem tıkladığınızda önceki bölümde verilen uzantısı eklerseniz **çağırma TestOutput** bildiren bir üstbilgiyle çıktı penceresi gördüğünüz komutu **Göster çıktı: DTEPane** ve sözcükleri **eklenen DTE bölmesinde** bölmesinde.  
  
## <a name="deleting-an-output-window"></a>Çıktı penceresi silme  
 Bu örnek nasıl silineceğini gösterir bir **çıkış** bölme.  
  
```csharp  
void DeletePane(Guid paneGuid)  
{  
    IVsOutputWindow output =  
    (IVsOutputWindow)ServiceProvider.GetService(typeof(SVsOutputWindow));  
  
    IVsOutputWindowPane pane;  
    output.GetPane(ref paneGuid, out pane);  
  
    if (pane == null)  
    {  
        CreatePane(paneGuid, "New Pane\n", true, true);  
    }  
     else  
    {  
        output.DeletePane(ref paneGuid);  
    }  
}  
```  
  
 Bu yöntem tıkladığınızda önceki bölümde verilen uzantısı eklerseniz **çağırma TestOutput** bildiren bir üstbilgiyle çıktı penceresi gördüğünüz komutu **Göster çıktı: yeni bölmesi** ve sözcükleri **oluşturulan bölmesinde eklenen** bölmesinde. Tıklatırsanız **çağırma TestOutput** komutunu yeniden, bölmesinde silinir.  
  
## <a name="getting-the-general-pane-of-the-output-window"></a>Çıktı penceresi genel bölmesinin Başlarken  
 Bu örnek, yerleşik alınacağı gösterilmektedir **genel** bölmesinde **çıkış** penceresi.  
  
```csharp  
void GetGeneralPane()  
{  
    return (IVsOutputWindowPane)GetService(  
        typeof(SVsGeneralOutputWindowPane));  
}  
```  
  
 Bu yöntem tıkladığınızda önceki bölümde verilen uzantısı eklerseniz, **çağırma TestOutput** görmeniz gerekir, komut **çıkış** penceresi gösterir sözcükleri **bulunan genel bölmesinde** bölmesinde.  
  
## <a name="getting-the-build-pane-of-the-output-window"></a>Çıktı penceresi yapı bölmesinin Başlarken  
 Bu örnek, Yapı bölmesinde bulmak ve yazma gösterilmektedir. Yapı bölmesinde varsayılan olarak etkinleştirilmez olduğundan, bu da etkinleştirir.  
  
```csharp  
void OutputTaskItemStringExExample(string buildMessage)  
{  
    EnvDTE80.DTE2 dte = (EnvDTE80.DTE2)ServiceProvider.GetService(typeof(EnvDTE.DTE));  
  
    EnvDTE.OutputWindowPanes panes =  
        dte.ToolWindows.OutputWindow.OutputWindowPanes;  
    foreach (EnvDTE.OutputWindowPane pane in panes)  
        {  
            if (pane.Name.Contains("Build"))  
            {  
                pane.OutputString(buildMessage + "\n");  
                pane.Activate();  
                return;  
             }  
        }  
}  
```