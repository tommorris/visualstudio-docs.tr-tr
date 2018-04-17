---
title: VSPerfCmd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, VSPerfCmd tool
- command-line tools, VSPerfCmd tool
- command line, tools
- profiling tools,VSPerfCmd
- VSPerfCmd tool
ms.assetid: 778bc105-7643-46c4-a338-f3620e31125a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c3a90658eedded4afdf3d81cedcb27eb06c93592
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="vsperfcmd"></a>VSPerfCmd
**VSPerfCmd.exe** aracı performans verileri toplama durdurmak ve başlatmak için kullanılır. Aşağıdaki sözdizimini kullanır:  
  
```  
VSPerfCmd [/U] [/options]  
```  
  
 Aşağıdaki tabloda açıklanmaktadır **VSPerfCmd.exe** aracı seçenekleri.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**U**|Yeniden yönlendirilen konsol çıktısı Unicode olarak yazılır. İlk seçeneği belirtilmelidir.|  
|[Başlat](../profiling/start.md) **:** `mode`|Profil oluşturma hizmeti belirtilen modunda başlatır.|  
|[Çıktı](../profiling/output.md) **:** `filename`|Çıktı dosyası adını belirtir. Yalnızca kullanmak **Başlat**.|  
|[CrossSession&#124;CS](../profiling/crosssession.md)|Windows oturumlarında profil etkinleştirir. Yalnızca kullanmak **Başlat**, **Attach**, **veya başlatma**.|  
|[Kullanıcı](../profiling/user-vsperfcmd.md) **:**[`domain\`]`username`|Profil Oluşturucu hizmeti belirtilen hesap erişmesini sağlar. Yalnızca kullanmak **Başlat**.|  
|[WaitStart](../profiling/waitstart.md)[**:**`n`]|Başlatmak veri toplama Günlükçü için bekler. Varsa `n` belirtilirse, **VSPerfCmd** en fazla bekleyeceği `n` saniye. Varsa `n` belirtilmezse, **VSPerfCmd** sonsuza kadar bekler. Bu kullanımını kolaylaştırır **VSPerfCmd** toplu işleminin bir parçası olarak.|  
|[Sayaç](../profiling/counter.md) **:** `cfg`|Profili oluşturma yöntemi örnek kullanıldığında, CPU sayaç ve örnekleme aralığı kullanmak için olayların sayısını belirtir. Yalnızca bir sayaç değeri örnek oluşturabilirsiniz.<br /><br /> İzleme profili oluşturma yöntemi kullanıldığında, her izleme noktada toplanacak CPU sayaç belirtir. Yalnızca kullanmak **Başlat:**`Trace`, **Attach**, veya **başlatma**.|  
|[QueryCounters](../profiling/querycounters.md)|Geçerli makinenin geçerli CPU sayaçları listesini görüntüler.|  
|[WinCounter](../profiling/wincounter.md) **:** *yolu*|Profil işareti verilerle dahil etmek için bir Windows performans sayacı olay belirtir. Yalnızca kullanmak **Başlat**.|  
|[Otomatik işaret](../profiling/automark.md) **:** *n*|Windows performans sayacı verilerini toplama olayları süre (milisaniye cinsinden) belirtir. İle kullandığınız **WinCounter**.|  
|[Olayları](../profiling/events-vsperfcmd.md) **:** `option`|Belirtilen olay Windows için izleme (ETW) olayları koleksiyonu denetler. Profil oluşturma veri (.vsp) dosyası değil bir .itl dosyasına ETW verileri toplanır.|  
|[Status](../profiling/status.md)|Profil Oluşturucu, şu anda profili oluşturuluyor işlemleri ve profil oluşturucu denetim yetkisi olan hesaplar hakkında bilgi durumunu görüntüler.|  
|[Kapatma](../profiling/shutdown.md)[**:**`n`]|Profil oluşturma veri dosyası kapatır ve profil oluşturucu kapatır.|  
|[GlobalOn](../profiling/globalon-and-globaloff.md)|Veri toplama için bir çağrı sonra sürdürür **VSPerfCmdGlobalOff**.|  
|[GlobalOff](../profiling/globalon-and-globaloff.md)|Tüm veri toplamayı durdurur, ancak profil oluşturma oturumu bitmez.|  
|[ProcessOn](../profiling/processon-and-processoff.md) **:** `pid`|Belirtilen işlem için veri toplama için yapılan bir çağrı tarafından profil oluşturma duraklatıldı sonra sürdürür **VSPerfCmdProcessOff**.|  
|[ProcessOff](../profiling/processon-and-processoff.md) **:** `pid`|Belirtilen işlem için veri toplamayı durdurur.|  
|[ThreadOn ve ThreadOff](../profiling/threadon-and-threadoff.md) **:** *komutu*|Sürdürür için yapılan bir çağrı tarafından profil oluşturma duraklatıldı sonra belirtilen işlem için profil oluşturma **VSPerfCmdThreadOff**. Kullanım **ThreadOn** yalnızca profil oluşturma araçları yöntemi ile olduğunda.|  
|[ThreadOn ve ThreadOff](../profiling/threadon-and-threadoff.md) **:** *komutu*|Belirtilen iş parçacığı için profil oluşturma duraklatır. Kullanım **ThreadOff** yalnızca profil oluşturma araçları yöntemi ile olduğunda.|  
|[İşareti](../profiling/mark.md) **:** *MarkNum*[**,***MarkText***]**|Profil oluşturma veri dosyası, isteğe bağlı bir metin işareti ekler.|  
  
## <a name="sampling-method-options"></a>Örnekleme yöntemi seçenekleri  
 Örnekleme profili oluşturma yöntemi kullanırken aşağıdaki seçeneklerden yalnızca kullanılabilir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|[Başlatma](../profiling/launch.md) **:** *çalıştırılabilir*|Belirtilen uygulamayı başlatır ve profil oluşturma başlar.|  
|[Bağımsız değişken](../profiling/args.md) **:** *bağımsız değişkenleri*|Başlatılan uygulamaya geçirilecek komut satırı bağımsız değişkenlerini belirtir.|  
|[Console](../profiling/console.md)|Belirtilen komut yeni bir komut istemi penceresi başlatır.|  
|[Attach](../profiling/attach.md) **:** *PID*[**, *** PID*]|Belirtilen işlemler profil başlar. İşlemler işlem kimliği veya işlem adına göre tanımlanabilir.|  
|[Detach](../profiling/detach.md)[**: *** PID*[,*PID*]]|Profil oluşturma belirtilen işlemleri durdurur. İşlemler işlem kimliği veya işlem adına göre tanımlanabilir. Profil oluşturma hiçbir işlem belirtilmişse, tüm işlemler için durdurulur.|  
|[GC](../profiling/gc-vsperfcmd.md)[**:**{**ayırma**`&#124;`**ömrü**}]|.NET bellek ayırma ve nesne yaşam verisi toplar. Yalnızca kullanmak **VSPerfCmdLaunch** seçeneği.|  
  
### <a name="sampling-interval-options"></a>Örnekleme aralığı seçenekleri  
 Türü ve süresi örnekleme aralıkları, aşağıdaki seçenekleri belirtin. Varsayılan değer **Zamanlayıcı**. Kullanarak aralığı olarak CPU sayaç belirtebilirsiniz **sayaç** seçeneği. Bu seçenekler yalnızca ile belirtilebilir **başlatma** veya ilk ile **Attach** profil oluşturma oturumu.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|[PF](../profiling/pf.md)[**: *** n*]|Her n. sayfa hatası örnekleri (varsayılan = 10).|  
|[Sys](../profiling/sys-vsperfcmd.md)[**: *** n*]|Her n. sistem çağrısı örnekleri (varsayılan = 10).|  
|[Zamanlayıcı](../profiling/timer.md)[**: *** n*]|Her n. işlemci örnekleri döngüsü (varsayılan = 10000000).|  
  
## <a name="service-component-and-kernel-mode-device-options"></a>Hizmet bileşeni ve çekirdek modu aygıt seçenekleri  
 Aşağıdaki yönetim seçenekleri profil hizmet bileşenlerini veya çekirdek modu aygıt sürücülerini destekler. Yönetim seçenekleri profil oluşturma izinlerini ayarlama ve profili hizmeti veya aygıt sürücüsü denetleyebilirsiniz.  
  
 Yönetim seçenekleri, yönetici kimlik bilgileriyle çalışan bir komut isteminde yürütülmelidir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Admin:security** \< **izin&#124;REDDETME**> *sağ*[ *sağ*] \< *kullanıcı*  &#124; *Grubu*>|İzin verir veya belirtilen kullanıcı veya grup erişimi profil oluşturma hizmetleri engeller.<br /><br /> `Right` aşağıdakilerden biri olabilir:<br /><br /> CrossSession - hizmete profil oluşturma oturumu arası için kullanıcı erişimi verir.<br /><br /> SampleProfiling - örnekleme profili oluşturma etkinleştirmek için bir sürücü için kullanıcı erişimi verir. İzleme profili oluşturma sırasında çekirdek geçiş bilgilere erişmek için de kullanılır.<br /><br /> FullAccess - kullanıcı verir CrossSession ve SampleProfiling erişim.|  
|**Admin:Security, liste**|Profil oluşturma hizmetleri geçerli durumunu listeler ve kullanıcı izinleri listeler.|  
|**Yönetici:** \< *hizmet*&#124;*sürücü*>\<**Başlat**&#124;**Durdur**  &#124; **Yükleme**&#124;**Kaldır**>|Başlatır, durdurur, yükler veya profil oluşturma hizmeti bileşeni (hizmeti) veya çekirdek modu aygıt sürücüsü (sürücü) kaldırır.|  
|**Yönetici:** \< *hizmet*&#124;*sürücü*>**AutoStart**\<**üzerinde** &#124; **Kapalı**>|Etkinleştirir veya bir yeniden başlatma sonrasında profil oluşturma hizmeti (hizmeti) veya çekirdek modu aygıt sürücüsü (sürücü) otomatik olarak başlatılmasını devre dışı bırakır.|  
  
## <a name="vsperfcmd-driver"></a>VSPerfCmd Driver  
 **VSPerfCmd Driver** seçeneği kullanılmıyor şimdi. Kullanım **VsPerfCmdAdmin** bu işlev için Seçenekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Vsınstr](../profiling/vsinstr.md)   
 [VSPerfMon](../profiling/vsperfmon.md)   
 [VSPerfReport](../profiling/vsperfreport.md)