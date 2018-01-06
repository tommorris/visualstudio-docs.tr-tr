---
title: "Sayaç | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa4b4cdb-e6ea-433a-9579-56f3785e1385
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5974c2f5a1acccebfb9385b91eface6fdc7ba278
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="counter"></a>Sayaç
**Sayaç** seçeneği verileri işlemci (Donanım) performans sayaçlarını toplar.  
  
-   Örnekleme profili oluşturma yöntemi, kullanırken **sayaç** yongadaki performans sayacı ve örnekleme aralığı kullanmak için sayacı olaylarını sayısını belirtir. Örnekleme kullanırken, yalnızca bir sayaç belirtebilirsiniz.  
  
-   İzleme profili oluşturma yöntemi kullanırken, geçerli ve önceki koleksiyon olaylar arasındaki süreyi oluştu sayacı olay sayısı profil oluşturucu raporları ayrı alanlar olarak listelenir. Birden çok **sayaç** araçları kullanılırken seçenekleri belirtilebilir.  
  
 Her işlemci türü donanım performans sayaçları kendi kümesi vardır. Profil Oluşturucu neredeyse tüm işlemciler için ortak olan genel performans sayaçları kümesini tanımlar. Bilgisayarınızda genel ve işlemci özgü sayaçları listelemek için VSPerfCmd kullanın **QueryCounters** komutu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach PID} /Counter:Name[,Reload[,FriendlyName]][Options]  
```  
  
```  
VSPerfCmd.exe /Start:Method /Counter:Name[,Reload[,FriendlyName]][/Counter:Name[,Reload[,FriendlyName]]][Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Name`  
 Sayaç adı. VSPerfCmd.exe kullanmak **/QueryCounters** bilgisayardaki kullanılabilir sayaçlar adlarını listelemek için seçeneği.  
  
 `Reload`  
 Sayaç olaylarını örnekleme aralığı sayısı. İzleme yöntemi ile kullanmayın.  
  
 `FriendlyName`  
 (İsteğe bağlı) Yerine kullanılacak dizesi `Name` profil oluşturucu raporları ve görünümlerin sütun üst bilgileri.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 Sayaç seçeneği, yalnızca aşağıdaki seçeneklerden biriyle kullanılabilir:  
  
 **Başlangıç:**`Trace`  
 Profil Oluşturucu izleme yöntemini kullanmak için başlatır.  
  
 **Başlatma:**`AppName`  
 Belirtilen uygulama ve profil oluşturucu başlatır. Profil Oluşturucu örnekleme yöntemini kullanmak için başlatılmalıdır.  
  
 **Ekle:**`PID`  
 Profil Oluşturucu başlatır ve işlem kimliği tarafından belirtilen işlem ekler Profil Oluşturucu örnekleme yöntemini kullanmak için başlatılmalıdır.  
  
## <a name="example"></a>Örnek  
 Örnekleme yöntemi örneği 1000 her oluşumu uygulama NonHaltedCycles genel profil oluşturucu sayacın örnek gösterilmiştir.  
  
 İzleme yöntemi örneği L2InstructionFetches sayacı olaylarını toplamak için profil oluşturucu başlatma gösterilmiştir. L2InstructionFetches sayaç adı işlemciyi özeldir.  
  
```  
; Sample Method Example  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Counter:NonHaltedCycles,1000,"Non-Halted Cycles"  
  
;INSTRUMENTATION METHOD EXAMPLE  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /Counter:L2InstructionFetches,,"L2 Cache Instruction Fetches"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)