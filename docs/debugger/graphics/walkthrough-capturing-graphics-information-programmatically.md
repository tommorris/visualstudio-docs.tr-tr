---
title: "İzlenecek yol: Grafik bilgilerini programla yakalama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5adeff9-afaf-4047-b5ce-ef0aefe710eb
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 59853bf733364f2db8a60e3c9515e2771c8e4ebe
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-capturing-graphics-information-programmatically"></a>İzlenecek Yol: Grafik Bilgilerini Programla Yakalama
Kullanabileceğiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] program aracılığıyla bir Direct3D uygulamasından grafik bilgilerini yakalama için grafik tanılama.  
  
 Programlı yakalama gibi senaryolarda kullanışlıdır:  
  
-   Grafik uygulamanızı swapchain mevcut bir doku zaman işleyen gibi kullandığınızda değil yakalama programlı olarak başlar.  
  
-   Uygulamanız, ne zaman DirectCompute hesaplamalar gerçekleştirmek için kullandığı gibi işleme değil, yakalama programlı olarak başlar.  
  
-   Çağrı `CaptureCurrentFrame`kullandığınızda bir işleme sorun düşündüğünüz ve el ile test yakalamak zordur ancak program aracılığıyla çalışma zamanında uygulama durumu hakkındaki bilgileri kullanarak tahmin.  
  
##  <a name="CaptureDX11_2"></a>Windows 8.1 programlı yakalama  
 Kılavuzun bu bölümü sağlam yakalama yöntemini kullanan Windows 8.1 DirectX 11.2 API kullanan uygulamalar programlı yakalama gösterir. Windows 8. 0'DirectX önceki sürümlerini kullanan uygulamalarda programlı yakalama kullanma hakkında daha fazla bilgi için bkz: [programlı yakalama Windows 8.0 ve öncesi](#CaptureDX11_1) bu kılavuzda daha sonra.  
  
 Bu bölümde bu görevlerin nasıl yapılacağını gösterir:  
  
-   Programlı yakalama kullanmak için uygulamanızı hazırlama  
  
-   IDXGraphicsAnalysis arabirimi alma  
  
-   Graf bilgilerini yakalama  
  
> [!NOTE]
>  Programlı yakalama önceki uygulamaları dayanıyordu uzak araçlar için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Yakalama işlevselliği sağlamak için Windows 8.1 yakalama Direct3D 11.2 aracılığıyla doğrudan destekler. Sonuç olarak, artık Windows 8.1 programlı yakalama için Uzak araçları yüklemeniz gerekmez.  
  
### <a name="preparing-your-app-to-use-programmatic-capture"></a>Programlı yakalama kullanmak için uygulamanızı hazırlama  
 Uygulamanızda programlı yakalama kullanmak için gerekli üstbilgileri içermelidir. Bu üstbilgileri Windows 8.1 SDK'ın bir parçasıdır.  
  
##### <a name="to-include-programmatic-capture-headers"></a>Programlı yakalama üstbilgileri dahil etmek için  
  
-   Bu üstbilgileri IDXGraphicsAnalysis arabirimi burada tanımlayacaksınız kaynak dosyasına ekleyin:  
  
    ```  
    #include <DXGItype.h>  
    #include <dxgi1_2.h>  
    #include <dxgi1_3.h>  
    #include <DXProgrammableCapture.h>  
    ```  
  
    > [!IMPORTANT]
    >  Üstbilgi dosyası vsgcapture.h—which destekler programlı yakalama Windows 8.0 ve öncesi içermez; Windows 8.1 uygulamalarınızda programlı yakalama gerçekleştirmek için. Bu üst DirectX 11.2 ile uyumlu değil. D3d11_2.h üstbilgisi dahil tamamlandıktan sonra bu dosya bulunur, derleyici bir uyarı verir. Vsgcapture.h d3d11_2.h önce eklediyseniz, uygulama başlatılmaz.  
  
    > [!NOTE]
    >  Varsa Haziran 2010 DirectX SDK makinenize yüklü olduğundan ve projenizin INCLUDE yolu içeren `%DXSDK_DIR%includex86`, INCLUDE yolu sonuna taşıyın. Kitaplık yolu için aynı işlemi yapın.  
  
#### <a name="windows-phone-81"></a>Windows Phone 8.1  
 Windows Phone 8.1 SDK'sını DXProgrammableCapture.h üstbilgi içermediği için tanımlamak gerekir `IDXGraphicsAnalysis` , kullanabilmesi için kendiniz arabirim `BeginCapture()` ve `EndCapture()` yöntemleri. Önceki bölümde açıklandığı gibi, diğer üst bilgiler içerir.  
  
###### <a name="to-define-the-idxgraphicsanalysis-interface"></a>IDXGraphicsAnalysis arabirimi tanımlamak için  
  
-   Üstbilgi dosyaları dahil dosyasında IDXGraphicsAnalysis arabirimi tanımlayın.  
  
    ```  
    interface DECLSPEC_UUID("9f251514-9d4d-4902-9d60-18988ab7d4b5") DECLSPEC_NOVTABLE  
    IDXGraphicsAnalysis : public IUnknown  
    {  
        STDMETHOD_(void, BeginCapture)() PURE;  
        STDMETHOD_(void, EndCapture)() PURE;  
    };  
    ```  
  
 Kolaylık olması için yeni bir üstbilgi dosyasında aşağıdaki adımları gerçekleştirin ve ardından duyulduğu uygulamanızda dahil edin.  
  
### <a name="getting-the-idxgraphicsanalysis-interface"></a>IDXGraphicsAnalysis arabirimi alma  
 DirectX 11.2 grafik bilgileri yakalamak için önce DXGI hata ayıklama arabirimi almak zorunda.  
  
> [!IMPORTANT]
>  Programlı yakalama kullanırken, uygulamanızı grafik tanılama altında hala çalıştırmanız gerekir (Alt + F5'e [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]) ya da altında [yakalama komut satırı aracı](command-line-capture-tool.md).  
  
##### <a name="to-get-the-idxgraphicsanalysis-interface"></a>IDXGraphicsAnalysis arabirimi almak için  
  
-   Aşağıdaki kod DXGI hata ayıklama arabirimi IDXGraphicsAnalysis arabirimine bağlanacağını için kullanın.  
  
    ```  
    IDXGraphicsAnalysis* pGraphicsAnalysis;  
    HRESULT getAnalysis = DXGIGetDebugInterface1(0, __uuidof(pGraphicsAnalysis), reinterpret_cast<void**>(&pGraphicsAnalysis));  
    ```  
  
     Kontrol ettiğinizden emin olun `HRESULT` tarafından döndürülen `DXGIGetDebugInterface1` kullanmadan önce geçerli bir arabirim alırsınız emin olmak için:  
  
    ```  
    if (FAILED(getAnalysis))  
    {  
        // Abort program or disable programmatic capture in your app.  
    }  
    ```  
  
    > [!NOTE]
    >  Varsa `DXGIGetDebugInterface1` döndürür `E_NOINTERFACE` (`error: E_NOINTERFACE No such interface supported`), uygulama, grafik tanılama altında çalıştığından emin olun (Alt + F5'e [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]).  
  
### <a name="capturing-graphics-information"></a>Graf bilgilerini yakalama  
 Geçerli bir sahip olduğunuza `IDXGraphicsAnalysis` arabirimi kullanabilir `BeginCapture` ve `EndCapture` grafik bilgilerini yakalama için.  
  
##### <a name="to-capture-graphics-information"></a>Grafik bilgilerini yakalama  
  
-   Grafik bilgilerini yakalama başlatmak için kullanmak `BeginCapture`:  
  
    ```  
    ...  
    pGraphicsAnalysis->BeginCapture();  
    ...  
    ```  
  
     Yakalama işlemi başladığında hemen zaman `BeginCapture` olarak adlandırılır; sonraki çerçevenin başlamak bekleyin değil. Geçerli çerçeve sunulduğunda veya çağırdığınızda durakları yakalama `EndCapture`:  
  
    ```  
    ...  
    pGraphicsAnalysis->EndCapture();  
    ...  
    ```  
  
##  <a name="CaptureDX11_1"></a>Windows 8.0 ve öncesi programlı yakalama  
 Kılavuzun bu bölümü eski yakalama yöntemini kullanır DirectX 11.1 API kullanan uygulamalarda Windows 8.0 ve önceki sürümleri programlı yakalama gösterir. Windows 8.1 DirectX 11.2 kullanan uygulamalarda programlı yakalama kullanma hakkında daha fazla bilgi için bkz: [Programmatic yakalama Windows 8.1](#CaptureDX11_2) bu kılavuzda önceki.  
  
 Bu bölümü, bu görevleri gösterir:  
  
-   Bilgisayarınızı programlı yakalama kullanacak şekilde hazırlama  
  
-   Programlı yakalama kullanmak için uygulamanızı hazırlama  
  
-   Grafik günlük dosyasının konumunu ve adını yapılandırma  
  
-   Kullanarak `CaptureCurrentFrame` API  
  
### <a name="preparing-your-computer-to-use-programmatic-capture"></a>Bilgisayarınızı programlı yakalama kullanacak şekilde hazırlama  
 İçin Uzak araçları programlı yakalama API kullanan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Yakalama işlevselliği sağlamak için. Uygulamanın çalıştırılacağı bilgisayar uzak araçları bile, yerel bilgisayarınızda programlı yakalama kullanırken yüklü olması gerekir. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]yerel bir bilgisayar üzerinde programlı yakalama gerçekleştirdiğinizde çalışıyor olması gerekmez.  
  
 Bir bilgisayarda çalışan bir uygulama uzak yakalama API'leri kullanmak için öncelikle için Uzak araçları yüklemeniz gerekir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] o bilgisayardaki. Uzak araçları farklı sürümlerini farklı donanım platformları destekler. Uzak Araçları'nı yükleme hakkında daha fazla bilgi için bkz: [uzak araçları indirme sayfasına](http://go.microsoft.com/fwlink/p/?LinkId=246691) Microsoft Web sitesi yükler.  
  
 Alternatif olarak, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 32-bit uygulamalar için Uzak yakalama gerçekleştirmek için gerekli bileşenleri yükler.  
  
> [!NOTE]
>  Çünkü çoğu Windows Masaüstü uygulamaları — dahil olmak üzere [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]— desteklenmez [!INCLUDE[win8](../includes/win8_md.md)] ARM cihazlar için Uzak araçları kullanarak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] birlikte programlı yakalama API ARM cihazlarda grafik tanılama yakalama için tek yoludur.  
  
### <a name="preparing-your-app-to-use-programmatic-capture"></a>Programlı yakalama kullanmak için uygulamanızı hazırlama  
 Grafik tanılama araçları kullanmak için öncelikle kullanır. Grafik bilgilerini yakalama gerekir. Kullanarak program aracılığıyla bilgi yakalayabilirsiniz `CaptureCurrentFrame` API.  
  
##### <a name="to-prepare-your-app-to-capture-graphics-information-programmatically"></a>Grafik bilgilerini programla yakalama için uygulamanızı hazırlamak için  
  
1.  Olduğundan emin olun `vsgcapture.h` üstbilgi uygulama için kaynak kod yer almaktadır. Yalnızca tek bir konumda bulunan — Örneğin, burada, çağıracaktır programlı kaynak kodu dosyasına API yakalama — veya birden çok kaynak kodu dosyaları API'yi çağırmak için önceden derlenmiş üstbilgi dosyası.  
  
2.  Geçerli çerçevenin geri kalanı yakalamak istediğiniz her uygulama için kaynak kodunu çağırın `g_pVsgDbg->CaptureCurrentFrame()`. Bu yöntem parametre almaz ve bir değer döndürmüyor.  
  
### <a name="configuring-the-name-and-location-of-the-graphics-log-file"></a>Grafik günlük dosyasının konumunu ve adını yapılandırma  
 Grafik günlük tarafından tanımlanmış. konumda oluşturulur `DONT_SAVE_VSGLOG_TO_TEMP` ve `VSG_DEFAULT_RUN_FILENAME` makroları.  
  
##### <a name="to-configure-the-name-and-location-of-the-graphics-log-file"></a>Grafik günlük dosyasının konumunu ve adını yapılandırmak için  
  
-   Grafik günlük temp dizini için yazılmış önce önlemek için `#include <vsgcapture.h>` satır, bunu ekleyin:  
  
    ```  
    #define DONT_SAVE_VSGLOG_TO_TEMP  
    ```  
  
     Grafik günlük çalışma dizini ile ilişkili olan bir konuma veya mutlak bir yol yazmak için bu değeri tanımlayabilirsiniz, tanımını `VSG_DEFAULT_RUN_FILENAME` mutlak bir yol.  
  
-   Grafik günlük farklı bir konuma kaydedin veya farklı bir dosya adı, önce vermek için `#include <vsgcapture.h>` satır, bunu ekleyin:  
  
    ```  
    #define VSG_DEFAULT_RUN_FILENAME <filename>  
    ```  
  
     Bu adım gerçekleştirme, default.vsglog dosya adı değil. Siz tanımlarsanız `DONT_SAVE_VSGLOG_TO_TEMP`, ardından dosyasının konumunu göre temp dizini; bir mutlak dosya adı belirtilirse Aksi halde, çalışma dizine göreli veya başka bir konumda.  
  
 İçin [!INCLUDE[win8_appname_long](../includes/win8_appname_long_md.md)] uygulamalar temp dizininin konumu her kullanıcı ve uygulama özeldir ve genellikle C:\users gibi bir konumda bulunan\\*kullanıcıadı*\AppData\Local\Packages\\ *paket ailesi adı*\TempState\\. Masaüstü uygulamalarında temp dizininin konumu her kullanıcı için özeldir ve genellikle C:\Users gibi bir konumda bulunan\\*kullanıcıadı*\AppData\Local\Temp\\.  
  
> [!NOTE]
>  Belirli bir konuma yazmak için bu konuma yazma izniniz olması gerekir; Aksi takdirde hata oluşur. Aklınızda [!INCLUDE[win8_appname_long](../includes/win8_appname_long_md.md)] uygulamaları Masaüstü uygulamaları burada şirketlerin veri yazabilirsiniz ve belirli konumlara yazmak için ek yapılandırma gerektiren hakkında daha fazla kısıtlanmış.  
  
### <a name="capturing-the-graphics-information"></a>Grafik bilgilerini yakalama  
 Uygulamayı programlı yakalama için hazırlanmış ve isteğe bağlı olarak yapılandırdıktan sonra grafik adını ve konumunu günlük dosyası, uygulamanızı oluşturmak ve ardından çalıştırın veya verilerini yakalama için hata ayıklama; Grafik tanılama başlatmayın [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] programlı yakalama API kullandığınızda. Grafik günlüğüne belirttiğiniz konuma kaydedilir. Bu sürüm günlük tutmak istiyorsanız, bu, başka bir konuma başına taşıyın; Uygulama yeniden çalıştırdığınızda, aksi takdirde, üzerine yazılacak.  
  
> [!TIP]
>  Programlı yakalama kullanırken, hala grafik bilgilerini el ile yakalayabilirsiniz — odakta uygulamayla yalnızca basın **Print Screen**. API programlı yakalama tarafından sayılmaz ek grafik bilgilerini yakalama için bu yöntemi kullanabilirsiniz.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuz, grafik bilgilerini programla yakalama gösterilmektedir. Sonraki adım olarak, bu seçenek göz önünde bulundurun:  
  
-   Grafik tanılama araçlarını kullanarak yakalanan grafik bilgilerini çözümlemeyi öğrenin. Bkz: [genel bakış](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Grafik bilgilerini yakalama](walkthrough-capturing-graphics-information.md)   
 [Grafik bilgilerini yakalama](capturing-graphics-information.md)   
 [Komut satırı Yakalama aracı](command-line-capture-tool.md)