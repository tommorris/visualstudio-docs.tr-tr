---
title: 'Nasıl yapılır: ekleme listesi güvenliğini yapılandırma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio
- inclusion lists [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f8995e95ed1a35841aab945daa1ea35854946b56
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-inclusion-list-security"></a>Nasıl Yapılır: Ekleme Listesi Güvenliğini Yapılandırma
  Yönetici izinlerine sahipseniz, yapılandırabileceğiniz [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] denetlemek için son kullanıcıların Office çözümleri listesine bir güven kararı kaydederek yükleme seçeneği verilip verilmediğini güven istemi. Ekleme listeleri hakkında daha fazla bilgi için bkz: [güvenen Office çözümleri ekleme listeleri kullanarak tarafından](../vsto/trusting-office-solutions-by-using-inclusion-lists.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Her beş bölgeleri çözümleri için aşağıdaki seçenekleri ayarlayabilirsiniz:  
  
-   Etkinleştirme [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] güven istemi anahtarını ve ekleme listesi. Son kullanıcıların herhangi bir sertifika ile imzalanmış Office çözümlerine güven verme izin verebilirsiniz.  
  
-   Kısıtlama [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] güven istemi anahtarını ve ekleme listesi. Yayımcı tanımlar, ancak zaten güvenilir olmayan bir sertifikayla imzalanmış Office çözümleri yüklemek son kullanıcılara izin verebilirsiniz.  
  
-   Devre dışı [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] güven istemi anahtarını ve ekleme listesi. Son kullanıcılar açıkça güvenilir bir sertifika ile imzalanmamış herhangi bir Office çözümü yüklemesini engelleyebilir.  
  
## <a name="enabling-the-inclusion-list"></a>Ekleme listelerini etkinleştirme  
 Son kullanıcılara bu bölgeden gelen herhangi bir Office çözümü çalıştırma ve yükleme seçeneğiyle gösterilmesini istediğiniz zaman bir bölgenin ekleme listesi etkinleştirin.  
  
#### <a name="to-enable-the-inclusion-list-by-using-the-registry-editor"></a>Kayıt Defteri Düzenleyicisi'ni kullanarak ekleme listesini etkinleştirmek için  
  
1.  Kayıt Defteri Düzenleyicisi'ni açın:  
  
    1.  Tıklatın **Başlat**ve ardından **çalıştırmak**.  
  
    2.  İçinde **açık** kutusuna **regedt32.exe**ve ardından **Tamam**.  
  
2.  Aşağıdaki kayıt defteri anahtarını bulun:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Anahtar mevcut değilse oluşturun.  
  
3.  Aşağıdaki alt anahtarları olarak ekleyin **dize değeri**, zaten ilişkili değerleri ile birlikte mevcut değil.  
  
    |Dize değeri alt anahtarı|Değer|  
    |-------------------------|-----------|  
    |**Internet**|**AuthenticodeRequired**|  
    |**UntrustedSites**|**devre dışı**|  
    |**Bilgisayarım**|**Etkin**|  
    |**LocalIntranet**|**Etkin**|  
    |**TrustedSites**|**Etkin**|  
  
     Varsayılan olarak, **Internet** değerine sahip **AuthenticodeRequired** ve **UntrustedSites** değerine sahip **devre dışı**.  
  
#### <a name="to-enable-the-inclusion-list-programmatically"></a>Ekleme listesini programlı olarak etkinleştirmek için  
  
1.  Visual Basic veya Visual C# konsol uygulaması oluşturun.  
  
2.  Düzenlemek için Program.vb veya Program.cs dosyasını açın ve aşağıdaki kodu ekleyin.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Enabled")  
    key.SetValue("LocalIntranet", "Enabled")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "Enabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Enabled");  
    key.SetValue("LocalIntranet", "Enabled");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "Enabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Derleme ve uygulamayı çalıştırın.  
  
## <a name="restricting-the-inclusion-list"></a>Ekleme listelerini kısıtlama  
 Çözümleri, kullanıcılar için bir güven kararı istenir önce kimlik bilmesinin Authenticode sertifikaları kullanılarak imzalanmalıdır. böylece ekleme listesini sınırlayın.  
  
#### <a name="to-restrict-the-inclusion-list"></a>Ekleme listesini kısıtlamak için  
  
1.  Kayıt Defteri Düzenleyicisi'ni açın:  
  
    1.  Tıklatın **Başlat**ve ardından **çalıştırmak**.  
  
    2.  İçinde **açık** kutusuna **regedt32.exe**ve ardından **Tamam**.  
  
2.  Aşağıdaki kayıt defteri anahtarını bulun:  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Anahtar mevcut değilse oluşturun.  
  
3.  Aşağıdaki alt anahtarları olarak ekleyin **dize değeri**, zaten ilişkili değerleri ile birlikte mevcut değil.  
  
    |Dize değeri alt anahtarı|Değer|  
    |-------------------------|-----------|  
    |**UntrustedSites**|**devre dışı**|  
    |**Internet**|**AuthenticodeRequired**|  
    |**Bilgisayarım**|**AuthenticodeRequired**|  
    |**LocalIntranet**|**AuthenticodeRequired**|  
    |**TrustedSites**|**AuthenticodeRequired**|  
  
     Varsayılan olarak, **Internet** değerine sahip **AuthenticodeRequired** ve **UntrustedSites** değerine sahip **devre dışı**.  
  
#### <a name="to-restrict-the-inclusion-list-programmatically"></a>Ekleme listesini programlı olarak kısıtlamak için  
  
1.  Visual Basic veya Visual C# konsol uygulaması oluşturun.  
  
2.  Düzenlemek için Program.vb veya Program.cs dosyasını açın ve aşağıdaki kodu ekleyin.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "AuthenticodeRequired")  
    key.SetValue("LocalIntranet", "AuthenticodeRequired")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "AuthenticodeRequired")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "AuthenticodeRequired");  
    key.SetValue("LocalIntranet", "AuthenticodeRequired");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "AuthenticodeRequired");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Derleme ve uygulamayı çalıştırın.  
  
## <a name="disabling-the-inclusion-list"></a>Ekleme listesi devre dışı bırakma  
 Son kullanıcılar yalnızca güvenilir ve bilinen bir sertifikayla imzalanmış çözümleri yükleyebilmek ekleme listesi devre dışı bırakabilirsiniz.  
  
#### <a name="to-disable-the-inclusion-list"></a>Ekleme listesi devre dışı bırakmak için  
  
1.  Kayıt Defteri Düzenleyicisi'ni açın:  
  
    1.  Tıklatın **Başlat**ve ardından **çalıştırmak**.  
  
    2.  İçinde **açık** kutusuna **regedt32.exe**ve ardından **Tamam**.  
  
2.  Bu zaten yoksa, aşağıdaki kayıt defteri anahtarı oluşturun:  
  
     **\HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel**  
  
3.  Aşağıdaki alt anahtarları olarak ekleyin **dize değeri**, zaten ilişkili değerleri ile birlikte mevcut değil.  
  
    |Dize değeri alt anahtarı|Değer|  
    |-------------------------|-----------|  
    |**UntrustedSites**|**devre dışı**|  
    |**Internet**|**devre dışı**|  
    |**Bilgisayarım**|**devre dışı**|  
    |**LocalIntranet**|**devre dışı**|  
    |**TrustedSites**|**devre dışı**|  
  
#### <a name="to-disable-the-inclusion-list-programmatically"></a>Ekleme listesi program aracılığıyla devre dışı bırakmak için  
  
1.  Visual Basic veya Visual C# konsol uygulaması oluşturun.  
  
2.  Düzenlemek için Program.vb veya Program.cs dosyasını açın ve aşağıdaki kodu ekleyin.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Disabled")  
    key.SetValue("LocalIntranet", "Disabled")  
    key.SetValue("Internet", "Disabled")  
    key.SetValue("TrustedSites", "Disabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Disabled");  
    key.SetValue("LocalIntranet", "Disabled");  
    key.SetValue("Internet", "Disabled");  
    key.SetValue("TrustedSites", "Disabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
  
    ```  
  
3.  Derleme ve uygulamayı çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ekleme listelerini kullanarak Office çözümlerine güvenme](../vsto/trusting-office-solutions-by-using-inclusion-lists.md)   
 [Office Çözümleri Güvenliğini Sağlama](../vsto/securing-office-solutions.md)  
  
  