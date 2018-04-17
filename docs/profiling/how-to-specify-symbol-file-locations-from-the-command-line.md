---
title: 'Nasıl yapılır: simge dosyası konumlarını komut satırından belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 8aa067bb-e8bf-4081-aff0-cfbcf65934a0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b62048cdc0bacfc94c855d8397d6be93ba72c524
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-symbol-file-locations-from-the-command-line"></a>Nasıl yapılır: Simge Dosyası Konumlarını Komut Satırından Belirtme
İşlev adları ve satır numaralarını gibi sembol bilgilerini görüntülemek için VSPerfReport komut satırı aracı profili bileşenlerinin simge (.pdb) dosyaları ve Windows sistem dosyalarını erişim gerektirir. Bir bileşenin derlendiğinde simge dosyaları oluşturulur. Daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md). VSPerfReport, otomatik olarak simge dosyaları aşağıdaki konumlarda arar:  
  
-   Belirtilen yol **/SymbolPath** seçeneği veya **_NT_SYMBOL_PATH** ortam değişkeni.  
  
-   Bir bileşen burada derlenen tam yerel yolu.  
  
-   Profil oluşturma veri (.vsp veya .vsps) dosyasını içeren dizini.  
  
 Microsoft birçok ürünlerinde çevrimiçi bir simge Server'daki .pdb dosyaları sağlar. Raporlama için kullandığınız bilgisayar Internet'e bağlı değilse VSPerfReport otomatik olarak sembol bilgilerini aramak ve yerel depoya dosyaları kaydetmek için çevrimiçi simgesi sunucusuna bağlanır.  
  
 Aşağıdaki yollarla simge dosyaları ve Microsoft simgesi sunucu depolama konumunu belirtebilirsiniz:  
  
-   Ayarlama **_NT_SYMBOL_PATH** ortam değişkeni.  
  
-   Ekleme **/SymbolPath** VSPerfReport komut satırı seçeneği.  
  
 Bu yöntemlerin her ikisi de kullanabilirsiniz.  
  
> [!NOTE]
>  Varsa [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Windows simge dosyaları büyük olasılıkla belirtildiği için zaten bir konum yerel bilgisayara yüklendi. Daha fazla bilgi için bkz: [nasıl yapılır: başvuru pencereleri sembol bilgileri](../profiling/how-to-reference-windows-symbol-information.md). Hala VSPerfReport konumu ve bu konunun ilerleyen bölümlerinde açıklandığı gibi sunucusu kullanacak şekilde yapılandırmanız gerekir.  
  
## <a name="specifying-windows-symbol-files"></a>Belirterek Windows simge dosyaları  
  
#### <a name="to-configure-the-use-of-the-windows-symbol-server"></a>Windows Simge sunucusunu kullanımını yapılandırmak için  
  
1.  Gerekirse, simge dosyaları yerel olarak depolamak için bir dizin oluşturun.  
  
2.  Ayarlamak için aşağıdaki sözdizimini kullanın **_NT_SYMBOL_PATH** ortam değişkeni veya VSPerfReport /SymbolPath seçeneği:  
  
     **SRV\***  *LocalStore* **\*http://msdl.microsoft.com/downloads/symbols**  
  
     Burada *LocalStore* oluşturduğunuz yerel dizin yoludur.  
  
## <a name="specifying-component-symbol-files"></a>Bileşeni sembol dosyalarını belirtme  
 Profil oluşturma araçları bileşenleri veya profil oluşturma veri dosyasını içeren klasöre depolanan özgün konumlarına profilinde istediğiniz bileşenleri the.pdb dosyaları arar. Bir veya daha fazla yol ekleyerek aramak için diğer konumlar belirtebilirsiniz **_NT_SYMBOL_PATH** veya **/SymbolPath** seçeneği. Ayrı yollar noktalı virgülle ayırın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırı kümeleri **_NT_SYMBOL_PATH** ortam değişkenine Windows Simge sunucusunu ve yerel dizine **C:\Symbols**.  
  
 **ayarlama _NT_SYMBOL_PATH srv =\*C:\symbols\*http://msdl.microsoft.com/downloads/symbols**  
  
 Aşağıdaki VSPerfReport komut satırını kullanarak C:\Projects\Symbols dizin arama yoluna ekler **/SymbolPath** seçeneği.  
  
 **VSPerfReport***Uygulamam* **.exe /SymbolPath:C:\Projects\Symbols /summary:all** 