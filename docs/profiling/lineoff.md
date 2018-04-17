---
title: LineOff | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 76082063-20ef-47ae-ad64-81b43b654865
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 42cceb5c2bc756a976cd1df2a0c74f5313a6df79
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="lineoff"></a>LineOff
Örnekleme profili oluşturma yöntemi kullanırken varsayılan olarak, profil oluşturucu kaynak kodu satır sayısı ve satır numarası uzaklık verilerini toplar. VSPerfCmd **LineOff** seçeneği devre dışı bırakır satır numarası veri toplama VSPerfCmd uygulamayı başlatmak için kullanıldığında. Profil oluşturma verilerini işleve toplanır ne zaman düzey **LineOff** belirtilir.  
  
 Kullanabileceğiniz **LineOff** yalnızca **başlatma** seçeneği ve yalnızca zaman profil oluşturucu örnekleme için kullanarak başlatıldı **Başlat**:**örnek** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Launch:AppName /LineOff [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **LineOff** seçeneği içeren bir komut satırında yalnızca kullanılabilir **başlatma** seçeneği.  
  
 **Başlat:** `AppName`  
 Belirtilen uygulamayı başlatır ve profil oluşturma örnekleme yöntemi ile başlar.  
  
## <a name="example"></a>Örnek  
 Bu örnek uygulama ve profil oluşturucu başlatır ve satır düzeyi örnekleme devre dışı bırakır.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /LineOff  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)