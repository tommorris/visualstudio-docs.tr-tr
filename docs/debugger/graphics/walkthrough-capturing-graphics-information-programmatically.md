---
title: 'İzlenecek yol: Grafik bilgilerini programla yakalama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 899c5e233a8afb898d7864d388448a186b8ab781
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-capturing-graphics-information-programmatically"></a>İzlenecek Yol: Grafik Bilgilerini Programla Yakalama
Kullanabileceğiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] program aracılığıyla bir Direct3D uygulamasından grafik bilgilerini yakalama için grafik tanılama.  
  
 Programlı yakalama gibi senaryolarda kullanışlıdır:  
  
-   Grafik uygulamanızı swapchain mevcut bir doku zaman işleyen gibi kullandığınızda değil yakalama programlı olarak başlar.  
  
-   Uygulamanız, ne zaman DirectCompute hesaplamalar gerçekleştirmek için kullandığı gibi işleme değil, yakalama programlı olarak başlar.  
  
-   Çağrı `CaptureCurrentFrame`kullandığınızda bir işleme sorun düşündüğünüz ve el ile test yakalamak zordur ancak program aracılığıyla çalışma zamanında uygulama durumu hakkındaki bilgileri kullanarak tahmin.  
  
##  <a name="CaptureDX11_2"></a> Windows 10 programlı yakalama  
 Kılavuzun bu bölümü sağlam yakalama yöntemini kullanan Windows 10'DirectX 11.2 API kullanan uygulamalar programlı yakalama gösterir.
  
 Bu bölümde bu görevlerin nasıl yapılacağını gösterir:  
  
-   Programlı yakalama kullanmak için uygulamanızı hazırlama  
  
-   IDXGraphicsAnalysis arabirimi alma  
  
-   Graf bilgilerini yakalama  
  
> [!NOTE]
>  Programlı yakalama önceki uygulamaları için Visual Studio için Uzak araçları dayanıyordu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Yakalama işlevselliği sağlamak için.
  
### <a name="preparing-your-app-to-use-programmatic-capture"></a>Programlı yakalama kullanmak için uygulamanızı hazırlama  
 Uygulamanızda programlı yakalama kullanmak için gerekli üstbilgileri içermelidir. Bu üstbilgileri Windows 10 SDK'ın bir parçasıdır.  
  
##### <a name="to-include-programmatic-capture-headers"></a>Programlı yakalama üstbilgileri dahil etmek için  
  
-   Bu üstbilgileri IDXGraphicsAnalysis arabirimi burada tanımlayacaksınız kaynak dosyasına ekleyin:  
  
    ```  
    #include <DXGItype.h>  
    #include <dxgi1_2.h>  
    #include <dxgi1_3.h>  
    #include <DXProgrammableCapture.h>  
    ```  
  
    > [!IMPORTANT]
    >  Üstbilgi dosyası vsgcapture.h—which destekler programlı yakalama Windows 8.0 ve öncesi içermez — Windows 10 uygulamalarınızda programlı yakalama gerçekleştirmek için. Bu üst DirectX 11.2 ile uyumlu değil. D3d11_2.h üstbilgisi dahil tamamlandıktan sonra bu dosya bulunur, derleyici bir uyarı verir. Vsgcapture.h d3d11_2.h önce eklediyseniz, uygulama başlatılmaz.  
  
    > [!NOTE]
    >  Varsa Haziran 2010 DirectX SDK makinenize yüklü olduğundan ve projenizin INCLUDE yolu içeren `%DXSDK_DIR%includex86`, INCLUDE yolu sonuna taşıyın. Kitaplık yolu için aynı işlemi yapın.  
  
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
  
     Kontrol ettiğinizden emin olun `HRESULT` tarafından döndürülen [DXGIGetDebugInterface1](https://msdn.microsoft.com/library/windows/desktop/dn457937(v=vs.85).aspx) kullanmadan önce geçerli bir arabirim alırsınız emin olmak için:  
  
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
  
- Grafik bilgilerini yakalama başlatmak için kullanmak `BeginCapture`:  
  
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

- Çağrısından sonra `EndCapture`, grafik nesnesi serbest bırakın. 
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuz, grafik bilgilerini programla yakalama gösterilmektedir. Sonraki adım olarak, bu seçenek göz önünde bulundurun:  
  
-   Grafik tanılama araçlarını kullanarak yakalanan grafik bilgilerini çözümlemeyi öğrenin. Bkz: [genel bakış](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Grafik bilgilerini yakalama](walkthrough-capturing-graphics-information.md)   
 [Grafik bilgilerini yakalama](capturing-graphics-information.md)   
 [Komut satırı Yakalama Aracı](command-line-capture-tool.md)