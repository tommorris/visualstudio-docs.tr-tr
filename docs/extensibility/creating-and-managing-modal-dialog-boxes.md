---
title: "Oluşturma ve kalıcı iletişim kutuları yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: dialog boxes, managing in Visual Studio
ms.assetid: 491bc0de-7dba-478c-a76b-923440e090f3
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 466f39ea7ea4b7d5b79901b2503622d2248bb7a8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-and-managing-modal-dialog-boxes"></a>Oluşturma ve yönetme kalıcı iletişim kutuları
Visual Studio içinde bir modal iletişim kutusu oluşturduğunuzda, iletişim kutusu görüntülendiği sırada iletişim kutusunun üst pencere devre dışı bırakıldığından emin olun sonra iletişim kutusunu kapattıktan sonra ana pencereyi yeniden etkinleştirmeniz gerekir. Bunu yaparsanız hata iletisini alabilirsiniz: "Microsoft Visual Studio kapatamaz kalıcı bir iletişim kutusu etkin olduğundan. Etkin iletişim kutusunu kapatın ve yeniden deneyin."  
  
 Bunu yapmanın iki yolu vardır. Bir WPF iletişim kutusu varsa önerilen, buradan türetebilir yoludur <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>ve ardından arama <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.ShowModal%2A> iletişim kutusunu görüntülemek için. Bunu yaparsanız üst pencere kalıcı durumunu yöneten gerekmez.  
  
 İletişim kutusu WPF değilse veya bazı diğer adınızı iletişim kutusundan türetilen olamaz neden sınıf <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>, iletişim kutusunun üst çağırarak almalısınız sonra <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.GetDialogOwnerHwnd%2A> ve kalıcı durumunu kendiniz çağırarak yönetme <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.EnableModeless%2A> yöntemi ile bir iletişim kutusunu görüntüleme ve iletişim kutusunu kapattıktan sonra yeniden parametresi 1 (true) olan bir yöntemini çağırmadan önce 0 (false) parametresi.  
  
## <a name="creating-a-dialog-box-derived-from-dialogwindow"></a>DialogWindow türetilmiş bir iletişim kutusu oluşturma  
  
1.  Adlı VSIX proje oluşturma **OpenDialogTest** ve adlı menü komutu ekleme **OpenDialog**. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Kullanılacak <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow> sınıfı, şu derlemeleri başvurular eklemeniz gerekir (Framework sekmesinde **Başvuru Ekle** iletişim kutusu):  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   System.Xaml  
  
3.  OpenDialog.cs içinde aşağıdaki ekleme `using` deyimi:  
  
    ```csharp  
    using Microsoft.VisualStudio.PlatformUI;  
    ```  
  
4.  Adlı bir sınıf bildirme **TestDialogWindow** , türetilen <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>:  
  
    ```csharp  
    class TestDialogWindow : DialogWindow  
    {. . .}  
    ```  
  
5.  En aza indirmek ve iletişim kutusunun en üst düzeye çıkarmak için ayarlanmış <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasMaximizeButton%2A> ve <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasMinimizeButton%2A> true:  
  
    ```csharp  
    internal TestDialogWindow()  
    {  
        this.HasMaximizeButton = true;  
        this.HasMinimizeButton = true;  
    }  
    ```  
  
6.  İçinde **OpenDialog.ShowMessageBox** yöntemi, var olan kodu şununla değiştirin:  
  
    ```csharp  
    TestDialogWindow testDialog = new TestDialogWindow();  
    testDialog.ShowModal();  
    ```  
  
7.  Derleme ve uygulamayı çalıştırın. Visual Studio'nun deneysel örneği görüntülenmesi gerekir. Üzerinde **Araçları** Deneysel örneğinin menü adlı bir komut görmelisiniz **çağırma OpenDialog**. Bu komutu tıklattığınızda iletişim penceresini görmeniz gerekir. Simge durumuna küçültüp penceresinin ekranı kaplamasını sağlayın yapabiliyor olmanız gerekir.  
  
## <a name="creating-and-managing-a-dialog-box-not-derived-from-dialogwindow"></a>Oluşturma ve yönetme DialogWindow türetilmemiş bir iletişim kutusu  
  
1.  Bu yordam için kullandığınız **OpenDialogTest** aynı derleme başvuruları olan önceki yordamda oluşturduğunuz çözümü.  
  
2.  Aşağıdakileri ekleyin `using` bildirimleri:  
  
    ```csharp  
    using System.Windows;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    ```  
  
3.  Adlı bir sınıf oluşturun **TestDialogWindow2** , türetilen <xref:System.Windows.Window>:  
  
    ```csharp  
    class TestDialogWindow2 : Window  
    {. . .}  
    ```  
  
4.  Özel bir başvuru ekleyin <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>:  
  
    ```  
    private IVsUIShell shell;  
    ```  
  
5.  Başvuru ayarlar için bir oluşturucu ekleyin <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>:  
  
    ```csharp  
    public TestDialogWindow2(IVsUIShell uiShell)  
    {  
        shell = uiShell;  
    }  
    ```  
  
6.  İçinde **OpenDialog.ShowMessageBox** yöntemi, var olan kodu şununla değiştirin:  
  
    ```csharp  
    IVsUIShell uiShell = (IVsUIShell)ServiceProvider.GetService(typeof(SVsUIShell));  
  
    TestDialogWindow2 testDialog2 = new TestDialogWindow2(uiShell);  
    //get the owner of this dialog  
    IntPtr hwnd;  
    uiShell.GetDialogOwnerHwnd(out hwnd);  
    testDialog2.WindowStartupLocation = System.Windows.WindowStartupLocation.CenterOwner;  
    uiShell.EnableModeless(0);  
    try  
    {  
        WindowHelper.ShowModal(testDialog2, hwnd);  
    }  
    finally  
    {  
        // This will take place after the window is closed.  
        uiShell.EnableModeless(1);  
    }  
    ```  
  
7.  Derleme ve uygulamayı çalıştırın. Üzerinde **Araçları** menü adlı bir komut görmelisiniz **çağırma OpenDialog**. Bu komutu tıklattığınızda iletişim penceresini görmeniz gerekir.