---
title: "Başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f81bde5c-3394-4b79-a315-c2f6491689b3
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 95bec41931dbde49b3de4c6ff5250df494646392
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="launch"></a>Başlat
**Başlatma** seçeneği profil oluşturucu örnekleme yöntemini kullanarak başlar ve ayrıca belirtilen uygulamayı başlatır.  
  
 Kullanılacak **başlatma** seçeneğini belirtmeniz gerekir **örnek** yönteminde **Başlat** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Launch:AppName [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `AppName`  
 Başlatmak için uygulamanın adı. Geçerli dizindeki tam ve kısmi yollar desteklenir.  
  
## <a name="valid-options"></a>Geçerli seçenekleri  
 Aşağıdaki VSPerfCmd seçenekleri ile birleştirilebilir **başlatma** tek bir komut satırı seçeneği.  
  
 **Başlangıç:**`Method`  
 Komut satırı Profil Oluşturucu oturumu başlatır ve belirtilen profil oluşturma yöntemini ayarlar.  
  
 **GlobalOn**ve **GlobalOff**  
 Sürdürür (**GlobalOn**) veya duraklatır (**GlobalOff**) profil, ancak profil oluşturma oturumu bitmez.  
  
 **ProcessOn:** `PID` ve **ProcessOff**:`PID`  
 Sürdürür (**ProcessOn**) veya duraklatır (**ProcessOff**) belirtilen işlem için profil oluşturma.  
  
 **TargetCLR**  
 Profil oluşturma oturumu içinde birden fazla sürümü yüklendiğinde, .NET Framework ortak dil çalışma zamanı (CLR) profiline sürümünü belirtir. Varsayılan olarak, ilk yüklenen sürüm profili.  
  
## <a name="exclusive-options"></a>Dışlayan seçenekleri  
 Aşağıdaki seçenekler yalnızca kullanılabilir **başlatma** seçeneği.  
  
 **Konsol**  
 Yeni bir pencerede belirtilen komut satırı uygulamasını başlatır.  
  
 **Bağımsız değişken:**`ArgList`  
 Uygulamaya geçirilecek bağımsız değişkenleri listesini belirtir.  
  
 **LineOff**  
 Satır düzeyi profil oluşturma veri koleksiyonunu devre dışı bırakır.  
  
## <a name="sampling-options"></a>Örnekleme seçenekleri  
 Örnekleme aralığı şunlardan biri belirtilebilir üzerinde **başlatma** komut satırı. Varsayılan örnekleme aralığı 10,000,000 işlemci saat döngüsü ' dir.  
  
 **Zamanlayıcı**[**:**`Cycles`]**PF**[**:**`Events`]**Sys**[**:**`Events`] **Sayaç**[**:**`Name`,`Reload`,`FriendlyName`]**GC**[:**ayırma**&#124; **Ömür**]  
 Örnekleme aralığı türü ve numarası belirtir.  
  
-   **Zamanlayıcı** -Samples her `Cycles` durdurulamaz harici işlemci saat döngüsü. Varsa `Cycles` belirtilmezse, 10,000,000 döngüleri kullanılır.  
  
-   **PF** -Samples her `Events` sayfa hataları. Varsa `Events` belirtilmezse, 10 sayfa hataları.  
  
-   **Sys** -Samples her `Events` çağrıları işletim sistemi. Varsa `Events` belirtilmezse, 10 sistem çağrıları kullanılır.  
  
-   **Sayaç** -Samples her `Reload` CPU performans sayacı tarafından belirtilen sayıda `Name`. İsteğe bağlı olarak, `FriendlyName` profil oluşturucu raporlarında sütun başlığı olarak kullanılacak bir dize belirtebilirsiniz.  
  
-   **GC** -toplar .NET bellek verileri. Varsayılan olarak (**ayırma**), her bellek ayırma etkinlikte toplanan veriler. Zaman **ömrü** parametresi belirtilmişse, veri her atık toplama etkinlikte de toplanır.  
  
## <a name="example"></a>Örnek  
 Bu örnek kullanımını gösteren **başlatma** bir uygulamayı başlatmak için.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)