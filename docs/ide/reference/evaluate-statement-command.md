---
title: Deyimi değerlendir komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fe960ec84830ce76095577f7d8ee2f0c9c4ccbe8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="evaluate-statement-command"></a>Deyimi Değerlendir Komutu
Değerlendirir ve belirli deyim görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.EvaluateStatement text   
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 Gerekli. Değerlendirilecek ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Girmek için kullanılan penceresi **EvaluateStatement** komutu belirleyen bir eşittir işareti (=) bir karşılaştırma işleci veya atama işleci olarak yorumlanır.  
  
 İçinde **komutu** penceresinde, bir eşittir işareti (=) bir karşılaştırma işleci yorumlanır. Örneğin, bunu, değişkenlerin değerleri `a` ve `b` farklı, sonra komutu  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 bir değeri döndürür `false`.  
  
 İçinde **hemen** penceresinde, buna karşın bir eşittir işareti (=) atama işleci yorumlanır. Bu nedenle, örneğin, komutu  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 değişkene atar `a` değişkenin değerini `b`.  
  
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