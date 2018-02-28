---
title: "SccUninitialize işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5976313939ee9efa81c71e7894da8e5f45e2d017
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sccuninitialize-function"></a>SccUninitialize işlevi
Bu işlev herhangi bir ayırma veya önceki bir çağrı tarafından oluşturulan açık bağlantıları temizler [SccInitialize](../extensibility/sccinitialize-function.md) eklenti kaynak denetimi kapatılıyor hazırlanırken.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccUninitialize (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısına yönelik işaretçinin oluşturulan [SccInitialize](../extensibility/sccinitialize-function.md).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Başarıyla tamamlanan temizleyin.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak Denetim eklentisi kapatılması hazırlama ve bağlam yapısını eklenti ayırdığı bellek boşaltma sorumludur. İşlev bir eklenti, belirtilen her örneği için bir kez çağrılır. Çağrı [SccInitialize](../extensibility/sccinitialize-function.md) bu çağrıyı önce gelir. Proje hala çağrısı zaman açılabilir `SccUninitialize`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)