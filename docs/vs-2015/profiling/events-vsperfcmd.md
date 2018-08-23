---
title: Olaylar (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9d14397da6eae0c85b2549bb2f7e6d48af03c17
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673968"
---
# <a name="events-vsperfcmd"></a>Olaylar (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [olaylar (VSPerfCmd)](https://docs.microsoft.com/visualstudio/profiling/events-vsperfcmd).  
  
VSPerfCmd.exe **olayları** olay izleme için Windows (ETW) günlüğe kaydetme seçeneği denetler. ETW verilerini Profil Oluşturucu veri dosyasından ayrı .etl dosyasına kaydedilir. Bir raporu kullanarak verileri görüntülenebilir [VSPerfReport](../profiling/vsperfreport.md) /summary:etw komutu.  
  
 **Olayları** seçeneği VSPerfCmd önce herhangi bir zamanda çağrılabilir **kapatma** komutu, profil oluşturmayı durdurmak için çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]  
```  
  
#### <a name="parameters"></a>Parametreler  
 **Üzerinde**&#124;**kapalı**  
 Başlatır veya olay veri toplamayı durdurur.  
  
 `Guid`  
 Sağlayıcı denetimden GUİD'si.  
  
 `ProviderName`  
 Kayıtlı Windows Yönetim Araçları (WMI) sağlayıcısının adı.  
  
 `Flags`  
 "0 x"-Olay sağlayıcısı tarafından tanımlanan bayrakları onaltılık değer öneki.  
  
 `Level`  
 Toplanan veri miktarını belirtir. `Level` Olay sağlayıcısı tarafından tanımlanır.  
  
 **Olayları** seçeneği sağlayıcı adları olarak aşağıdaki çekirdek anahtar sözcükleri anlar:  
  
 **İşlem**  
 Olayları işleme  
  
 **iş parçacığı**  
 İş parçacığı olayları  
  
 **Görüntü**  
 Görüntü yükleme ve kaldırma olayları  
  
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
  
 Çekirdek sağlayıcısı yalnızca etkin olduğunu unutmayın. Devre dışı bırakılamaz ya da İzleyici kapatılana dek bayraklarının değiştirilebilir.  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  CLR ETW olaylarını etkin olduğunda, ek başlatma verileri de izleme görünümü raporda toplanır. Başlangıç olayları raporda görünmesini dışarıda bırakmak için aşağıdaki komutu kullanın:  
  
```  
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5  
```  
  
> [!IMPORTANT]
>  Başlangıç olayları dışlamazsanız, çünkü bu olaylar Yönetilen Nesne Biçimi (MOF) dosyasında listelenmeyen ardından GUID'leri raporda görünürler. Daha fazla bilgi için Microsoft Web sitesindeki bu sayfaya bakın: [örnek Yönetilen Nesne Biçimi (MOF) dosyası](http://go.microsoft.com/fwlink/?linkid=37118).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)



