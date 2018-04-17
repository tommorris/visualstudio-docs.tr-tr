---
title: Ayarları deposunu kullanan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Settings Store, using
ms.assetid: 447ec08a-eca5-40b8-89b0-f98fdf3d39a4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3919ee3973194967f9d0367ecd13c495b3b62af2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="using-the-settings-store"></a>Ayarları deposu kullanma
Ayarları depolar iki tür vardır:  
  
-   Salt okunur Visual Studio ve VSPackage ayarları yapılandırma ayarları. Visual Studio ayarları tüm bilinen .pkgdef dosyalarından Bu depoya birleştirir.  
  
-   Yazılabilir ayarları sayfalarında görüntülenen olanlar gibi kullanıcı ayarları **seçenekleri** iletişim kutusu, özellik sayfaları ve belirli bir iletişim kutusu. Visual Studio uzantıları bunlar küçük miktarda veri yerel depolama için kullanabilir.  
  
 Bu kılavuz, yapılandırma ayarı Mağazası'ndan verileri okumak gösterilmiştir. Bkz: [kullanıcı ayarları deposu için yazma](../extensibility/writing-to-the-user-settings-store.md) nasıl yazılacağını kullanıcı ayarları deposu için bir açıklama için.  
  
## <a name="creating-the-example-project"></a>Örnek Proje oluşturma  
 Bu bölümde tanıtım için menü komutu ile basit uzantı projesi oluşturulacağını gösterir.  
  
1.  Visual Studio uzantılarının uzantısı varlıklar yer alacağı VSIX dağıtım projesi ile başlar. Oluşturma bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] adlı VSIX proje `SettingsStoreExtension`. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C# / genişletilebilirlik**.  
  
2.  Şimdi adlı bir özel komut öğesi şablonu Ekle **SettingsStoreCommand**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# / genişletilebilirlik** seçip **özel komut**. İçinde **adı** alan penceresinin alt kısmında, komut dosyası adı Değiştir **SettingsStoreCommand.cs**. Özel bir komut oluşturma hakkında daha fazla bilgi için bkz: [menü komutu ile bir uzantısı oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
## <a name="using-the-configuration-settings-store"></a>Yapılandırma ayarları deposu kullanma  
 Bu bölümde, algılamak ve yapılandırma ayarlarını görüntülemek gösterilmiştir.  
  
1.  Aşağıdaki SettingsStorageCommand.cs dosyasına ekleyin using deyimleri:  
  
    ```  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Settings;  
    using Microsoft.VisualStudio.Shell.Settings;  
    using System.Windows.Forms;  
    ```  
  
2.  İçinde `MenuItemCallback`yönteminin gövdesi kaldırın ve bu satırları Al yapılandırma ayarları deposu ekleyin:  
  
    ```  
    SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
    SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.Settings.ShellSettingsManager> Üzerinden yönetilen yardımcı sınıf olan <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsManager> hizmet.  
  
3.  Artık Windows Phone araçlarının yüklü olduğu çıkışı bulun. Kod gibi görünmelidir:  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);  
        SettingsStore configurationSettingsStore = settingsManager.GetReadOnlySettingsStore(SettingsScope.Configuration);  
        bool arePhoneToolsInstalled = configurationSettingsStore.CollectionExists(@"InstalledProducts\Microsoft Windows Phone Developer Tools");  
        string message = "Microsoft Windows Phone Developer Tools: " + arePhoneToolsInstalled;  
        MessageBox.Show(message);  
    }  
    ```  
  
4.  Kodu test edin. Projeyi derleyin ve hata ayıklamayı Başlat.  
  
5.  Deneysel örneğinde üzerinde **Araçları** menüsünde tıklatın **çağırma SettingsStoreCommand**.  
  
     Kutusunu iletisini görmeniz gerekir **Microsoft Windows Phone geliştirici araçları:** arkasından **True** veya **False**.  
  
 Visual Studio ayarları deposu sistem kayıt defterinde tutar.  
  
#### <a name="to-use-a-registry-editor-to-verify-configuration-settings"></a>Yapılandırma ayarları doğrulamak için bir kayıt defteri Düzenleyicisi'ni kullanmak için  
  
1.  Regedit.exe açın.  
  
2.  İçin HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0Exp_Config\InstalledProducts gidin\\.  
  
    > [!NOTE]
    >  \14.0Exp_Config\ ve değil \14.0_Config içeren anahtar baktığınızdan emin olun\\. Visual Studio'nun deneysel örneği çalıştırdığınızda, yapılandırma kayıt defteri kovanında "14.0Exp_Config" ayarlardır.  
  
3.  \Installed Products\ düğümünü genişletin. İleti, önceki adımlarda, **Microsoft Windows Phone geliştirici araçları yüklü: True**, sonra da \Installed Products\ bir Microsoft Windows Phone geliştirici araçları düğümünü de içermelidir. İleti, **Microsoft Windows Phone geliştirici araçları yüklü: yanlış**, sonra da \Installed Products\ bir Microsoft Windows Phone geliştirici araçları düğümü içermemesi gerekir.