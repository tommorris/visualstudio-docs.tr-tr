---
title: Olaylar (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 352feacc59a129d24575408776e9ec075b1294ac
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="events-vsperfcmd"></a>Olaylar (VSPerfCmd)
VSPerfCmd.exe **olayları** seçeneği olay Windows için izleme (ETW) günlüğe kaydedilmesini denetler. ETW verilerini Profil Oluşturucu veri dosyasından ayrı bir .etl dosyasına kaydedilir. Verileri kullanarak bir rapor görüntülenebilir [VSPerfReport](../profiling/vsperfreport.md) /summary:etw komutu.  
  
 **Olayları** seçeneği VSPerfCmd önce herhangi bir zamanda çağrılabilir **kapatma** komutu profil oluşturmayı durdurmak için çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cmd  
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]  
```  
  
#### <a name="parameters"></a>Parametreler  
 **Üzerinde**&#124;**devre dışı**  
 Başlatır veya olay veri toplamayı durdurur.  
  
 `Guid`  
 Sağlayıcı denetim GUID.  
  
 `ProviderName`  
 Windows Yönetim Araçları (WMI) kayıtlı sağlayıcısının adı.  
  
 `Flags`  
 "0 x"-Olay sağlayıcısı tarafından tanımlanan onaltılık flags değeri öneki.  
  
 `Level`  
 Toplanan veri miktarını belirtir. `Level` Olay sağlayıcısı tarafından tanımlanır.  
  
 **Olayları** seçeneği anlar sağlayıcı adları olarak aşağıdaki çekirdek anahtar sözcükler:  
  
 **İşlem**  
 İşlem olayları  
  
 **İş parçacığı**  
 İş parçacığı olayları  
  
 **Görüntü**  
 Yük görüntü ve olayları kaldırma  
  
 **disk**  
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
  
```cmd  
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5  
```  
  
> [!IMPORTANT]
>  Başlangıç olayları bırakmazsanız bu olaylar Yönetilen Nesne Biçimi (MOF) dosyasında listelenmeyen çünkü sonra GUID raporda görünürler. Daha fazla bilgi için Microsoft Web sitesinde bu sayfaya bakın: [örnek Yönetilen Nesne Biçimi (MOF) dosyasını](http://go.microsoft.com/fwlink/?linkid=37118).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)