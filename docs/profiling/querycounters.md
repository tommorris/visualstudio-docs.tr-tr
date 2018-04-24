---
title: QueryCounters | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 8059d4b2-af61-4a47-a6c2-8da5c0741c74
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64bcd93e6d9045558c231c3b47ff967ffe14c078
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="querycounters"></a>QueryCounters
**QueryCounters** seçeneği bilgisayarda kullanılabilir CPU (Donanım) performans sayaçları listeler.  
  
 **QueryCounters** komut satırında tek seçenek olması gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /QueryCounters  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="remarks"></a>Açıklamalar  
 Profil Oluşturucu izleme yöntemini kullanırken, her veri koleksiyonu olayı sırasında bir veya daha fazla CPU performans sayaçları değerlerini toplayabilirsiniz. Örnekleme profili oluşturma yöntemi kullanırken, bir sayaç olay ve örnekleme aralığı kullanılacak olay sayısı belirtebilirsiniz.  
  
 Farklı işlemcilere farklı CPU performans sayaçları kullanıma sunar. Profil Oluşturucu neredeyse tüm işlemcilerde kullanılabilir genel sayaçları kümesini tanımlar. **QueryCounters** seçeneği hem genel sayaç adları ve işlemciye özgü sayaçları adlarını listeler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)