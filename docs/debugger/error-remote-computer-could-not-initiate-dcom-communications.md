---
title: 'Hata: Uzak bilgisayar DCOM iletişimini başlatamadı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.unmarshal_callback_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e104e63bf9dde11efbefe4b657a85b3bfc94549
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-remote-computer-could-not-initiate-dcom-communications"></a>Hata: Uzak bilgisayar DCOM iletişimini başlatamadı
Uzak makinede yerel makineyle iletişim kurmak çalışırken bir DCOM hata oluştu. Yerel makine olan makinesidir  
  
 Visual Studio çalışıyor. Bu hata, çeşitli nedenlerle oluşabilir:  
  
-   Yerel makinede etkin bir güvenlik duvarı vardır.  
  
-   Yerel makinede uzak makinede Windows kimlik doğrulaması çalışmıyor.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Yerel makinede Windows Güvenlik Duvarı etkinse, bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md) yerel hata ayıklama için Güvenlik Duvarı'nı yapılandırma hakkında yönergeler için.  
  
2.  Uzak sunucudan yerel makine üzerinde bir dosya paylaşımı açılmaya çalışılırken test Windows kimlik doğrulama.  
  
3.  Windows kimlik doğrulaması geri yüklemek için her iki makine yeniden deneyin. Yerel ve Uzak makinelerde Kerberos hataları için olay günlüklerini inceleyin ve bilinen sorunlar için etki alanı yöneticileri ile iletişime geçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)