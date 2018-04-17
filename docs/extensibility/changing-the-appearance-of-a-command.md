---
title: Bir komut görünümünü değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, changing appearance
- menu commands, changing appearance
- menus, changing command appearance
ms.assetid: da2474fa-f92d-4e9e-b8bf-67c61bf249c2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4a19793f16991bc61636a929822757823728a926
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="changing-the-appearance-of-a-command"></a>Bir komut görünümünü değiştirme
Komutunun görünümünü değiştirerek, kullanıcı geri bildirim sağlayabilirsiniz. Örneğin, kullanılamaz duruma geldiğinde farklı aramak için bir komut isteyebilirsiniz. Komutları kullanılabilir veya kullanılamaz yapma, gizleyebilir veya, göstermek veya denetleyin veya menüsünde seçeneğinin işaretini kaldırın.  
  
 Bir komut görünümünü değiştirmek için şu eylemlerden birini gerçekleştirin:  
  
-   Uygun bayrakları komutu tablo dosyasındaki komut tanımı belirtin.  
  
-   Kullanım <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> hizmeti.  
  
-   Uygulama <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirim ve raw komutu nesneleri değiştirebilirsiniz.  
  
 Aşağıdaki adımlar, bulmak ve yönetilen paket Framework (MPF) kullanarak bir komut görünümünü güncelleştirmek gösterilmektedir.  
  
### <a name="to-change-the-appearance-of-a-menu-command"></a>Menü komutu görünümünü değiştirmek için  
  
1.  ' Ndaki yönergeleri izleyin [menü komutu metin değiştirme](../extensibility/changing-the-text-of-a-menu-command.md) adlı menü öğesi oluşturmak için `New Text`.  
  
2.  ChangeMenuText.cs dosyasında aşağıdaki ekleme deyimini kullanarak:  
  
    ```csharp  
    using System.Security.Permissions;  
    ```  
  
3.  ChangeMenuTextPackageGuids.cs dosyasında aşağıdaki satırı ekleyin:  
  
    ```csharp  
    public const string guidChangeMenuTextPackageCmdSet= "00000000-0000-0000-0000-00000000";  // get the GUID from the .vsct file  
    ```  
  
4.  ChangeMenuText.cs dosyasında ShowMessageBox yöntemindeki kodu aşağıdakilerle değiştirin:  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        var command = sender as OleMenuCommand;  
        if (command.Text == "New Text")  
            ChangeMyCommand(command.CommandID.ID, false);}  
    }  
    ```  
  
5.  Gelen güncelleştirmek istediğiniz komut elde <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService> nesne ve command nesnesinde uygun özellikleri ayarlayın. Örneğin, aşağıdaki yöntemi VSPackage komut belirtilen komuttan kullanılabilir veya kullanılamaz hale getirir. Aşağıdaki kod öğesi adlı menü yapar `New Text` onu tıklatıldıktan sonra kullanılamaz.  
  
    ```csharp  
    public bool ChangeMyCommand(int cmdID, bool enableCmd)  
    {  
        bool cmdUpdated = false;  
        var mcs = this.ServiceProvider.GetService(typeof(IMenuCommandService))  
            as OleMenuCommandService;  
        var newCmdID = new CommandID(new Guid(ChangeMenuTextPackageGuids.guidChangeMenuTextPackageCmdSet), cmdID);  
        MenuCommand mc = mcs.FindCommand(newCmdID);  
        if (mc != null)  
        {  
            mc.Enabled = enableCmd;  
            cmdUpdated = true;  
        }  
        return cmdUpdated;    }  
    }  
    ```  
  
6.  Projeyi derleyin ve hata ayıklamayı Başlat. Visual Studio'nun deneysel örneği görüntülenmesi gerekir.  
  
7.  Üzerinde **Araçları** menüsünde tıklatın **çağırma ChangeMenuText** komutu. Bu noktada komut adıdır **çağırma ChangeMenuText**, bu komut işleyici ChangeMyCommand() çağrısı değil.  
  
8.  Üzerinde **Araçları** artık görmelisiniz menü **yeni metin**. Tıklatın **yeni metin**. Komut şimdi gri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komutları, menüleri ve araç çubukları](../extensibility/internals/commands-menus-and-toolbars.md)   
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md)   
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)