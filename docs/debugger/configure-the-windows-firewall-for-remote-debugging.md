---
title: Uzaktan hata ayıklama için Windows Güvenlik duvarını yapılandırma | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 66e3230a-d195-4473-bbce-8ca198516014
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d9fdd6db229bf1aa6f607e096715ea485ec5c5ce
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="configure-the-windows-firewall-for-remote-debugging"></a>Uzaktan hata ayıklama için Windows Güvenlik duvarını yapılandırma
Bu konu, aşağıdaki işletim sistemlerini çalıştıran bilgisayarlarda uzaktan hata ayıklamayı etkinleştirmek için Güvenlik Duvarı'nı yapılandırmak açıklar:  
  
-   Windows 10  
  
-   Windows 8/8.1  
  
-   Windows 7   
  
-   Windows Server 2012 R2  

-   Windows Server 2012
  
-   Windows Server 2008 R2 
  
 Üzerinde ayıkladığınız ağ güvenlik duvarı tarafından korumalı değilse, bu yapılandırma gerekli değildir. Aksi takdirde, Visual Studio barındıran bilgisayarda ve ayıklanacak uzak bilgisayarda güvenlik duvarı yapılandırması değişiklikleri gerektirir.  
  
 **IPSec** ağınız iletişimin gerektiriyorsa olması IPSec kullanılarak gerçekleştirilen, Visual Studio ana bilgisayarı ve uzak bilgisayara ek bağlantı noktalarını açmanız gerekir.  
  
 **Web sunucusu** uzak bir Web sunucusunun hata ayıklama, uzak bilgisayarda ek bir bağlantı noktası açmanız gerekir. (IIS için 80 numaralı bağlantı noktası açık olması gerekir.)  
  
 Her iki bilgisayar aynı işletim sistemini çalıştırmak sahip olmadığını unutmayın. Örneğin, Visual Studio bilgisayar Windows 10 çalıştırabilir ve uzak bilgisayarda Windows Server 2012 R2 çalıştırabilirsiniz.      
  
## <a name="ports-on-the-remote-computer-that-enable-remote-debugging"></a>Uzaktan hata ayıklamayı etkinleştirme bağlantı noktalarını uzak bilgisayarda  
  
|||||  
|-|-|-|-|  
|**Bağlantı Noktaları**|**Gelen ve giden**|**Protokolü**|**Açıklama**|   
|4022|gelen|TCP|VS 2017 için. Bağlantı noktası numarası, her bir Visual Studio sürümü için 2 tarafından artırılır. Daha fazla bilgi için bkz: [Visual Studio uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md).|  
|4023|gelen|TCP|VS 2017 için. Bağlantı noktası numarası, her bir Visual Studio sürümü için 2 tarafından artırılır. (Yalnızca kullanılan uzak hata ayıklama uzaktan hata ayıklayıcı 64-bit sürümünden 32 bitlik bir işlem.) Daha fazla bilgi için bkz: [Visual Studio uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md).| 
|3702|Giden|UDP|(İsteğe bağlı) Uzaktan hata ayıklayıcı bulma için gerekli.|    
  
## <a name="how-to-configure-ports-in-windows-firewall"></a>Windows Güvenlik Duvarı'nda bağlantı noktalarını yapılandırma  

Visual Studio veya uzaktan hata ayıklayıcı yüklediğinizde, yazılım doğru bağlantı noktalarını açmak dener. Ancak, (örneğin, bir üçüncü taraf Güvenlik Duvarı'nı kullanarak) Bazı senaryolarda, bir bağlantı noktası el ile açmanız gerekebilir. Bağlantı noktalarının açık olduğunu doğrulamanız gerekiyorsa, bkz: [sorun giderme](#troubleshooting). Bir bağlantı noktası açmak için bazı yönergeler, Windows'un eski sürümlerinde farklı olabilir.

Bir bağlantı noktasını açmak için:
  
1. Açık **Başlat** menüsü, arama **Gelişmiş Güvenlik Özellikli Windows Güvenlik Duvarı**.

2. Ardından **gelen kuralları > Yeni Kural > bağlantı noktası**ve ardından **sonraki**. (Giden kuralları için seçin **giden kuralları** yerine.)

3. Ya da seçin **TCP** veya **UDP**bağlı olarak bağlantı noktası numarası.

4. Altında **belirli yerel bağlantı noktaları**, bağlantı noktası numarasını girin, tıklatın **sonraki**.

5. Tıklatın **bağlantıya izin** ve ardından **sonraki**.

6. Bağlantı noktası için Etkinleştir'i tıklatın bir veya daha fazla ağ türlerini **sonraki**.

    Seçtiğiniz türü uzak bilgisayarın bağlı olduğu ağ eklemeniz gerekir.
7. Ad ekleyin (örneğin, **msvsmon**, **IIS**, veya **Web dağıtımı**) tıklatın ve kural için **son**.

    Yeni kuralınıza kuralları gelen veya giden kuralları listesinde görmeniz gerekir.

## <a name="troubleshooting"></a>Sorun giderme

Uzaktan hata ayıklayıcı ile uygulamanıza ekleme ile ilgili sorunlar yaşıyorsanız, doğru bağlantı noktalarının açık olduğunu doğrulamak gerekebilir.

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-visual-studio-computer"></a>Bağlantı noktaları Visual Studio bilgisayardaki Windows Güvenlik Duvarı'nda açık olduğundan emin olun  
 Windows Güvenlik Duvarı'nı yapılandırma yönergeleri, farklı işletim sistemleri üzerinde biraz farklılık gösterir. Windows 8/8.1, Windows 10 ve Windows Server 2012, word **uygulama** kullanılır; Windows 7 veya Windows Server 2008, word **program** kullanılır;  Aşağıdaki adımlarda word kullanacağız **uygulama**.  
  
1.  Windows Güvenlik Duvarı sayfasını açın. (İçinde **Başlat** menü arama kutusuna **Windows Güvenlik Duvarı**).  
  
2.  Tıklatın **bir uygulamayı veya özelliği Windows Güvenlik Duvarı aracılığıyla izin**.  
  
3.  İçinde **verilen uygulamalar ve Özellikler** listesinde, Ara **Visual Studio uzaktan hata ayıklayıcı bulma**. Listeleniyorsa, seçili olduğunu ve bir veya daha fazla ağ türü Ayrıca seçili olduğundan emin olun.  
  
4.  Varsa **Visual Studio uzaktan hata ayıklayıcı bulma** olan listelenmeyen tıklatın **başka bir uygulamanın ver**. İçinde hala görmüyorsanız, **bir uygulama ekleyin** penceresinde tıklatın **Gözat** gidin  **\<Visual Studio yükleme dizini > \Common7\IDE\Remotehataayıklayıcı**. (X86, x64, Appx) uygulama için uygun klasörü bulun ve ardından **msvsmon.exe**. Ardından **Ekle**.  
  
5.  İçinde **verilen uygulamalar ve Özellikler** listesinde **Visual Studio uzaktan hata ayıklayıcı**. Bir veya daha fazla ağ türleri kontrol edin (**etki alanı, ev/iş (özel), ortak**) ile iletişim kurmak için uzaktan hata ayıklama İzleyicisi istiyor. Visual Studio bilgisayarın bağlı olduğu ağ türleri eklemeniz gerekir. 

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-remote-computer"></a>Bağlantı noktaları uzak bilgisayarda Windows Güvenlik Duvarı'nda açık olduğundan emin olun  
 Uzaktan hata ayıklama bileşenleri uzak bilgisayarda yüklü veya paylaşılan bir dizinden çalıştırabilirsiniz. Güvenlik Duvarı'nı uzak bilgisayarın her iki durumda da yapılandırılması gerekir. Uzaktan hata ayıklama bileşenler bulunur:  
  
 **\<Visual Studio yükleme dizini > \Common7\IDE\Remote hata ayıklayıcı**  
  
 Windows Güvenlik Duvarı'nı yapılandırma yönergeleri, farklı işletim sistemleri üzerinde biraz farklılık gösterir. Windows 8/8.1, Windows 10 ve Windows Server 2012, word **uygulama** kullanılır; Windows 7 veya Windows Server 2008, word **program** kullanılır;  Aşağıdaki adımlarda word kullanacağız **uygulama**.  
  
1.  Windows Güvenlik Duvarı sayfasını açın. (Üzerinde **Başlat** menü arama kutusuna **Windows Güvenlik Duvarı**.)  
  
2.  Tıklatın **bir uygulamayı veya özelliği Windows Güvenlik Duvarı aracılığıyla izin**.  
  
3.  İçinde **verilen uygulamalar ve Özellikler** listesinde, Ara **Visual Studio uzaktan hata ayıklayıcı**. Listeleniyorsa, seçili olduğunu ve bir veya daha fazla ağ türü Ayrıca seçili olduğundan emin olun.  
  
4.  Varsa **Visual Studio uzaktan hata ayıklayıcı** olan listelenmeyen tıklatın **başka bir uygulamanın ver**. İçinde hala görmüyorsanız, **bir uygulama penceresi ekleyin**, tıklatın **Gözat** gidin  **\<Visual Studio yükleme dizini > \Common7\IDE\Remotehataayıklayıcı**. (X86, x64, Appx) uygulama için uygun klasörü bulun ve ardından **msvsmon.exe**. Ardından **Ekle**.  
  
5.  İçinde **uygulamalara izin** listesinde **Visual Studio uzaktan hata ayıklayıcı**. Bir veya daha fazla ağ türleri kontrol edin (**etki alanı, ev/iş (özel), ortak**) ile iletişim kurmak için uzaktan hata ayıklama İzleyicisi istiyor. Visual Studio bilgisayarın bağlı olduğu ağ türleri eklemeniz gerekir. 

### <a name="managed-or-native-compatibility-mode-open-additional-ports-on-the-remote-computer"></a>(Yönetilen veya özgün uyumluluk modu) Uzak bilgisayarda ek bağlantı noktalarını açın

Hata ayıklayıcı uyumluluk modu kullanıyorsa (**Araçlar > Seçenekler > hata ayıklama**), ek bağlantı noktalarının açılması gerekir. Hata ayıklayıcı eski bir sürümü uyumluluk modu sağlar ve farklı bağlantı noktaları gerekir.

> [!NOTE]
> Hata ayıklayıcı eski sürümünü Visual Studio 2010 Hata Ayıklayıcısı ' dir.
  
|||||  
|-|-|-|-|  
|**Bağlantı Noktaları**|**Gelen ve giden**|**Protokolü**|**Açıklama**|  
|135, 139, 445|Giden|TCP|Gerekli.|  
|137, 138|Giden|UDP|Gerekli.|  
|500, 4500|Giden|UDP|Etki alanı ilkesi ağ iletişimi IPSec gerçekleştirilmesini gerektiriyorsa gereklidir.|  
|80|Giden|TCP|Web sunucusunun hata ayıklama için gereklidir.|
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)