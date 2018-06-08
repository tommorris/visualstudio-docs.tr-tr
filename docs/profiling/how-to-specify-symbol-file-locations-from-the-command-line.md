---
title: 'Nasıl yapılır: simge dosyası konumlarını komut satırından belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 8aa067bb-e8bf-4081-aff0-cfbcf65934a0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d31479ec46c407ca875a1ad2a1d81e1438b7715
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845216"
---
# <a name="how-to-specify-symbol-file-locations-from-the-command-line"></a>Nasıl yapılır: komut satırından simge dosyası konumlarını belirtin
İşlev adları ve satır numaralarını gibi sembol bilgilerini görüntülemek için VSPerfReport komut satırı aracı simgenin erişmesi (. *pdb*) profili bileşenleri ve Windows sistem dosyalarının dosya. Bir bileşenin derlendiğinde simge dosyaları oluşturulur. Daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md). VSPerfReport, otomatik olarak simge dosyaları aşağıdaki konumlarda arar:  
  
-   Belirtilen yol **/SymbolPath** seçeneği veya **_NT_SYMBOL_PATH** ortam değişkeni.  
  
-   Bir bileşen burada derlenen tam yerel yolu.  
  
-   Profil oluşturma verileri içeren dizine (. *Vsp* veya. *vsps*) dosyası.  
  
 Microsoft sağlar. *pdb* birçok ürünlerinde çevrimiçi bir simge Server'daki dosyaları. Raporlama için kullandığınız bilgisayar Internet'e bağlı değilse VSPerfReport otomatik olarak sembol bilgilerini aramak ve yerel depoya dosyaları kaydetmek için çevrimiçi simgesi sunucusuna bağlanır.  
  
 Aşağıdaki yollarla simge dosyaları ve Microsoft simgesi sunucu depolama konumunu belirtebilirsiniz:  
  
-   Ayarlama **_NT_SYMBOL_PATH** ortam değişkeni.  
  
-   Ekleme **/SymbolPath** VSPerfReport komut satırı seçeneği.  
  
 Bu yöntemlerin her ikisi de kullanabilirsiniz.  
  
> [!NOTE]
>  Varsa [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Windows simge dosyaları büyük olasılıkla belirtildiği için zaten bir konum yerel bilgisayara yüklendi. Daha fazla bilgi için bkz: [nasıl yapılır: başvuru Windows sembol bilgileri](../profiling/how-to-reference-windows-symbol-information.md). Hala VSPerfReport konumu ve bu konunun ilerleyen bölümlerinde açıklandığı gibi sunucusu kullanacak şekilde yapılandırmanız gerekir.  
  
## <a name="specify-windows-symbol-files"></a>Windows simge dosyaları belirtin  
  
#### <a name="to-configure-the-use-of-the-windows-symbol-server"></a>Windows Simge sunucusunu kullanımını yapılandırmak için  
  
1.  Gerekirse, simge dosyaları yerel olarak depolamak için bir dizin oluşturun.  
  
2.  Ayarlamak için aşağıdaki sözdizimini kullanın **_NT_SYMBOL_PATH** ortam değişkeni veya VSPerfReport /SymbolPath seçeneği:  
  
     **SRV\***  *LocalStore* **\*http://msdl.microsoft.com/downloads/symbols**  
  
     Burada *LocalStore* oluşturduğunuz yerel dizin yoludur.  
  
## <a name="specify-component-symbol-files"></a>Bileşeni sembol dosyaları belirtin  
 Profil oluşturma araçları arar. *pdb* bileşenleri veya profil oluşturma veri dosyasını içeren klasöre depolanan özgün konumlarına profilinde istediğiniz bileşenleri dosyaları. Bir veya daha fazla yol ekleyerek aramak için diğer konumlar belirtebilirsiniz **_NT_SYMBOL_PATH** veya **/SymbolPath** seçeneği. Ayrı yollar noktalı virgülle ayırın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırı kümeleri **_NT_SYMBOL_PATH** ortam değişkenine Windows Simge sunucusunu ve yerel dizine **C:\Symbols**.  
  
 **ayarlama _NT_SYMBOL_PATH srv =\*C:\symbols\*http://msdl.microsoft.com/downloads/symbols**  
  
 Aşağıdaki VSPerfReport komut satırını ekler *C:\Projects\Symbols* arama yolu kullanarak dizin **/SymbolPath** seçeneği.  
  
 **VSPerfReport***Uygulamam* **.exe /SymbolPath:C:\Projects\Symbols /summary:all**