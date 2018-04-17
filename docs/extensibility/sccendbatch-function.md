---
title: SccEndBatch işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccEndBatch
helpviewer_keywords:
- SccEndBatch function
ms.assetid: 100e7833-fe0a-45c0-9fca-3e61fd1165b7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ec549b5bb0a6c48946edf59f0ab1423cea0ac704
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sccendbatch-function"></a>SccEndBatch işlevi
Bu işlev, kaynak denetimi işlemleri toplu sonlanır. Bu toplu bulunmayabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccEndBatch(void);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Toplu işlem başarıyla tamamlanmış.|  
|SCC_E_UNKNOWNERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak denetimi toplu birden çok projeleri veya birden çok bağlamları arasında aynı kaynak denetimi işlemleri yürütmek için kullanılır. Toplu kullanıcı deneyimini yedekli iletişim kutularından toplu işlemi sırasında ortadan kaldırmak için kullanılabilir. [SccBeginBatch](../extensibility/sccbeginbatch-function.md) ve `SccEndBatch` işlevi başlangıcını ve bitişini bir işlemin belirtmek için bir çift olarak kullanılır. Bunlar iç içe olamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccBeginBatch](../extensibility/sccbeginbatch-function.md)