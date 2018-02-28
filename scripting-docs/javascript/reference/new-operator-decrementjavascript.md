---
title: "New işleci (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- new_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- new operator in JavaScript
ms.assetid: 5ea556ba-7ae6-426c-8430-9032eee5a0a5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ad004abb534d69bed1a1bd9bbd2ae96755544b9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="new-operator-javascript"></a>new İşleci (JavaScript)
Yeni bir nesne oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
new constructor ([arguments])   
```  
  
## <a name="parameters"></a>Parametreler  
 `constructor`  
 Gerekli. Nesne oluşturucusu. Oluşturucu bağımsız değişken almayan parantez atlanabilir.  
  
 `arguments`  
 İsteğe bağlı. Yeni nesnenin oluşturucuya geçirilen herhangi bir bağımsız değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 `new` İşleci aşağıdaki görevleri gerçekleştirir:  
  
-   Hiçbir üyeleriyle bir nesne oluşturur.  
  
-   Bir işaretçi yeni oluşturulan nesnenin geçirilmesi bu nesne için oluşturucuyu çağırır `this` işaretçi.  
  
-   Oluşturucu sonra oluşturucuya geçirilen bağımsız değişken göre nesnesini başlatır.  
  
 Geçerli kullanımlarını örnekleri bunlar **yeni** işleci.  
  
```JavaScript  
my_object = new Object;  
my_array = new Array();  
my_date = new Date("Jan 5 1996");  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Function deyimi](../../javascript/reference/function-statement-javascript.md)