---
title: Bağımsız değişken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 20c35949-1f29-4282-ac75-4e6c237d71bc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d8e9130609c9e16e16b572edfdfa34d758f2eaa2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="args"></a>Bağımsız Değişkenler
VSPerfCmd.exe **Args** seçeneği belirtir hedef uygulama için geçirilen bağımsız değişken listesini **başlatma** alt komutu.  
  
 **Bağımsız değişken** yalnızca ne zaman kullanılabilir **başlatma** komut satırında da belirtilmiş. **Bağımsız değişken** isteğe bağlı olduğunda **başlatma** belirtilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Launch:AppName /Args:Arguments [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Arguments`  
 Bağımsız değişkenleri hedef uygulamaya listesini **başlatma** komutu.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **Başlat:** `AppName`  
 Belirtilen uygulamayı başlatır ve profil oluşturma örnekleme yöntemi ile başlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır **Args** bağımsız değişkenler için TestApp.exe geçirmek için seçeneği.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Args:"123, 'Hello World'"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)