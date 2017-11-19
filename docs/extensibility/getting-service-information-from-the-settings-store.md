---
title: "Hizmet bilgileri ayarlarını mağazadan almasının | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7028d440-d16d-4b08-9b94-eb8cc93b25fc
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a8508f0d017ba94981f5f54c7a8b63c7528ac6e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="getting-service-information-from-the-settings-store"></a>Ayarları Mağazası'ndan hizmet bilgileri alınıyor
Ayarları deposu tüm kullanılabilir hizmetler bulmak için veya belirli bir hizmet yüklü olup olmadığını belirlemek için kullanabilirsiniz. Hizmet sınıfı türünü bilmeniz gerekir.  
  
### <a name="to-list-the-available-services"></a>Kullanılabilir hizmetler listelemek için  
  
1.  FindServicesExtension adlı VSIX projesi oluşturun ve ardından FindServicesCommand adlı özel bir komut ekleyin. Özel bir komut oluşturma hakkında daha fazla bilgi için bkz: [menü komutu ile bir uzantısı oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
2.  FindServicesCommand.cs içinde aşağıdaki ekleme deyimlerini kullanarak:  
  
    ```vb  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Settings;  
    using Microsoft.VisualStudio.Shell.Settings;  
    using System.Windows.Forms;  
    ```  
  
3.  Yapılandırma ayarları deposu almak, ardından Hizmetleri adlı koleksiyonla bulun. Bu koleksiyon, tüm kullanılabilir hizmetler içerir. MenuItemCommand yöntemi var olan kodu kaldırın ve aşağıdakiyle değiştirin:  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
        string message = "Available services:\n";  
        IEnumerable<string> collection = configurationSettingsStore.GetSubCollectionNames("Services");  
        int n = 0;  
        foreach (string service in collection)  
        {  
            message += configurationSettingsStore.GetString("Services\\" + service, "Name", "Unknown") + "\n";  
        }  
  
        MessageBox.Show(message);  
    }  
    ```  
  
4.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir.  
  
5.  Deneysel örneğinde üzerinde **Araçları** menüsünde tıklatın **çağırma FindServicesCommand**.  
  
     Tüm hizmetler listeleyen bir ileti kutusu görmeniz gerekir.  
  
     Bu ayarları doğrulamak için Kayıt Defteri Düzenleyicisi'ni kullanabilirsiniz.  
  
## <a name="finding-a-specific-service"></a>Belirli bir hizmet bulma  
 Aynı zamanda <xref:Microsoft.VisualStudio.Settings.SettingsStore.CollectionExists%2A> belirli bir hizmet yüklü olup olmadığını belirlemek amacıyla yöntemi. Hizmet sınıfı türünü bilmeniz gerekir.  
  
1.  Yapılandırma ayarları deposu için önceki yordamda oluşturduğunuz proje MenuItemCallback içinde arama `Services` hizmet GUID ile adlı koleksiyonla sahip koleksiyonu. Bu durumda biz için Yardım hizmeti arar.  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
        string helpServiceGUID = typeof(SVsHelpService).GUID.ToString("B").ToUpper();  
        bool hasHelpService = configurationSettingsStore.CollectionExists("Services\\" + helpServiceGUID);  
        string message = "Help Service Available: " + hasHelpService;  
  
        MessageBox.Show(message);  
    }  
    ```  
  
2.  Projeyi derleyin ve hata ayıklamayı Başlat.  
  
3.  Deneysel örneğinde üzerinde **Araçları** menüsünde tıklatın **çağırma FindServicesCommand**.  
  
     Metin içeren bir ileti görürsünüz **Yardım hizmeti kullanılabilir:** arkasından **True** veya **False**. Bu ayarı doğrulamak için önceki adımlarda gösterildiği gibi bir kayıt defteri düzenleyicisi kullanabilirsiniz.