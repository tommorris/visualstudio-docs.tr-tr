---
title: VSPerf | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b5854e62-279e-4850-bfeb-0c6ef82f4805
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fcac1e902ccc1fcc5432a231c5f34629422815fd
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34477398"
---
# <a name="vsperf"></a>VSPerf
Kullanım **VsPerf** komut satırı aracı:  
  
1.  Visual Studio cihazda yüklü değilken UWP uygulamaları komut satırından profil.  
  
2.  Masaüstü uygulamaları Windows 8 ve Windows Server 2012 uygulamaları örnekleme profili oluşturma yöntemi kullanarak profil.  
  
 Profil oluşturma seçenekleriniz hakkında daha fazla bilgi için bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="uwp-apps-only"></a>Yalnızca UWP uygulamaları  
 Bu seçenekler yalnızca UWP uygulamalar için geçerlidir.  
  
|||  
|-|-|  
|**/App: {AppName}**|Profil Oluşturucu başlatır ve belirtilen uygulamanın Başlat menüsünden başlatılması için bekler.<br /><br /> Çalıştırma `vsperf /listapps` PackageFullName yüklü uygulamalar ve uygulama adı görüntülemek için.|  
|**/ paketini: {PackageFullName}**|Profil Oluşturucu başlatır ve belirtilen uygulamanın Başlat menüsünden başlatılması için bekler.<br /><br /> Çalıştırma `vsperf /listapps` PackageFullName yüklü uygulamalar ve uygulama adı görüntülemek için.|  
|**/js**|Profil oluşturma JavaScript uygulamaları için gereklidir.<br /><br /> JavaScript uygulamalardan performans verilerini topla.<br /><br /> Yalnızca /package ile kullanım veya / ekleyin.|  
|**/noclr**|İsteğe bağlı. CLR veri toplamaz.<br /><br /> Yalnızca /package ile kullanım veya / ekleyin.<br /><br /> En iyi duruma getirme, yönetilen simge çözer.|  
|**/listapps**|Uygulama adları ve PackageFullNames yüklü listele.|  
  
## <a name="windows-8-desktop-applications-and-windows-server-2012-applications-only"></a>Windows 8 Masaüstü uygulamaları ve yalnızca Windows Server 2012 uygulamaları  
 Bu seçenekler, UWP uygulamaları çalışmaz.  
  
|||  
|-|-|  
|**/ başlatın: {yürütülebilir}**|Başlatır ve belirtilen yürütülebilir dosya profil başlar.|  
|**/args: {ExecutableArguments}**|Geçirilecek komut satırı bağımsız değişkenlerini belirtir **/başlatma** hedef.|  
|**/ Console**|Çalıştırır **/başlatma** yeni bir komut penceresinde hedef.|  
  
## <a name="all-applications"></a>Tüm uygulamalar  
 Bu seçenek, herhangi bir Windows 8 veya Windows Server 2012 uygulama için geçerlidir.  
  
|||  
|-|-|  
|**/ bağlayın: {PID&#124;işlemadı} [, PID&#124;işlemadı]...**|Belirtilen işlemlerden veri toplar.<br /><br /> İşlem kimliği (PID) görüntülemek ve çalışan uygulamalar adları işlemek için Görev Yöneticisi'ni kullanın.|  
|**/ file:{ReportName}**|İsteğe bağlı. Çıktı dosyası (varolan dosyanın üzerine yazar) belirtir.<br /><br /> Yalnızca /package ile kullanım veya / ekleyin.|  
|**/ Pause**|Duraklatma veri koleksiyonu.|  
|**/Resume**|Veri toplama devam edin.|  
|**/ Stop**|Veri toplama işlemini durdurun ve hedef işlemleri sonlanır.|  
|**/ Ayır**|Veri toplamayı Durdur, ancak çalışmaya devam hedef işlemler sağlar.|  
|**/ Status**|Profil Oluşturucu durumunu gösterir.|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)   
 [Komut satırından profil](../profiling/using-the-profiling-tools-from-the-command-line.md)