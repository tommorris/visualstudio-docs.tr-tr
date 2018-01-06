---
title: VSPerf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5854e62-279e-4850-bfeb-0c6ef82f4805
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ea6214987e12b8c5cf7e563b666822989d3a7015
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="vsperf"></a>VSPerf
Kullanım **VsPerf** komut satırı aracı:  
  
1.  Visual Studio cihazda yüklü değilken UWP uygulamaları komut satırından profil.  
  
2.  Masaüstü uygulamaları Windows 8 ve Windows Server 2012 uygulamaları örnekleme profili oluşturma yöntemi kullanarak profil.  
  
 Profil oluşturma seçenekleriniz hakkında daha fazla bilgi için bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
##  <a name="BKMK_In_this_topic"></a>Bu konudaki  
 Bu konu ile kullanabileceğiniz seçenekleri açıklar `vsperf.exe` komut satırı aracı. Konu aşağıdaki bölümleri içerir:  
  
 [Yalnızca UWP uygulamaları](#BKMK_windows_store_apps_only)  
  
 [Windows 8 Masaüstü uygulamaları ve yalnızca Windows Server 2012 uygulamaları](#BKMK_Windows_8_classic_applications_and_Windows_Server_2012_applications_only)  
  
 [Tüm uygulamalar](#BKMK_All_applications)  
  
##  <a name="BKMK_windows_store_apps_only"></a>Yalnızca UWP uygulamaları  
 Bu seçenekler yalnızca UWP uygulamalar için geçerlidir.  
  
|||  
|-|-|  
|**/App: {AppName}**|Profil Oluşturucu başlatır ve belirtilen uygulamanın Başlat menüsünden başlatılması için bekler.<br /><br /> Çalıştırma `vsperf /listapps` PackageFullName yüklü uygulamalar ve uygulama adı görüntülemek için.|  
|**/ paketini: {PackageFullName}**|Profil Oluşturucu başlatır ve belirtilen uygulamanın Başlat menüsünden başlatılması için bekler.<br /><br /> Çalıştırma `vsperf /listapps` PackageFullName yüklü uygulamalar ve uygulama adı görüntülemek için.|  
|**/js**|Profil oluşturma JavaScript uygulamaları için gereklidir.<br /><br /> JavaScript uygulamalardan performans verilerini topla.<br /><br /> Yalnızca /package ile kullanım veya / ekleyin.|  
|**/noclr**|İsteğe bağlı. CLR veri toplamaz.<br /><br /> Yalnızca /package ile kullanım veya / ekleyin.<br /><br /> En iyi duruma getirme, yönetilen simge çözer.|  
|**/listapps**|Uygulama adları ve PackageFullNames yüklü listele.|  
  
##  <a name="BKMK_Windows_8_classic_applications_and_Windows_Server_2012_applications_only"></a>Windows 8 Masaüstü uygulamaları ve yalnızca Windows Server 2012 uygulamaları  
 Bu seçenekler, UWP uygulamaları çalışmaz.  
  
|||  
|-|-|  
|**/ başlatın: {yürütülebilir}**|Başlatır ve belirtilen yürütülebilir dosya profil başlar.|  
|**/args: {ExecutableArguments}**|Geçirilecek komut satırı bağımsız değişkenlerini belirtir **/başlatma** hedef.|  
|**/ Console**|Çalıştırır **/başlatma** yeni bir komut penceresinde hedef.|  
  
##  <a name="BKMK_All_applications"></a>Tüm uygulamalar  
 Bu seçenek, herhangi bir Windows 8 veya Windows Server 2012 uygulama için geçerlidir.  
  
|||  
|-|-|  
|**/ bağlayın: {PID &#124; İşlemadı} [, PID &#124; İşlem adı]...**|Belirtilen işlemlerden veri toplar.<br /><br /> İşlem kimliği (PID) görüntülemek ve çalışan uygulamalar adları işlemek için Görev Yöneticisi'ni kullanın.|  
|**/ file:{ReportName}**|İsteğe bağlı. Çıktı dosyası (varolan dosyanın üzerine yazar) belirtir.<br /><br /> Yalnızca /package ile kullanım veya / ekleyin.|  
|**/ Pause**|Duraklatma veri koleksiyonu.|  
|**/Resume**|Veri toplama devam edin.|  
|**/ Stop**|Veri toplama işlemini durdurun ve hedef işlemleri sonlanır.|  
|**/ Ayır**|Veri toplamayı Durdur, ancak çalışmaya devam hedef işlemler sağlar.|  
|**/ Status**|Profil Oluşturucu durumunu gösterir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)   
 [Komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md)