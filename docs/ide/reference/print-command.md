---
title: "Yazdır komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6eaf5d77da1dbc6e005764087dad338458e7ce8c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)