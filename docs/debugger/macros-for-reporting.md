---
title: Raporlama makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.macros
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- macros, CRT reporting macros
- macros, debugging with
- _RPTFn macro
- CRT, reporting macros
- debugging [CRT], reporting macros
- _RPTn macro
ms.assetid: f2085314-a3a8-4caf-a5a4-2af9ad5aad05
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd2dbb0651aa35243090fb554fa9142573e04e04
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31476916"
---
# <a name="macros-for-reporting"></a>Raporlama Makroları
Kullanabileceğiniz **_RPTn**, ve **_RPTFn** CRTDBG içinde tanımlı makrolar. Kullanımını değiştirmek için H `printf` hata ayıklama için deyimleri. Bu makroları otomatik olarak, yayın kaybolur ne zaman yapı **_DEBUG** ; böylece bunları içine gerek yoktur, tanımlı değil **#ifdef**s.  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|**_RPT0**, **_RPT1**, **_RPT2**, **_RPT3**, **_RPT4**|Bir ileti dizesi ve sıfır dört bağımsız olarak çıkarır. _RPT1 için **_RPT4**, printf stili biçimlendirme dizesi bağımsız değişkenler için ileti dizesi görür.|  
|**_RPTF0**, **_RPTF1**, **, _RPTF2**, **_RPTF4**|Aynı **_RPTn**, ancak bu makroları ayrıca makrosu bulunduğu dosya adı ve satır numarası çıktı.|  
  
 Aşağıdaki örnek göz önünde bulundurun:  
  
```  
#ifdef _DEBUG  
    if ( someVar > MAX_SOMEVAR )  
        printf( "OVERFLOW! In NameOfThisFunc( ),  
               someVar=%d, otherVar=%d.\n",  
               someVar, otherVar );  
#endif  
```  
  
 Bu kod değerlerini çıkarır `someVar` ve `otherVar` için **stdout**. Aşağıdaki çağrıyı kullanabilirsiniz `_RPTF2` aynı bu değerleri ve ayrıca, dosya adı ve satır numarası bildirmek için:  
  
```  
if (someVar > MAX_SOMEVAR) _RPTF2(_CRT_WARN, "In NameOfThisFunc( ), someVar= %d, otherVar= %d\n", someVar, otherVar );  
```  
  
 Belirli bir uygulama C çalışma zamanı kitaplığı ile sağlanan makroları sağlıyor mu Raporlama hata ayıklama gerektiğini fark ederseniz, özellikle kendi gereksinimlerinizi karşılayacak şekilde tasarlanmış bir makro yazabilirsiniz. Üstbilgi dosyaları her birinde Örneğin, size adlı bir makro tanımlamak için aşağıdaki gibi kod içerebilir **ALERT_IF2**:  
  
```  
#ifndef _DEBUG                  /* For RELEASE builds */  
#define  ALERT_IF2(expr, msg, arg1, arg2)  do {} while (0)  
#else                           /* For DEBUG builds   */  
#define  ALERT_IF2(expr, msg, arg1, arg2) \  
    do { \  
        if ((expr) && \  
            (1 == _CrtDbgReport(_CRT_ERROR, \  
                __FILE__, __LINE__, msg, arg1, arg2))) \  
            _CrtDbgBreak( ); \  
    } while (0)  
#endif  
```  
  
 Yapılan bir çağrı **ALERT_IF2** tüm işlevlerini gerçekleştirebilir **printf** , bu konunun başlangıcında kod:  
  
```  
ALERT_IF2(someVar > MAX_SOMEVAR, "OVERFLOW! In NameOfThisFunc( ),   
someVar=%d, otherVar=%d.\n", someVar, otherVar );  
```  
  
 Özel bir makro fazla veya az (daha kullanışlı ne olduğuna bağlı olarak) farklı hedeflere bilgileri raporlamak için kolayca değiştirilebilmesi için hata ayıklama gereksinimlerinizi geliştikçe bu yaklaşım özellikle yararlı olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT hata ayıklama teknikleri](../debugger/crt-debugging-techniques.md)