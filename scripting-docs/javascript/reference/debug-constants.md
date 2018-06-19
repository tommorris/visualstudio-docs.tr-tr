---
title: Debug sabitleri | Microsoft Docs
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
ms.assetid: 76b572ee-bad0-404e-9fd4-841c9af35642
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e2c50181dc9f40d8665d6caca407232231682d63
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790355"
---
# <a name="debug-constants"></a>Debug Sabitleri
Hata ayıklama özelliklerini sabitleri dönüş sabit değerleri `Debug` nesnesi.  
  
## <a name="debug-object-constants"></a>Hata ayıklama nesnesi sabitleri  
 Özellikleridir sabit değerleri aşağıdaki tabloda listelenmektedir [hata ayıklama nesnesi](../../javascript/reference/debug-object-javascript.md).  
  
|Sabit|Açıklama|Değer|  
|--------------|-----------------|-----------|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_ASSIGN_DELEGATE`|Zaman uyumlu iş öğesi, bir geri çağırma veya zaman uyumsuz bir işlem tarafından çalıştırılacak devamlılık atanmış.|0|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_JOIN`|Zaman uyumlu iş öğesi bir birleşim zaman uyumsuz işlemin parçası memnun.|1.|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_CHOOSEANY`|Zaman uyumlu iş öğesi bir seçim zaman uyumsuz işlem memnun.|2|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_CANCEL`|Zaman uyumlu iş öğesi iptal edildi.|3|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_ERROR`|Zaman uyumlu iş öğesini zaman uyumsuz bir işlem neden bir hata oluştu.|4|  
|`Debug.MS_ASYNC_OP_STATUS_SUCCESS`|Zaman uyumsuz işlemi başarılı oldu.|1.|  
|`Debug.MS_ASYNC_OP_STATUS_CANCELED`|Zaman uyumsuz işlemi iptal edildi.|2|  
|`Debug.MS_ASYNC_OP_STATUS_ERROR`|Zaman uyumsuz işlem hatayla sonuçlandı.|3|  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Debug.msTraceAsyncOperationCompleted işlevi](../../javascript/reference/debug-mstraceasyncoperationcompleted-function.md)   
 [Debug.msUpdateAsyncCallbackRelation işlevi](../../javascript/reference/debug-msupdateasynccallbackrelation-function.md)