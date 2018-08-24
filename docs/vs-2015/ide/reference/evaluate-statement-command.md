---
title: Deyimi değerlendir komutu | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d569033193997135d9d0bc990ab7b9a9ef815f8d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681383"
---
# <a name="evaluate-statement-command"></a>Deyimi Değerlendir Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [değerlendirmek deyimi komut](https://docs.microsoft.com/visualstudio/ide/reference/evaluate-statement-command).  
  
  
Değerlendirir ve verilen deyimi görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.EvaluateStatement text   
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Gerekli. Değerlendirilecek ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Girmek için kullanılan pencere **EvaluateStatement** komut belirleyen bir eşittir işareti (=) karşılaştırma işleci veya bir atama işleci olarak yorumlanır.  
  
 İçinde **komut** penceresinde, eşittir işareti (=) karşılaştırma işleci yorumlanır. Örneğin, bu nedenle, değişkenlerin değerleri `a` ve `b` farklı, sonra komutu  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 bir değeri döndürür `false`.  
  
 İçinde **hemen** penceresinde, aksine, eşittir işareti (=) bir atama işleci yorumlanır. Bunu, örneğin, komut  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 atar `a` değişkenin değerini `b`.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.EvaluateStatement(a+b)  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazdır komutu](../../ide/reference/print-command.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



