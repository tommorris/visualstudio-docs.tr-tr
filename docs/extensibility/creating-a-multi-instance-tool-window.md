---
title: "Çok örnekli araç penceresi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multi
- tool windows
ms.assetid: 4a7872f1-acc9-4f43-8932-5a526b36adea
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a4dd74bc1a59d93e2eef9c7dc00d8b83d53628a8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-multi-instance-tool-window"></a>Çok örnekli araç penceresi oluşturma
Birden çok örneği aynı anda açık olması için bir araç penceresi programlama yapabilirsiniz. Varsayılan olarak, aracı windows açmak yalnızca bir örneği olabilir.  
  
 Çok örnekli araç penceresi kullandığınızda, bilgi aynı anda birden fazla ilgili kaynakları gösterebilir. Örneğin, çok satırlı koyabilirsiniz <xref:System.Windows.Forms.TextBox> birkaç kod parçacıkları programlama oturumu sırasında aynı anda kullanılabilir olacak şekilde, birden çok örneği araç penceresinde denetim. Ayrıca örneğin koyabilirsiniz bir <xref:System.Windows.Forms.DataGrid> denetimi ve aşağı açılan liste kutusunu çok örnekli araç penceresinde birkaç gerçek zamanlı veri kaynakları aynı anda izlenebilir şekilde.  
  
## <a name="creating-a-basic-single-instance-tool-window"></a>Temel (tekli) araç penceresi oluşturma  
  
1.  Adlı bir proje oluşturun **MultiInstanceToolWindow** VSIX şablonu kullanarak ve adlandırılmış bir özel araç pencere öğesi şablonu Ekle **MIToolWindow**.  
  
    > [!NOTE]
    >  Bir araç penceresi uzantı oluşturma hakkında daha fazla bilgi için bkz: [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="making-a-tool-window-multi-instance"></a>Araç penceresi çok örnekli yapma  
  
1.  Açık **MIToolWindowPackage.cs** dosya ve Bul `ProvideToolWindow` özniteliği. ve `MultiInstances=true` aşağıdaki örnekte gösterildiği gibi parametre.  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
        [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
        [ProvideMenuResource("Menus.ctmenu", 1)]  
        [ProvideToolWindow(typeof(MultiInstanceToolWindow.MIToolWindow), MultiInstances = true)]  
        [Guid(MIToolWindowPackageGuids.PackageGuidString)]  
        public sealed class MIToolWindowPackage : Package  
    {. . .}  
    ```  
  
2.  MIToolWindowCommand.cs dosyasında ShowToolWindos() yöntemini bulun. Bu yöntemi çağırın <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> yöntemi ve kümesi kendi `create` bayrağını `false` mevcut araç penceresi örnekleri kullanılabilir bir kadar yineleme böylece `id` bulunur.  
  
3.  Bir araç penceresi örneği oluşturmak için arama <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> yöntemi ve kümesi kendi `id` kullanılabilir değerine ve kendi `create` bayrağını `true`.  
  
     Varsayılan olarak, değeri `id` parametresinin <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> yöntemi `0`. Bu, tek örnek araç penceresi hale getirir. Barındırılması birden fazla örnek için her örneğinin kendi benzersiz olmalıdır `id`.  
  
4.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> yöntemi <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> tarafından döndürülen nesne <xref:Microsoft.VisualStudio.Shell.ToolWindowPane.Frame%2A> araç penceresi örneğinin özelliği.  
  
5.  Varsayılan olarak, `ShowToolWindow` aracı pencere öğesi şablonu tarafından oluşturulan yöntemi, tek örnek araç penceresi oluşturur. Aşağıdaki örnekte nasıl değiştirileceğini gösterir `ShowToolWindow` birden çok örneği oluşturmak için yöntemi.  
  
    ```csharp  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        for (int i = 0; i < 10; i++)  
        {  
            ToolWindowPane window = this.package.FindToolWindow(typeof(MIToolWindow), i, false);  
            if (window == null)  
            {  
                // Create the window with the first free ID.   
                window = (ToolWindowPane)this.package.FindToolWindow(typeof(MIToolWindow), i, true);  
                if ((null == window) || (null == window.Frame))  
                {  
                    throw new NotSupportedException("Cannot create tool window");  
                }  
  
            IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
            Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
            break;  
            }  
        }  
    }  
    ```