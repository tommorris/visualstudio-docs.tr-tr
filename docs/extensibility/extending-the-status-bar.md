---
title: "Durum çubuğu genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- status bars, about status bars
- status bars, overview
ms.assetid: f955115c-4c5f-45ec-b41b-365868c5ec0c
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e170edf941455dd21727628c2e07a836db919d0e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-the-status-bar"></a>Durum çubuğu genişletme
IDE alt kısmındaki Visual Studio durum çubuğu bilgilerini görüntülemek için kullanabilirsiniz.  
  
 Durum çubuğu genişlettiğinizde, bilgi ve kullanıcı Arabirimi dört bölgelerde görüntüleyebilirsiniz: geri bildirim bölgeye, ilerleme çubuğu, animasyon bölgeye ve tasarımcı bölgesi. Geri bildirim bölge metni görüntülemek ve görüntülenen metni vurgulama izin verir. İlerleme çubuğu dosya kaydetme gibi kısa süreli işlemleri için artımlı ilerleme durumunu gösterir. Animasyon bölge sürekli döngüye animasyon uzun süre çalışan işlemleri veya işlem bir çözümde birden çok proje derleme gibi belirlenmemiş uzunluğu görüntüler. Ve tasarımcı bölge imleç konumu satır ve sütun sayısını gösterir.  
  
 Durum çubuğunu kullanarak alabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> arabirimi (gelen <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> hizmeti). Ayrıca, bir pencere çerçevesi tarihli herhangi bir nesne bir durum çubuğu istemci nesnesi olarak uygulayarak kaydedebilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> arabirimi. Her bir pencere etkinleştirildiğinde, Visual Studio için bu pencere tarihli nesneyi sorgular `IVsStatusbarUser` arabirimi. Bulursa, onu çağrılarını <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> döndürüldü arabirim ve nesne üzerinde yöntemi, bu yöntem içinde durum çubuğundan güncelleştirebilirsiniz. Belge pencereleri, örneğin, kullanabilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> yöntemi etkin olduklarında Tasarımcı bölge bilgileri güncelleştirin.  
  
 Aşağıdaki yordamlar VSIX proje oluşturma ve özel menü komutu eklemek nasıl anladığınızı varsayar. Bilgi için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
## <a name="modifying-the-status-bar"></a>Durum çubuğu değiştirme  
 Bu yordamda ayarlamak ve metni almak, statik metin görüntülemek ve durum çubuğunun geri bildirim bölgede görüntülenen metni vurgulama gösterilmiştir.  
  
#### <a name="reading-and-writing-to-the-status-bar"></a>Okuma ve yazma durum çubuğu  
  
1.  Adlı VSIX proje oluşturma **TestStatusBarExtension** ve adlı menü komutu ekleme **TestStatusBarCommand**.  
  
2.  TestStatusBarCommand.cs içinde komut işleyici yöntemi kodu (MenuItemCallback) aşağıdakiyle değiştirin:  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar = (IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
  
        // Make sure the status bar is not frozen  
        int frozen;  
  
        statusBar.IsFrozen(out frozen);  
  
        if (frozen != 0)   
        {  
            statusBar.FreezeOutput(0);  
        }  
  
        // Set the status bar text and make its display static.  
        statusBar.SetText("We just wrote to the status bar.");  
  
        // Freeze the status bar.  
        statusBar.FreezeOutput(1);  
  
        // Get the status bar text.   
        string text;  
        statusBar.GetText(out text);  
        System.Windows.Forms.MessageBox.Show(text);  
  
        // Clear the status bar text.  
        statusBar.FreezeOutput(0);  
        statusBar.Clear();  
    }  
    ```  
  
3.  Kodu derlemek ve hata ayıklamayı Başlat.  
  
4.  Açık **Araçları** Visual Studio'nun deneysel örneği menüde. Tıklatın **çağırma TestStatusBarCommand** düğmesi.  
  
     Görmelisiniz durum çubuğu şimdi okuma metinde **"Yalnızca durum çubuğu yazdığımız."** ve aynı metin görünür ileti kutusu vardır.  
  
#### <a name="updating-the-progress-bar"></a>İlerleme çubuğu güncelleştiriliyor  
  
1.  Bu yordamda başlatmak ve ilerleme çubuğu güncelleştirmek nasıl göstereceğiz.  
  
2.  TestStatusBarCommand.cs dosyasını açın ve MenuItemCallback yöntemini aşağıdaki kodla değiştirin:  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar = (IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
        uint cookie = 0;  
        string label = "Writing to the progress bar";  
  
        // Initialize the progress bar.  
        statusBar.Progress(ref cookie, 1, "", 0, 0);  
  
        for (uint i = 0, total = 20; i <= total; i++)  
        {  
            // Display progress every second.  
            statusBar.Progress(ref cookie, 1, label, i, total);  
            System.Threading.Thread.Sleep(1000);  
        }  
  
        // Clear the progress bar.  
        statusBar.Progress(ref cookie, 0, "", 0, 0);  
    }  
    ```  
  
3.  Kodu derlemek ve hata ayıklamayı Başlat.  
  
4.  Açık **Araçları** Visual Studio'nun deneysel örneği menüde. Tıklatın **çağırma TestStatusBarCommand** düğmesi.  
  
     Görmelisiniz durum çubuğu şimdi okuma metinde **"ilerleme çubuğu yazılıyor."** Ayrıca, saniyede 20 saniye güncelleştirilmesi ilerleme çubuğu görürsünüz. Bundan sonra durum çubuğu ve ilerleme çubuğu temizlenir.  
  
#### <a name="displaying-an-animation"></a>Bir animasyon görüntüleme  
  
1.  Durum çubuğunu gösterir ya da bir döngü animasyon uzun süre çalışan işlemi (örneğin, bir çözümde birden çok proje derleme) görüntüler. Bu animasyon görmüyorsanız, doğru olduğundan emin olun **Araçlar / Seçenekler** ayarları:  
  
     Git **Araçlar/Seçenekler / genel** sekmesinde ve işaretini **istemci performansı görsel deneyimi otomatik olarak ayarla**. Alt seçeneği denetleyin **etkinleştirmek zengin istemci görsel deneyimi**. Şimdi Deneysel Visual Studio örneğiniz projesinde derlerken animasyonun görüyor olmalısınız.  
  
     Bu yordamda, bir proje ya da çözüm oluşturma temsil eden standart Visual Studio animasyon görüntüler.  
  
2.  TestStatusBarCommand.cs dosyasını açın ve MenuItemCallback yöntemini aşağıdaki kodla değiştirin:  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar =(IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
  
        // Use the standard Visual Studio icon for building.  
        object icon = (short)Microsoft.VisualStudio.Shell.Interop.Constants.SBAI_Build;  
  
        // Display the icon in the Animation region.  
        statusBar.Animation(1, ref icon);  
  
        // The message box pauses execution for you to look at the animation.  
        System.Windows.Forms.MessageBox.Show("showing?");  
  
        // Stop the animation.   
        statusBar.Animation(0, ref icon);  
    }  
    ```  
  
3.  Kodu derlemek ve hata ayıklamayı Başlat.  
  
4.  Açık **Araçları** tıklayın ve Visual Studio deneysel örneği menüde **çağırma TestStatusBarCommand**.  
  
     İleti kutusu gördüğünüzde, ayrıca durum çubuğundaki animasyon sağ ucundaki görmeniz gerekir. İleti kutusu yok sayın, animasyonun kaybolur.