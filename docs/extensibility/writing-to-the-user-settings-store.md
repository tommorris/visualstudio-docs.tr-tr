---
title: "Kullanıcı ayarları deposu için yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efd27f00-7fe5-45f8-9b97-371af732be97
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7a824f0934a260a4e825a5618e5d3b91a500be7b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="writing-to-the-user-settings-store"></a>Kullanıcı ayarları deposu yazma
Kullanıcı ayarlarıdır Listedekilerin gibi yazılabilir ayarları **Araçlar / Seçenekler** iletişim kutusu, özellikleri windows ve belirli bir iletişim kutusu. Visual Studio uzantıları bunlar küçük miktarda veri depolamak için kullanabilirsiniz. Bu kılavuzda Notepad Visual Studio'ya dış bir araç okuma ve yazma için kullanıcı ayarları deposu tarafından nasıl ekleyeceğiniz gösterilmiştir.  
  
### <a name="backing-up-your-user-settings"></a>Bilgisayarınızı kullanıcı ayarları yedekleniyor  
  
1.  Hata ayıklama ve yordamı yineleyin harici araçlar ayarlarına olması gerekir. Bunu yapmak için böylece bunları gereken şekilde geri yükleyebilirsiniz özgün ayarlarına kaydetmeniz gerekir.  
  
2.  Regedit.exe açın.  
  
3.  HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0Exp\External Araçları'nın üzerine gidin\\.  
  
    > [!NOTE]
    >  \14.0Exp\ ve değil \14.0 içeren anahtar baktığınızdan emin olun\\. Visual Studio'nun deneysel örneği çalıştırdığınızda, kullanıcı kayıt defteri kovanında "14.0Exp" ayarlardır.  
  
4.  \External Tools\ anahtarını sağ tıklatın ve ardından **verme**. Olduğundan emin olun **Seçili dal** seçilir.  
  
5.  Sonuçta elde edilen dış Tools.reg dosyasını kaydedin.  
  
6.  Daha sonra harici araçlar ayarlara döndürmek istediğinizde, HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0Exp\External Tools\ kayıt defteri anahtarı seçin ve tıklatın **silmek** bağlam menüsünde.  
  
7.  Zaman **Anahtar Silinmesini Onayla** iletişim kutusu görüntülenirse, tıklatın **Evet**.  
  
8.  Daha önce kaydettiğiniz dış Tools.reg dosyaya sağ tıklayın, **birlikte Aç**ve ardından **Kayıt Defteri Düzenleyicisi'ni**.  
  
## <a name="writing-to-the-user-settings-store"></a>Kullanıcı ayarları deposu yazma  
  
1.  UserSettingsStoreExtension adlı VSIX projesi oluşturun ve ardından UserSettingsStoreCommand adlı özel bir komut ekleyin. Özel bir komut oluşturma hakkında daha fazla bilgi için bkz: [menü komutu ile bir uzantısı oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
2.  UserSettingsStoreCommand.cs içinde aşağıdaki ekleme deyimlerini kullanarak:  
  
    ```csharp  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Settings;  
    using Microsoft.VisualStudio.Shell.Settings;  
    ```  
  
3.  MenuItemCallback, yönteminin gövdesi silin ve kullanıcının ayarlarını depolamak, aşağıdaki gibi alın:  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);  
    }  
    ```  
  
4.  Şimdi olup Not Defteri zaten dış bir araç ayarlanmış bulun. ToolCmd ayarı "Not" gibi olup olmadığını belirlemek için tüm dış araçları üzerinden yineleme gerekir:  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);  
  
        // Find out whether Notepad is already an External Tool.  
        int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys");  
        bool hasNotepad = false;  
        CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo;  
        for (int i = 0; i < toolCount; i++)  
        {  
            if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0)  
            {  
                hasNotepad = true;  
                break;  
            }  
        }  
    }  
  
    ```  
  
5.  Not Defteri'ni dış bir araç ayarlanmamışsa, aşağıdaki gibi ayarlayın:  
  
    ```vb  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);  
  
        // Find out whether Notepad is already installed.  
        int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys");  
        bool hasNotepad = false;  
        CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo;  
        for (int i = 0; i < toolCount; i++)  
        {  
            if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0)  
            {  
                hasNotepad = true;  
                break;  
            }  
        }  
  
        string message = (hasNotepad) ? "Notepad already installed" : "Installing Notepad";  
         if (!hasNotepad)  
        {  
            userSettingsStore.SetString("External Tools", "ToolTitle" + toolCount, "&Notepad");  
            userSettingsStore.SetString("External Tools", "ToolCmd" + toolCount, "C:\\Windows\\notepad.exe");  
            userSettingsStore.SetString("External Tools", "ToolArg" + toolCount, "");  
            userSettingsStore.SetString("External Tools", "ToolDir" + toolCount, "$(ProjectDir)");  
            userSettingsStore.SetString("External Tools", "ToolSourceKey" + toolCount, "");  
            userSettingsStore.SetUInt32("External Tools", "ToolOpt" + toolCount, 0x00000011);  
  
            userSettingsStore.SetInt32("External Tools", "ToolNumKeys", toolCount + 1);  
        }  
    }  
    ```  
  
6.  Kodu test edin. İkinci kez çalıştırmadan önce kayıt defterini geri alma işlemleri gerekir böylece, dış bir araç not defteri ekler unutmayın.  
  
7.  Kod derleme ve hata ayıklamayı Başlat.  
  
8.  Üzerinde **Araçları** menüsünde tıklatın **çağırma UserSettingsStoreCommand**. Bu, Not Defteri'ne ekler **Araçları** menüsü.  
  
9. Artık araçları Notepad görmelisiniz / seçenekleri menüsü ve tıklatarak **not defteri** not defteri örneği duruma getirmeniz gerekir.