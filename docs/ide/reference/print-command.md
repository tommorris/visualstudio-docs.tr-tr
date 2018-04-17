---
title: Yazdır komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 66175f8aa1d371386793b892c0ead5b4dd1885b0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="print-command"></a>Yazdır Komutu
Bir ifadeyi değerlendirir veya belirtilen metin görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.Print text  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Gerekli. Değerlendirilecek ifade veya görüntülenecek metin.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu komut için bir diğer ad olarak soru işareti (?) kullanabilirsiniz. Bu nedenle, örneğin, komutu  
  
```  
>Debug.Print expA  
```  
  
 Ayrıca yazılabilir  
  
```  
>? expA  
```  
  
 Her iki sürümünün de bu komut geçerli ifadenin değerini döndürür `expA`.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.Print varA  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Deyimi değerlendir komutu](../../ide/reference/evaluate-statement-command.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)