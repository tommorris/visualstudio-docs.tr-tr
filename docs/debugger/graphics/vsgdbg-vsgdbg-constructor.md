---
title: "VsgDbg::VsgDbg (oluşturucu) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 670651e6-5e79-4845-b0c2-671beb7055a8
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7231e0cc5c9d5946fabe504c16813ea47b24bdbc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="vsgdbgvsgdbg-constructor"></a>VsgDbg::VsgDbg (Oluşturucu)
Bir örneğini oluşturur `VsgDbg` sınıfı ile veya olmadan etkin şekilde yakalamak ve varsayılan olarak belirli Boole parametresi temelinde, grafik bilgilerini kaydetmek için grafik tanılamayı uygulama bileşeninin hazırlanıyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
VsgDbg(  
  bDefaultInit  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `bDefaultInit`  
 `true`Grafik tanılama uygulama bileşeninin etkin olarak yakalamak ve grafik bilgilerini kaydetmek hazır olduğunu belirtmek için; `false` uygulama etkin olarak yakalamak ve şu anda grafik bilgilerini kaydetmek için hazırlıklı olmalıdır değil olduğunu belirtmek için.  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman Oluşturucusu çağrılır ile `bDefaultInit` kümesine `true`, grafik günlük dosyasının dosya adı tarafından nasıl belirlenir `DONT_SAVE_VSGLOG_TO_TEMP` ve `VSG_DEFAULT_RUN_FILENAME` önişlemci sembolleri önce tanımlanır `vsgcapture.h` uygulamanızda eklenmiştir.  
  
 Ne zaman Oluşturucusu çağrılır ile `bDefaultInit` kümesine `false`, etkin olarak yakalamak ve daha sonraki bir zamanda grafik bilgilerini çağırarak kaydetmek için grafik tanılamayı uygulama bileşeninin hazırlanabilmesi `Init` işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VsgDbg:: ~ VsgDbg (yok edici)](vsgdbg-tilde-vsgdbg-destructor.md)   
 [Init](init.md)   
 [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)   
 [VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)