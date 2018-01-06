---
title: Olaylar (VSPerfCmd) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3cfbeaa9c11bdb24b561e0dfdc10e8ab2a10053a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="events-vsperfcmd"></a>Olaylar (VSPerfCmd)
VSPerfCmd.exe **olayları** seçeneği olay Windows için izleme (ETW) günlüğe kaydedilmesini denetler. ETW verilerini Profil Oluşturucu veri dosyasından ayrı bir .etl dosyasına kaydedilir. Verileri kullanarak bir rapor görüntülenebilir [VSPerfReport](../profiling/vsperfreport.md) /summary:etw komutu.  
  
 **Olayları** seçeneği VSPerfCmd önce herhangi bir zamanda çağrılabilir **kapatma** komutu profil oluşturmayı durdurmak için çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]  
```  
  
#### <a name="parameters"></a>Parametreler  
 **Üzerinde**&#124; **Kapalı**  
 Başlatır veya olay veri toplamayı durdurur.  
  
 `Guid`  
 Sağlayıcı denetim GUID.  
  
 `ProviderName`  
 Windows Yönetim Araçları (WMI) kayıtlı sağlayıcısının adı.  
  
 `Flags`  
 "0 x"-Olay sağlayıcısı tarafından tanımlanan onaltılık flags değeri öneki.  
  
 `Level`  
 Toplanan veri miktarını belirtir. `Level`Olay sağlayıcısı tarafından tanımlanır.  
  
 **Olayları** seçeneği anlar sağlayıcı adları olarak aşağıdaki çekirdek anahtar sözcükler:  
  
 **İşlem**  
 İşlem olayları  
  
 **İş parçacığı**  
 İş parçacığı olayları  
  
 **Görüntü**  
 Yük görüntü ve olayları kaldırma  
  
 **Disk**  
 Disk g/ç olayları  
  
 **Dosya**  
 Dosya g/ç olayları  
  
 **Hardfault**  
 Sabit sayfa hataları  
  
 **Pagefault**  
 Esnek sayfa hataları  
  
 **Ağ**  
 Ağ olayları  
  
 **Kayıt defteri**  
 Kayıt defteri erişimi olayları  
  
 Çekirdek sağlayıcısı yalnızca etkin olduğunu unutmayın. Devre dışı bırakılamaz veya İzleyici kapatılana kadar bayraklarının değiştirilebilir.  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  CLR ETW olayları etkin olduğunda, ek başlangıç verileri de izleme görünümü raporda toplanır. Raporda görünmesini başlangıç olayları dışlamak için aşağıdaki komutu kullanın:  
  
```  
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5  
```  
  
> [!IMPORTANT]
>  Başlangıç olayları bırakmazsanız bu olaylar Yönetilen Nesne Biçimi (MOF) dosyasında listelenmeyen çünkü sonra GUID raporda görünürler. Daha fazla bilgi için Microsoft Web sitesinde bu sayfaya bakın: [örnek Yönetilen Nesne Biçimi (MOF) dosyasını](http://go.microsoft.com/fwlink/?linkid=37118).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)