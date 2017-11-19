---
title: "SccUninitialize işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccUninitialize
helpviewer_keywords: SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 434987489feccd5f576e04d69afbb4b39e1dc754
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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