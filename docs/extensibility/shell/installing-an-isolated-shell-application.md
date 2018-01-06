---
title: "Yalıtılmış Kabuk uygulama yükleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shell [Visual Studio], deploying shell-based applications
- Visual Studio shell, deploying shell-based applications
ms.assetid: 33416226-9083-41b5-b153-10d2bf35c012
caps.latest.revision: "40"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6672ed634ad8c8056ae372c9d1d9a3fa44b56243
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="installing-an-isolated-shell-application"></a>Yalıtılmış Kabuk uygulama yükleme
Bir kabuk uygulamasını yüklemek için aşağıdaki adımları gerçekleştirmeniz gerekir.  
  
-   Çözümünüzü hazırlayın.  
  
-   Uygulamanız için bir Windows Installer (MSI) paketi oluşturun.  
  
-   Kurulum önyükleyici oluşturun.  
  
 Bu belgedeki tüm örnek kodları gelir [Kabuk dağıtım örnek](http://go.microsoft.com/fwlink/?LinkId=262245), ve MSDN Web sitesinde kod Galerisi'nden indirebilirsiniz. Örnek bu adımların her biri gerçekleştirme sonuçlarını gösterir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu konuda açıklanan yordamları gerçekleştirmek için aşağıdaki araçları bilgisayarınızda yüklenmesi gerekir.  
  
-   Visual Studio SDK'sı  
  
-   [Windows Installer XML araç takımı](http://go.microsoft.com/fwlink/?LinkId=82720) sürüm 3.6  
  
 Örnek ayrıca Microsoft Visualization ve tüm Kabukları gerektiren modelleme SDK gerektirir.  
  
## <a name="preparing-your-solution"></a>Çözümünüzü hazırlama  
 Varsayılan olarak, kabuk şablonları için VSIX paketleri oluşturmak, ancak bu davranış öncelikle hata ayıklama amacıyla tasarlanmıştır. Kabuk uygulamayı dağıttığınızda, yükleme sırasında yeniden başlatma ve kayıt defteri erişimi için izin vermek için MSI paketleri kullanmanız gerekir. Uygulamanız MSI dağıtım için hazırlamak için aşağıdaki adımları gerçekleştirin.  
  
#### <a name="to-prepare-a-shell-application-for-msi-deployment"></a>Bir kabuk uygulama MSI dağıtım için hazırlamak için  
  
1.  Çözümünüzdeki her .vsixmanifest dosyasını düzenleyin.  
  
     İçinde `Identifier` öğesi ekleme bir `InstalledByMSI` öğesi ve bir `SystemComponent` öğesi ve ardından ayarlanan değerleriyle `true`.  
  
     Bu öğeleri VSIX yükleyici kullanarak kaldırmasını bileşenlerinizi ve kullanıcı yüklemeye çalışmasını engellemek **Uzantılar ve güncelleştirmeler** iletişim kutusu.  
  
2.  VSIX bildirimini içeren her proje için MSI yükleme yapacakları konumunu içeriği çıktısını almak için derleme görevleri düzenleyebilirsiniz. Derleme çıktısında VSIX bildirimini içerir, ancak yapı .vsix dosyası yok.  
  
## <a name="creating-an-msi-for-your-shell"></a>Bir MSI Kabuğunuzu için oluşturma  
 MSI paketinizi oluşturmak için kullanmanız önerilir [Windows Installer XML araç takımı](http://go.microsoft.com/fwlink/?LinkId=82720) olduğundan standart bir kurulum projesi'den daha fazla esneklik sağlar.  
  
 Product.wxs dosyanızda algılama blokları ve Kabuk bileşenleri düzenini ayarlayın.  
  
 Ardından kayıt defteri girdileri .reg dosyasını çözümünüz için hem de ApplicationRegistry.wxs oluşturun.  
  
### <a name="detection-blocks"></a>Algılama blokları  
 Bir algılama blok oluşan bir `Property` algılamak için bir önkoşul belirtir öğesi ve bir `Condition` önkoşul bilgisayarda yoksa döndürmek için bir ileti belirtir öğesi. Örneğin, kabuk uygulamanızı Microsoft Visual Studio Kabuğu yeniden dağıtılabilir gerektirir ve algılama blok aşağıdaki biçimlendirme benzeyecektir.  
  
```xml  
<Property Id="ISOSHELLSFX">  
  <RegistrySearch Id="IsoShellSfx" Root="HKLM" Key="Software\Microsoft\DevDiv\vs\Servicing\\$(var.ShellVersion)\IsoShell\$(var.ProductLanguage)" Name="Install" Type="raw" />  
</Property>  
<Property Id="INTSHELLSFX">  
  <RegistrySearch Id="IntShellSfx" Root="HKLM" Key="SOFTWARE\Microsoft\DevDiv\vs\Servicing\$(var.ShellVersion)\devenv\$(var.ProductLanguage)" Name="Install" Type="raw" />  
</Property>  
  
<Condition Message="This application requires $(var.IsoShellName).  Please install $(var.IsoShellName) then run this installer again.">  
  <![CDATA[Installed OR ISOSHELLSFX]]>  
</Condition>  
<Condition Message="This application requires $(var.IntShellName).  Please install $(var.IntShellName) then run this installer again.">  
  <![CDATA[Installed OR INTSHELLSFX]]>  
</Condition>  
  
```  
  
### <a name="layout-of-shell-components"></a>Kabuk bileşenlerinin düzeni  
 Hedef dizin yapısını ve yüklenecek bileşenleri belirlemek için öğeleri eklemeniz gerekir.  
  
##### <a name="to-set-the-layout-of-shell-components"></a>Kabuk bileşenleri düzenini ayarlamak için  
  
1.  Hiyerarşisini oluşturmak `Directory` öğeleri tüm hedef bilgisayarda dosya sisteminde aşağıdaki örnekte gösterildiği gibi oluşturmak için dizinleri temsil eder.  
  
    ```xml  
    <Directory Id="TARGETDIR" Name="SourceDir">  
      <Directory Id="ProgramFilesFolder">  
        <Directory Id="CompanyDirectory" Name="$(var.CompanyName)">  
          <Directory Id="INSTALLDIR" Name="$(var.FullProductName)">  
            <Directory Id="ExtensionsFolder" Name="Extensions" />  
            <Directory Id="Folder1033" Name="1033" />  
          </Directory>  
        </Directory>  
      </Directory>  
      <Directory Id="ProgramMenuFolder">  
        <Directory Id="ApplicationProgramsFolder" Name="$(var.FullProductName)"/>  
      </Directory>  
    </Directory>  
    ```  
  
     Bu dizinleri tarafından başvurulan `Id` yüklenmelidir dosyaları belirtildiği zaman.  
  
2.  Aşağıdaki örnekte gösterildiği gibi kabuk ve Kabuk uygulamanızı gerektiren bileşenler tanımlayın.  
  
    > [!NOTE]
    >  Bazı öğeler diğer .wxs dosyaları tanımlarında bakabilirsiniz.  
  
    ```xml  
    <Feature Id="ProductFeature" Title="$(var.ShortProductName)Shell" Level="1">  
      <ComponentGroupRef Id="ApplicationGroup" />  
      <ComponentGroupRef Id="HelpAboutPackage" />  
      <ComponentRef Id="GeneralProfile" />  
      <ComponentGroupRef Id="EditorAdornment"/>        
      <ComponentGroupRef Id="SlideShowDesignerGroup"/>  
  
      <!-- Note: The following ComponentGroupRef is required to pull in generated authoring from project references. -->  
      <ComponentGroupRef Id="Product.Generated" />  
    </Feature>  
    ```  
  
    1.  `ComponentRef` Öğesi geçerli bileşen dosyaları tanımlayan başka bir .wxs dosyasına başvuruyor. Örneğin, GeneralProfile aşağıdaki tanımı içinde HelpAbout.wxs sahiptir.  
  
        ```xml  
        <Fragment Id="FragmentProfiles">  
          <DirectoryRef Id="INSTALLDIR">  
            <Directory Id="ProfilesFolder" Name="Profiles">  
              <Component Id='GeneralProfile' Guid='*'>  
                <File Id='GeneralProfile' Name='General.vssettings' DiskId='1' Source='$(var.BuildOutputDir)Profiles\General.vssettings' KeyPath='yes' />  
              </Component>  
            </Directory>  
          </DirectoryRef>  
        </Fragment>  
        ```  
  
         `DirectoryRef` Ögesi, bu dosyaları kullanıcının bilgisayarında nereye belirtir. `Directory` Öğesi belirttiğinden, bir alt dizine ve her yüklenecek `File` öğesi oluşturulan veya çözümün bir parçası var ve bu dosyayı MSI dosyası oluşturulduğunda bulunabileceği tanımlayan bir dosyayı temsil eder.  
  
    2.  `ComponentGroupRef` Öğesi ve diğer bileşenleri (veya bileşenleri bileşen grupları) bir gruba başvuruyor. Örneğin, `ComponentGroupRef` ApplicationGroup altında Application.wxs içinde şu şekilde tanımlanır.  
  
        ```xml  
        <ComponentGroup Id="ApplicationGroup">  
          <ComponentGroupRef Id="DebuggerProxy" />  
          <ComponentRef Id="MasterPkgDef" />  
          <ComponentRef Id="SplashResource" />  
          <ComponentRef Id="IconResource" />  
          <ComponentRef Id="WinPrfResource" />  
          <ComponentRef Id="AppExe" />  
          <ComponentRef Id="AppConfig" />  
          <ComponentRef Id="AppPkgDef" />  
          <ComponentRef Id="AppPkgDefUndef" />  
          <ComponentRef Id="$(var.ShortProductName)UI1033" />  
          <ComponentRef Id="ApplicationShortcut"/>  
          <ComponentRef Id="ApplicationRegistry"/>  
        </ComponentGroup>  
        ```  
  
    > [!NOTE]
    >  Kabuk (Yalýtýlmýþ) uygulamalar için bağımlılıkların gereklidir: DebuggerProxy, MasterPkgDef, kaynakları (özellikle .winprf dosyası), uygulama ve PkgDefs.  
  
### <a name="registry-entries"></a>Kayıt defteri girdileri  
 Kabuk (Yalýtýlmýþ) proje şablonu içeren bir *ProjectName*.reg dosyasını yüklemesinde birleştirmek kayıt defteri anahtarları için. Bu kayıt defteri girdileri MSI yükleme ve temizleme amacıyla bir parçası olması gerekir. İçinde ApplicationRegistry.wxs eşleşen kayıt defteri blokları da oluşturmanız gerekir.  
  
##### <a name="to-integrate-registry-entries-into-the-msi"></a>Kayıt defteri girdileri MSI içine tümleştirmek için  
  
1.  İçinde **Kabuk özelleştirmesi** klasörü, açık *ProjectName*. kayıt  
  
2.  $RootFolder$ belirteci tüm örneklerini hedef yükleme dizini yolu ile değiştirin.  
  
3.  Uygulamanızın gerektirdiği herhangi bir kayıt defteri girdilerini ekleyin.  
  
4.  ApplicationRegistry.wxs açın.  
  
5.  Her kayıt defteri girişi için *ProjectName*.reg, karşılık gelen bir kayıt defteri bloğundan, aşağıdaki örneklerde gösterildiği gibi ekleyin.  
  
    |*ProjectName*.reg|ApplicationRegisty.wxs|  
    |-----------------------|----------------------------|  
    |[HKEY_CLASSES_ROOT\CLSID\\{bb431796-a179-4df7-b65d-c0df6bda7cc6}]<br /><br /> @= "PhotoStudio DTE nesne"|\<RegistryKey Kimliği = 'DteClsidRegKey' kök = 'HKCR' anahtar =' $(var. DteClsidRegKey)' eylemi 'createAndRemoveOnUninstall' = ><br /><br /> \<REGISTRYVALUE türü = 'string' Name =' @' değeri =' $(var. ShortProductName) DTE nesne ' / ><br /><br /> \</ RegistryKey >|  
    |[HKEY_CLASSES_ROOT\CLSID\\{bb431796-a179-4df7-b65d-c0df6bda7cc6} \LocalServer32]<br /><br /> @= "$RootFolder$\PhotoStudio.exe"|\<RegistryKey Kimliği = 'DteLocSrv32RegKey' kök = 'HKCR' anahtar =' $(var. DteClsidRegKey) \LocalServer32' eylemi 'createAndRemoveOnUninstall' = ><br /><br /> \<REGISTRYVALUE türü = 'string' Name =' @' değeri ='[INSTALLDİR] $(var. ShortProductName) .exe ' / ><br /><br /> \</ RegistryKey >|  
  
     Bu örnekte, üst satırda kayıt defteri anahtarında Var.DteClsidRegKey çözümler. Var.ShortProductName çözümler için `PhotoStudio`.  
  
## <a name="creating-a-setup-bootstrapper"></a>Kurulum önyükleyici oluşturma  
 Yalnızca ilk önce tüm önkoşulların yüklü değilse, tamamlanmış MSI yükler. Son kullanıcı deneyimini kolaylaştırmak için toplar ve uygulamanızı yüklemeden önce tüm önkoşulların yükleyen bir Kurulum programı oluşturun. Yüklemenin başarılı olmak için bu eylemleri gerçekleştirin:  
  
-   Yükleme yönetici tarafından zorunlu tutun.  
  
-   Visual Studio Kabuğu (Yalýtýlmýþ) yüklü olup olmadığını algıla.  
  
-   Bir veya iki Kabuk yükleyicileri sırada çalıştırın.  
  
-   Yeniden başlatma istekleri işler.  
  
-   Msi dosyasını çalıştırın.  
  
### <a name="enforcing-installation-by-administrator"></a>Yükleme Yöneticisi tarafından zorlama  
 Bu yordam, \Program dosyaları gibi gerekli dizinler erişmek Kurulum programı etkinleştirmek için gerekli\\.  
  
##### <a name="to-enforce-installation-by-administrator"></a>Yükleme Yöneticisi tarafından zorlamak için  
  
1.  Kurulum projesi için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  Altında **yapılandırma bağlayıcı/özellikler/bildirimi dosyası**ayarlayın **UAC yürütme düzeyini** için **requireAdministrator'a**.  
  
     Bu özellik katıştırılmış bildirim dosyasına yönetici olarak çalıştırılacak programı gerektirir öznitelik koyar.  
  
### <a name="detecting-shell-installations"></a>Kabuk yüklemelerini algılamak  
 Visual Studio Kabuğu (Yalýtýlmýþ) yüklü olup olmadığını belirlemek için önce onu HKLM\Software\Microsoft\DevDiv\vs\Servicing\ShellVersion\isoshell\LCID\Install kayıt defteri değerini denetleyerek yüklü olup olmadığını belirleyin.  
  
> [!NOTE]
>  Bu değerleri de Product.wxs Kabuk algılama bloğunda salt okunurdur.  
  
 HKLM\Software\Microsoft\AppEnv\14.0\ShellFolder burada Visual Studio Kabuğu yüklendi ve dosya için kontrol etmek için konumu belirtir.  
  
 Kabuk yüklemesini algılamak nasıl bir örnek için bkz: `GetProductDirFromReg` Utilities.cpp Kabuk dağıtım örnekteki işlevi.  
  
 Bilgisayarda değil birini veya her ikisini paketinizi gerektirir Visual Studio Kabukları yüklü değilse, yüklenecek bileşenleri listenize eklemeniz gerekir. Bir örnek için bkz: `ComponentsPage::OnInitDialog` ComponentsPage.cpp Kabuk dağıtım örnekteki işlevi.  
  
### <a name="running-the-shell-installers"></a>Kabuk yükleyicileri çalıştırma  
 Kabuk yükleyicileri çalıştırmak için doğru komut satırı bağımsız değişkenleri kullanarak Visual Studio Kabuğu yeniden dağıtılabilir öğeleri çağırın. En azından, komut satırı bağımsız değişkenleri kullanmalısınız **/norestart /q** ve sonraki ne yapılmalı belirlemek dönüş kodu için izleyebilirsiniz. Aşağıdaki örnek redistributable Kabuğu (Yalýtýlmýþ) çalışır.  
  
```  
dwResult = ExecCmd("Vs_IsoShell.exe /norestart /q", TRUE);  
```  
  
### <a name="running-the-shell-language-pack-installers"></a>Kabuk dil paketi yükleyicileri çalıştırma  
 Bunun yerine Kabuk veya kabuklar yüklenen ve yalnızca bir dil paketine gereksinim fark ederseniz, aşağıdaki örnekte gösterildiği gibi dil paketlerini yükleyebilirsiniz.  
  
```  
dwResult = ExecCmd("Vs_IsoShellLP.exe /norestart /q", TRUE);  
  
```  
  
### <a name="deciphering-return-values"></a>Dönüş değerleri şifresini çözme  
 Bazı işletim sistemlerinde, Visual Studio Kabuğu (Yalýtýlmýþ) yükleme yeniden başlatma gerektirir. Bu durum çağrının dönüş kodu tarafından belirlenebilir `ExecCmd`.  
  
|Dönüş Değeri|Açıklama|  
|------------------|-----------------|  
|ERROR_SUCCESS|Yükleme tamamlandı. Uygulamanızı şimdi yükleyebilirsiniz.|  
|ERROR_SUCCESS_REBOOT_REQUIRED|Yükleme tamamlandı. Bilgisayar yeniden başlatıldıktan sonra uygulamayı yükleyebilir.|  
|3015|Yükleme devam ediyor. Yüklemeye devam etmek için bilgisayarın yeniden başlatılması gerekli.|  
  
### <a name="handling-restarts"></a>Yeniden işleme  
 Ne zaman çalıştırdığınız Kabuk yükleyici kullanarak **/norestart** bağımsız değişkeni, belirttiğiniz olmayacaktır bilgisayarı yeniden başlatın veya bilgisayarın yeniden başlatılması için sorun olduğunu. Ancak, bir yeniden başlatılması gerekli olabilir ve bilgisayar yeniden başlatıldıktan sonra yükleyici devam ettiğinden emin olmalısınız.  
  
 Yeniden başlatmalar doğru şekilde işlemek için bu yalnızca bir Kurulum programı sürdürmeye kümesi ve sürdürme işlemi düzgün işlenecek olduğundan emin olun.  
  
 ERROR_SUCCESS_REBOOT_REQUIRED veya 3015 döndürülür, kodunuzu bir yükleme devam etmeden önce bilgisayarı yeniden başlatmanız gerekir.  
  
 Yeniden işlemek için bu eylemleri gerçekleştirin:  
  
-   Windows başladığında yüklemeye devam etmek için kayıt defteri ayarlayın.  
  
-   Önyükleyici çift yeniden gerçekleştirin.  
  
-   Kabuk yükleyici ResumeData anahtarını silin.  
  
-   Windows'u yeniden başlatın.  
  
-   MSI başlangıç yolunu sıfırlayın.  
  
### <a name="setting-the-registry-to-resume-setup-when-windows-starts"></a>Windows başladığında kurulum devam etmek için kayıt defteri ayarı  
 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce\ kayıt defteri anahtarı yönetim izinlerine sahip sistem başlangıcında yürütür ve ardından silinir. HKEY_CURRENT_USER benzer bir anahtar içeriyor, ancak normal bir kullanıcı olarak çalışır ve yüklemeler için uygun değil. Bir dize değeri, yükleyici çağıran RunOnce anahtarı koyarak yükleme devam edebilirsiniz. Ancak, yükleyici kullanarak çağırma öneririz bir **/yeniden** veya başlangıç yerine sürdürüyor uygulama bildirmek için benzer bir parametre. Birden çok kez yeniden başlatılması yüklemelerde özellikle yararlı olur yükleme işleminde nerede belirtmek üzere parametreler de içerir.  
  
 Aşağıdaki örnek, bir yükleme devam ettirme için RunOnce kayıt defteri anahtar değeri gösterir.  
  
 `"c:\MyAppInstaller.exe /restart /SomeOtherDataFlag"`  
  
### <a name="installing-double-restart-of-bootstrapper"></a>Önyükleyici çift yeniden yükleme  
 Kurulum doğrudan RunOnce kullanılırsa, Masaüstü tamamen yük mümkün olmayacaktır. Tam kullanıcı arabirimi kullanılabilir hale getirmek Kur'un başka bir yürütme oluşturmak ve RunOnce örneği bitmelidir.  
  
 Kurulum programı doğru izinleri alır ve aşağıdaki örnekte gösterildiği gibi yeniden başlatmadan önce durduğu bilmek için yeterli bilgi vermeniz gerekir böylece yeniden yürütmeniz gerekir.  
  
```  
if (_cmdLineInfo.IsRestart())  
{  
    TCHAR path[MAX_PATH]={0};  
    GetModuleFileName(NULL, path, MAX_PATH * sizeof(TCHAR));      
    ShellExecute( NULL, _T( "open" ), path, _T("/install"), 0, SW_SHOWNORMAL );  
}  
  
```  
  
### <a name="deleting-the-shell-installer-resumedata-key"></a>Kabuk yükleyici ResumeData anahtarı silme  
 Kabuk yükleyici HKLM\Software\Microsoft\VisualStudio\14.0\Setup\ResumeData kayıt defteri anahtarı yeniden başlatma sonrasında kurulum devam verilerle ayarlar. Uygulamanızın, kabuk yükleyici sürdürme olduğundan, bu kayıt defteri anahtarı aşağıdaki örnekte gösterildiği gibi silin.  
  
```  
CString resumeSetupPath(MAKEINTRESOURCE("SOFTWARE\\Microsoft\\VisualStudio\\14.0\\Setup\\ResumeData"));  
RegDeleteKey(HKEY_LOCAL_MACHINE, resumeSetupPath);  
```  
  
### <a name="restarting-windows"></a>Windows'u yeniden başlatmayı  
 Gerekli kayıt defteri anahtarını ayarladıktan sonra Windows yeniden başlatabilirsiniz. Aşağıdaki örnekte farklı Windows işletim sistemleri için yeniden başlatma komutları çağırır.  
  
```  
OSVERSIONINFO ov;  
HANDLE htoken ;  
//Ask for the SE_SHUTDOWN_NAME token as this is needed by the thread calling for a system shutdown.  
if (OpenProcessToken(GetCurrentProcess(), TOKEN_ADJUST_PRIVILEGES | TOKEN_QUERY, &htoken))  
{  
    LUID luid ;  
    LookupPrivilegeValue(NULL, SE_SHUTDOWN_NAME, &luid) ;  
    TOKEN_PRIVILEGES    privs ;  
    privs.Privileges[0].Luid = luid ;  
    privs.PrivilegeCount = 1 ;  
    privs.Privileges[0].Attributes = SE_PRIVILEGE_ENABLED ;  
    AdjustTokenPrivileges(htoken, FALSE, &privs, 0, (PTOKEN_PRIVILEGES) NULL, 0) ;  
}   
  
//Use InitiateSystemShutdownEx to avoid unexpected restart message box  
try  
{              
    if ( (ov.dwMajorVersion > 5) || ( (ov.dwMajorVersion == 5) && (ov.dwMinorVersion  > 0) ))  
    {  
        bExitWindows = InitiateSystemShutdownEx(0, _T(""), 0, TRUE, TRUE, REASON_PLANNED_FLAG);  
    }  
    else  
    {  
#pragma prefast(suppress:380,"ignore warning about legacy api")  
        bExitWindows = InitiateSystemShutdown(0, _T(""), 0, TRUE, TRUE);  
    }  
}  
catch(...)  
{  
    //advapi32.dll call not available! Will not restart!  
}  
  
```  
  
### <a name="resetting-the-start-path-of-msi"></a>MSI başlangıç yolunu sıfırlama  
 Yeniden başlatma önce Kurulum programının konumunu geçerli dizin olduğu ancak yeniden başlatma sonrasında konumu system32 dizin haline gelir. Kurulum programı aşağıdaki örnekte gösterildiği gibi her MSI çağrıdan önce geçerli dizin sıfırlamanız gerekir.  
  
```  
CString GetSetupPath()  
{  
    TCHAR file[MAX_PATH];  
    GetModuleFileName(NULL, file, MAX_PATH * sizeof(TCHAR));  
    CString path(file);  
    int fpos = path.ReverseFind('\\');  
    if (fpos != -1)  
    {  
        path = path.Left(fpos + 1);  
    }  
  
    return path;  
}  
  
```  
  
### <a name="running-the-application-msi"></a>MSI uygulaması çalıştıran  
 Visual Studio Kabuğu yükleyici ERROR_SUCCESS döndükten sonra uygulamanız için MSI çalıştırabilirsiniz. Kullanıcı arabirimi, Kurulum programı sağladığından, MSI sessiz modda başlatın (**/q**) ve günlük ile (**/L**), aşağıdaki örnekte gösterildiği gibi.  
  
```cpp  
TCHAR temp[MAX_PATH];  
GetTempPath(MAX_PATH, temp);  
  
CString boutiqueInstallCmd, msi, log;  
CString cmdLine(MAKEINTRESOURCE("msiexec /q /I %s /L*vx %s REBOOT=ReallySuppress"));  
CString name(MAKEINTRESOURCE("PhotoStudioIntShell.msi"));  
log.Format(_T("\"%s%s.log\""), temp, name);  
msi.Format(_T("\"%s%s\""), GetSetupPath(), name);  
boutiqueInstallCmd.Format(cmdLine, msi, log);  
  
//TODO: You can use MSI API to gather and present install progress feedback from your MSI.  
dwResult = ExecCmd(boutiqueInstallCmd, FALSE);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Temel Yalıtılmış Kabuk Uygulaması Oluşturma](walkthrough-creating-a-basic-isolated-shell-application.md)