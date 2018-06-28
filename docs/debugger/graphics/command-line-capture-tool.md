---
title: Komut satırı Yakalama aracı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: db75b3a7-80b2-4a74-91d2-fd6e0f73b45d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2424fdcb36e9157c358ab510849a4dbb709d7e62
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057706"
---
# <a name="command-line-capture-tool"></a>Komut Satırı Yakalama Aracı
DXCap.exe bir grafik tanılama yakalama ve kayıttan yürütme için komut satırı aracıdır. Bu Direct3D 10 ile Direct3D 12 arasında tüm özellik düzeylerini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cmd  
DXCap.exe [-file filename] [-frame frames | -period periods | -manual] -c app [args...]  
DXCap.exe -p [filename] [-debug | -warp | -hw] [-config] [-rawmode]  
DXCap.exe -p [filename] -screenshot [-frame frames]  
DXCap.exe -p [filename] -toXML [xml_filename]  
DXCap.exe -v [-file filename] [-examine events] [-haltonfail | -exitonfail] [-showprogress]  
DXCap.exe -e [search_string]  
DXCap.exe -info  
```  
  
#### <a name="parameters"></a>Parametreler  
 `-file``filename`  
 Yakalama modu altında (`-c`), `filename` grafik bilgilerini için kaydedilen grafik günlük dosyasının adını belirtir. Varsa `filename` belirtilmezse, grafik bilgilerini adlı bir dosyaya kaydedilir `<appname>-<date>-<time>.vsglog` varsayılan olarak.  
  
 Doğrulama altında (-v) modunda `filename` doğrulanacak grafik günlük dosyasının adını belirtir. Varsa `filename` belirtilmezse, son doğrulandığı grafik günlük yeniden kullanılır.  
  
 `-frame``frames`  
 Yakalama modu altında `frames` yakalamak istediğiniz çerçeveleri belirtir. İlk kare 1'dir. Virgül ve aralıkları kullanarak birden çok çerçeve belirtebilirsiniz. Örneğin, varsa `frames` olan `2, 5, 7-9, 15`, ardından çerçeve `2`, `5`, `7`, `8`, `9`, ve `15` yakalanır.  

> [!TIP]
> Kullanım `-frame` `manual` çerçeveler el ile Print Screen tuşuna basarak yakalanmasını belirtmek için. Uygulama başlatıldığında çerçeveler yakalanabilir; Çerçeve Yakalamayı durdurmak için komut satırı arabirimini dönün ve ENTER tuşuna basın.  
  
 `-period``periods`  
 Yakalama modu altında `periods` zaman aralıklarına sırasında istediğiniz çerçeveleri yakalamak saniye olarak belirtir. Virgül ve aralıkları kullanarak birden çok nokta belirtebilirsiniz. Örneğin, `periods` olan `2.1-5, 7.0-9.3`, sonra arasında çizilir çerçeveler `2.1` ve `5` saniye arasındaki`7` ve `9.3` saniye yakalanır.  
  
 `-c` `app` [`args...`]  
 Yakalama modu. Yakalama modu altında `app` grafik bilgilerini; yakalamak istediğiniz uygulamanın adını belirtir. `args...` bu uygulama için ek komut satırı parametreleri belirtir.  
  
 `-p` [`filename`]  
 Kayıttan yürütme modu (`-p`). Kayıttan yürütme modu altında `filename` tekrarlanmasını grafik günlük dosyasının adını belirtir. Varsa `filename` belirtilmezse, en son geri yürütülmüş grafik günlük yeniden kullanılır.  
  
 `-debug`  
 Kayıttan yürütme modu altında `-debug` Bu kayıttan yürütme etkin Direct3D hata ayıklama katmanla gerçekleştirilmelidir belirtir.  
  
 `-warp`  
 Kayıttan yürütme modu altında `-warp` Bu kayıttan yürütme TÜNELİ yazılım oluşturucu kullanılarak gerçekleştirilmelidir belirtir.  
  
 `-hw`  
 Kayıttan yürütme modu altında `-hw` GPU donanım kullanarak bu kayıttan yürütme gerçekleştirilmelidir belirtir.  
  
 `-config`  
 Kayıttan yürütme modu altında `-config` bu bilgileri günlüğe kaydettiyseniz, grafik günlük dosyası yakalamak için kullanılan makine hakkındaki bilgileri görüntüler.  
  
 `-rawmode`  
 Kayıttan yürütme modu altında `-rawmode` Bu kayıttan yürütme, kaydedilen olaylara yapmadan gerçekleştirilmelidir belirtir. Normal işlemlerde hata ayıklama basitleştirmek ve kayıttan yürütme hızlandırmak için kayıttan yürütme için kayıttan yürütme modu, küçük değişiklikler yapabilir. Örneğin, bunu takas zinciri komutları yürütülürken yerine takas zinciri çıkış benzetimini. Genelde bu bir sorun değildir ancak kaydedilen olaylara görünümünün daha aslına sadık şekilde gerçekleşmesi için kayıttan yürütme gerekebilir; Örneğin, tam ekran modunda çalışırken yakalanan bir uygulama için tam ekran işleme davranışını geri yüklemek için bu seçeneği kullanın.  
  
 `-toXML` [`xml_filename`]  
 Kayıttan yürütme modu altında `xml_filename` için bir XML temsili kayıttan yürütme yazıldığı dosya adını belirtir. Varsa `xml_filename` belirtilmezse, XML gösterimi, adlı bir dosyaya yazılır, dosya ile aynı çalınma, ancak verilen bir `.xml` uzantısı.  
  
 `-v`  
 Doğrulama modu. Doğrulama modu altında yakalanan çerçeveleri geri hem donanım hem de TÜNELİ oynatılır ve sonuçları bir görüntü karşılaştırma işlevini kullanarak karşılaştırılır. Hızlı bir şekilde, işlemeyi etkileyen sürücü sorunları tanımlamak için bu özelliği kullanın.  
  
 `-examine``events`  
 Doğrulama modu altında `events` hemen sonuçlarını karşılaştırılır grafik olay kümesini belirtir. Örneğin, `-examine present,draw,copy,clear` yalnızca bu kategorilere ait olayları karşılaştırma sınırlar.  
  
> [!TIP]
>  İle başlayan öneririz `-examine present,draw,copy,clear` çünkü bu çoğu sorunları ortaya ancak olaylar daha kapsamlı bir dizi önemli ölçüde daha az uzun. Gerekirse, bu olayları doğrulamak ve diğer tür sorunları ortaya olayları daha büyük ya da farklı bir dizi belirtebilirsiniz.  
  
 `-haltonfail`  
 Doğrulama modu altında `-haltonfail` TÜNELİ oluşturucuyu ve donanım farklar algılandığında doğrulama durur. Bir anahtar basıldıktan sonra doğrulama sürdürür.  
  
 `-exitonfail`  
 Doğrulama modu altında `-exitonfail` TÜNELİ oluşturucuyu ve donanım farklar zaman algılanan hemen doğrulama çıkar. Program bu yolla çıktığında döndürür `0` ortamı; Aksi halde döner `1`.  
  
 `-showprogress`  
 Doğrulama modu altında `-showprogress` doğrulama oturum ilerleme durumu bilgilerini görüntüler. Sol tarafta TÜNELİ ilerlemesi görüntülenir; Donanım ilerleme sağ tarafta görüntülenir.  
  
 `-e``search_string`  
 Yüklü olan UWP uygulamaları numaralandırır. Komut satırı yakalamaları UWP uygulamaları ile gerçekleştirmek için bu bilgileri kullanın.  
  
 `-info`  
 Makine ve yakalama DLL'leri hakkındaki bilgileri görüntüler.  
  
## <a name="remarks"></a>Açıklamalar  
 DXCap.exe üç modda çalışır:  
  
 Yakalama modu (-c)  
 Çalışan bir uygulamanın grafik bilgilerini yakalama ve grafik günlük dosyasına kaydedin. Yakalama yetenekleri ve dosya biçimi bu Visual Studio için aynıdır.  
  
 Kayıttan yürütme modu (-p)  
 Varolan bir grafik günlük dosyasını daha önce yakalanan grafik olaylarından oynatılır. Grafik bile oturum açtığınızda varsayılan olarak, bir pencerede kayıttan yürütme oluşur dosya tam ekran uygulamadan yakalanan. Kayıttan yürütme grafikleri oturum açtığınızda dosya tam ekran uygulamadan yakalanan yalnızca tam ekran olarak ortaya çıkar ve `-rawmode` belirtilir.  
  
 Doğrulama modunu (`-v`)  
 Hem donanım hem de TÜNELİ yakalanan çerçeveleri kayıttan yürütme, ardından bir görüntü karşılaştırma işlevini kullanarak sonuçları karşılaştırma işleme davranışını doğrular. Hızlı bir şekilde, işlemeyi etkileyen sürücü sorunları tanımlamak için bu özelliği kullanın.  
  
 Bu modların yanı sıra dxcap.exe yakalama veya grafik bilgilerini çalınmasını gerçekleştirmeyin iki diğer işlevleri gerçekleştirir.  
  
 Numaralandırma işlevi (`-e`)  
 Makinede yüklü UWP uygulamaları ayrıntılarını görüntüler. Bu ayrıntılar paket adı ve bir UWP uygulaması yürütülebilir dosyada tanımlamak AppID ekleyin. DXCap.exe kullanarak bir windows mağazası uygulamasından grafik bilgilerini yakalama için bir masaüstü uygulamasının yakaladığınızda, kullanılan yürütülebilir dosya adı yerine AppID ve paket adı kullanın.  
  
 Bilgi işlevi)`-info)`  
 Makine ve yakalama DLL'leri hakkındaki ayrıntıları görüntüler.  
  
## <a name="examples"></a>Örnekler  
  
### <a name="capture-graphics-information-from-a-desktop-app"></a>Bir masaüstü uygulamasının grafik bilgilerini yakalama  
 Kullanım `-c` grafik bilgilerini yakalama istediğiniz uygulamayı belirtmek için.  
  
```ms-dos  
DXCap.exe -c BasicHLSL11.exe  
```  
  
 Varsayılan olarak, grafik bilgilerini adlı bir dosyaya kaydedilir `<appname>-<date>-<time>.vsglog`. Kullanım `-file` için kaydetmek için farklı bir dosya belirtmek için.  
  
```ms-dos  
DXCap.exe -file regression_test_12.vsglog -c BasicHLSL11.exe  
```  
  
 Öğesinden sonra uygulamanın filename dahil ederek yakalama uygulama için ek komut satırı parametreleri belirtin.  
  
```ms-dos  
DXCap.exe -c "C:\Program Files\Internet Explorer\iexplorer.exe" "www.fishgl.com"  
```  
  
 Yukarıdaki örnekte komut, 3-b içeriğini işlemek için WebGL API kullanan www.fishgl.com bulunan Web sayfası görüntülerken Internet Explorer'ın Masaüstü sürümünü grafik bilgilerini yakalar.  
  
> [!NOTE]
>  Uygulama sonra görünen komut satırı bağımsız değişkenleri için geçirildiğinden, kullanmadan önce DXCap.exe için hedeflenen bağımsız değişkenleri belirtmeniz gerekir `-c` seçeneği.  
  
### <a name="capture-graphics-information-from-a-uwp-app"></a>Bir UWP uygulaması grafik bilgilerini yakalama.  
 Bir UWP uygulaması grafik bilgilerinden yakalayabilirsiniz.  
  
```ms-dos  
DXCap.exe -c Microsof.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe,AppexMaps  
```  
  
 Bir UWP uygulamasını yakalamak için DXCap.exe kullanarak bir Windows Masaüstü uygulamadan yakalamak için kullanmaya benzer ancak bunun yerine bir masaüstü uygulamasının adından tanımlama, paket adı ve adına göre bir UWP uygulaması tanımlamak veya sizin paketini yürütülebilir iç Kimliğini istediğiniz  yakalamak. Makinenize yüklü UWP uygulamaları belirlemek nasıl bulmayı kolaylaştırmak için kullanın `-e` DXCap.exe seçeneğiyle bunları numaralandırmak için:  
  
```ms-dos  
DXCap.exe -e  
```  
  
 Aradığınız uygulama bulmak için bir isteğe bağlı arama dizesi sağlayabilirsiniz. Arama dizesini sağlandığında DXCap.exe, paket adı, uygulama adı veya uygulama kimlikleri arama dizesiyle eşleşen UWP uygulamaları numaralandırır. Arama büyük/küçük harf duyarlıdır.  
  
```ms-dos  
DXCap.exe -e map  
```  
  
 Yukarıdaki komut "harita"; eşleşen UWP uygulamaları sıralar çıktısı şöyledir:  
  
 **"Microsoft.BingMaps" paketi:**  
 **InstallDirectory: C:\Program Files\WindowsApps\Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe**  
 **FullName: Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe**  
 **UserSID: S-1-5-21-2127521184-1604012920-1887927527-5603533**  
 **Ad: Microsoft.BingMaps**  
 **Yayımcı: CN = Microsoft Corporation, O = Microsoft Corporation, L = Redmond, S = Washington, C = US =**  
 **Sürüm: 2.1.2914.1734**  
 **Launchable uygulamalar:**  
 **Kimliği: AppexMaps**  
 **Exe  : C:\Program Files\WindowsApps\Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe\Map.exe**  
 **IsWWA: Hayır**  
 ** (Başlatmak için) AppSpec: **DXCap.exe - c Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe,AppexMaps*** çıktı numaralandırılmış her uygulama için son satırının görüntüler grafik bilgilerinden yakalamak için kullanabileceğiniz komutu.  
  
### <a name="capture-specific-frames-or-frames-between-specific-times"></a>Belirli çerçeveleri veya belirli zamanları arasında çerçeveler yakalayın.  
 Kullanım `-frame` aralıkları ve virgül kullanarak yakalamak istediğiniz çerçeveleri belirlemek için:  
  
```ms-dos  
DXCap.exe -frame 2,5,7-9,15 -c SimpleBezier11.exe  
```  
  
 Veya kullanmak `-period` çerçeveleri yakalamak için sırasında zaman aralıkları kümesini belirtmek için. Zaman aralıkları saniye cinsinden belirtilir ve birden çok aralık belirtilebilir:  
  
```ms-dos  
DXCap.exe -period 2.1-5, 7.0-9.3 -c SimpleBezier11.exe  
```  
  
### <a name="capture-frames-interactively"></a>Çerçeve etkileşimli olarak yakalayın.  
 Kullanım `-manual` çerçeveleri etkileşimli olarak yakalamak için. Yakalama başlatmak için Enter tuşuna basın ve yeniden durdurmak için Enter tuşuna basın.  
  
```ms-dos  
DXCap.exe -manual -c SimpleBezier11.exe  
```  
  
### <a name="play-back-a-graphics-log-file"></a>Grafik günlük dosyası kayıttan  
 Kullanım `-p` daha önce yakalanan grafik günlük dosyasını oynatmak için.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog  
```  
  
 En son yakalanan grafik günlük kayıttan filename bırakın.  
  
```ms-dos  
DXCap.exe -p  
```  
  
### <a name="play-back-in-raw-mode"></a>Ham modunda kayıttan  
 Kullanım `-rawmode` tam olarak oluşma gibi yakalanan komutları çalabilirsiniz. Normal kayıttan yürütme altında bazı komutlar Öykünülen, örneğin, bir tam ekran uygulamadan yakalanan bir grafik günlük dosyası bir pencerede geri oynayacağı; raw modu etkin olan, aynı dosyanın tam ekran modunda kayıttan dener.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -rawmode  
```  
  
### <a name="play-back-using-warp-or-a-hardware-device"></a>Geri TÜNELİ ya da bir donanım aygıtı kullanarak Yürüt  
 Zorlamak isteyebilirsiniz TÜNELİ kullanmak için bir donanım aygıtında yakalanan bir grafik günlük dosyası arkasına yürütmek ya da bir donanım cihazı kullanın TÜNELİ yakalanan bir günlük çalınmasını zorla. Kullanım `-warp` TÜNELİ kullanarak yeniden yürütülecek.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -warp  
```  
  
 Kullanım `-hw` donanım kullanarak yeniden yürütülecek.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -hw  
```  
  
### <a name="validate-a-graphics-log-file-against-warp"></a>Grafik günlük dosyası TÜNELİ karşı doğrula  
 Doğrulama modu altında grafik günlük dosyası hem donanım hem de TÜNELİ geri çalınır ve sonuçları karşılaştırılır. Bu sürücü tarafından nedeniyle işleme hataları belirlemenize yardımcı olabilir. -V grafik donanım TÜNELİ karşı doğru davranışını doğrulamak için kullanın.  
  
```ms-dos  
DXCap.exe -v regression_test_12.vsglog  
```  
  
 Karşılaştırmaları miktarını azaltmak için karşılaştırmak doğrulama için komutları kümesini belirtebilirsiniz ve diğer komutları yoksayılır. Kullanın - sonuçları karşılaştırmak istediğiniz komutları belirtmek için inceleyin.  
  
```ms-dos  
DXCap.exe -v regression_test_12.vsglog -examine present,draw,copy,clear  
```  
  
### <a name="convert-a-graphics-log-file-to-pngs"></a>Bir grafik günlük dosyası için PNG'ler Dönüştür  
 Görüntülemek veya bir grafik günlük dosyasından çerçeveler çözümlemek için DXCap.exe yakalanan çerçeveleri .png (Taşınabilir Ağ Grafikleri) görüntü dosyaları kaydedebilirsiniz. Kullanım `-screenshot` için çerçeveleri .png dosyaları olarak çıktısını almak için kayıttan yürütme modu altında yakalanan.  
  
```ms-dos  
DXCap.exe -p BasicHLSL11.vsglog -screenshot  
```  
  
 Kullanım `-frame` ile `-screenshot` çıktısını almak istediğiniz çerçeveleri belirlemek için.  
  
```ms-dos  
DXCap.exe -p BasicHLSL11.vsglog -screenshot -frame 5, 7-9  
```  
  
### <a name="convert-a-graphics-log-file-to-xml"></a>Bir grafik günlük dosyası XML biçimine Dönüştür  
 DXCap.exe işlemek ve FindStr veya XSLT gibi tanıdık araçlar kullanarak grafik günlüklerini çözümlemek için grafik günlük dosyası XML biçimine dönüştürebilirsiniz. Kullanım `-toXML` çalma yerine günlük XML'e dönüştürmek için kayıttan yürütme modu altında yedekleyin.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -toXML  
```  
  
 Varsayılan olarak, XML çıktısı grafik günlük aynı ada sahip bir dosyaya yazılır, ancak bir .xml uzantısına atanmıştır. Yukarıdaki örnekte, XML dosyasını adlandırılacağını **regression_test_12.xml**. XML dosyasını farklı bir ad vermek için bundan sonra belirtin `-toXML`.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -toXML temp.xml  
```  
  
 Sonuç dosyası şuna benzer XML içerir:  
  
```xml  
<Moment value="67"/>  
<Method name="CreateDXGIFactory1" >  
    <Return type="HRESULT" value="S_OK" />  
    <Parameter name="riid" type="IID" value="770AAE78-F26F-4DBA-A829-253C83D1B387" />  
    <Parameter name="ppFactory" type="void" handle="1" isOutput="true" />  
</Method>  
  
<Moment value="167"/>  
<Method name="D3D11CreateDevice" >  
    <Return type="HRESULT" value="S_OK" />  
    <Parameter name="pAdapter" type="IDXGIAdapter" handle="34" />  
    <Parameter name="DriverType" type="D3D_DRIVER_TYPE" value="D3D_DRIVER_TYPE_UNKNOWN" />  
    <Parameter name="Software" type="HMODULE" value="pointer" />  
    <Parameter name="Flags" type="UINT" value="0" />  
    <Parameter name="pFeatureLevels" type="D3D_FEATURE_LEVEL" arrSize="1" >  
        <Element value="D3D_FEATURE_LEVEL_11_0" />  
    </Parameter>  
    <Parameter name="FeatureLevels" type="UINT" value="1" />  
    <Parameter name="SDKVersion" type="UINT" value="7" />  
    <Parameter name="ppDevice" type="ID3D11Device" handle="35" isOutput="true" />  
    <Parameter name="pFeatureLevel" type="D3D_FEATURE_LEVEL" value="D3D_FEATURE_LEVEL_11_0" isOutput="true" />  
    <Parameter name="ppImmediateContext" type="ID3D11DeviceContext" value="nullptr" isOutput="true" />  
</Method>  
```  
  
## <a name="requirements"></a>Gereksinimler