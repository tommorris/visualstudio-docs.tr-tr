---
title: "Windows komut dosyası konakları | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Script Host, implementing hosts
ms.assetid: 9d5f6471-b318-40f3-be01-d9cd0b1cdd47
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 41fa898c7f0d62cd35cc1cb1c7b35eb2651c8bb6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="windows-script-hosts"></a>Windows Komut Dosyası Konakları
Microsoft Windows Script host uygularken, güvenli bir şekilde bir komut dosyası motoru Yalnız çağrıları kabul edilebilir [Iactivescriptsite](../winscript/reference/iactivescriptsite.md) konak aşağıdakileri yapar sürece temel iş parçacığının bağlamında arabirim:  
  
-   Temel bir iş parçacığı (ileti döngüsü içeren genellikle iş parçacığı) seçer.  
  
-   Komut dosyası altyapısı temel iş parçacığında başlatır.  
  
-   Özellikle, örneklerini olduğu gibi izin verilen altyapısı yöntemleri yalnızca temel, iş parçacığı scripting çağrıları [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) ve [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
-   Komut dosyası altyapısı dağıtım nesnesi yalnızca temel iş parçacığından çağırır.  
  
-   Bir pencere tanıtıcının sağladıysanız ileti döngüsü temel iş parçacığında çalıştırmasını sağlar.  
  
-   Yalnızca kaynak olayları temel bir iş parçacığı model nesneleri ana bilgisayarın nesnesindeki sağlar.  
  
 Bu kurallar, tüm tek iş parçacıklı ana bilgisayar tarafından otomatik olarak izlenir. Yukarıda açıklanan kısıtlı modeli çağırarak takılmış bir komut dosyası iptal etmek bir konak izin vermek için kasıtlı olarak gevşek yeterince [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) (CTRL + BREAK işleyici veya benzeri tarafından başlatılan) başka bir iş parçacığından veya çok bir komut dosyası kullanarak yeni bir iş parçacığı içinde yinelenen [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu kısıtlamalar hiçbiri geçerli bir boş iş parçacıklı uygulamak için seçtiği bir ana bilgisayara [Iactivescriptsite](../winscript/reference/iactivescriptsite.md) arabirimi ve ücretsiz iş parçacıklı nesne modeli. Böyle bir ana bilgisayar kullanabilirsiniz [IActiveScript](../winscript/reference/iactivescript.md) kısıtlama olmadan tüm iş parçacığı arabiriminden.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows komut dosyası arabirimleri](../winscript/windows-script-interfaces.md)