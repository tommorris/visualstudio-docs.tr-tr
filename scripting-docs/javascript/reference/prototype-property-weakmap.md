---
title: prototype özelliği (WeakMap) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d28b8a9b-38c9-443d-9586-7cc74784bd99
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5cc1bff0d62f2aeb8d6fb78a0857f287fb34078c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791285"
---
# <a name="prototype-property-weakmap"></a>prototype Özelliği (WeakMap)
İçin prototip bir başvuru döndürür bir `WeakMap` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
weakmap.prototype  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `weakmap` Adı olmayan bağımsız değişken bir `WeakMap` nesnesi.  
  
 Kullanım `prototype` temel nesne sınıfı için işlevselliği sağlamak için özellik. Bir nesnenin "Bu nesneye atanmış prototip davranışını devral" yeni örnekleri.  
  
 Örneğin, bir yöntem eklemek için `WeakMap` en büyük öğenin değerini döndürür nesne `WeakMap`, işlevi bildirin, ekleyin `WeakMap.prototype`ve ardından onu kullanabilirsiniz.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]