---
title: "SccBeginBatch işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccBeginBatch
helpviewer_keywords: SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0e18eedcab133329f10064ef3dd6486beb2e1596
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sccbeginbatch-function"></a>SccBeginBatch işlevi
Bu işlev bir kaynak denetimi işlemleri toplu işlem dizisini başlatır. [SccEndBatch](../extensibility/sccendbatch-function.md) toplu sonlandırmak için çağrılır. Bu toplu bulunmayabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccBeginBatch(void);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Toplu işlem başarıyla başladı.|  
|SCC_E_UNKNOWNERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak denetimi toplu birden çok projeleri veya birden çok bağlamları arasında aynı işlemlerini yürütmek için kullanılır. Toplu kullanıcı deneyimini proje başına yedekli iletişim kutularından toplu işlemi sırasında ortadan kaldırmak için kullanılabilir. `SccBeginBatch` İşlevi ve [SccEndBatch](../extensibility/sccendbatch-function.md) işlevi çifti olarak başlangıcını ve bitişini bir işlemin belirtmek için kullanılır. Bunlar iç içe olamaz. `SccBeginBatch`bir toplu işlem devam ediyor belirten bir bayrak ayarlar.  
  
 Toplu işlem etkinken, eklenti kaynak denetimi en çok bir iletişim kutusu herhangi bir soru için kullanıcıya sunmak ve iletişim kutusu yanıtı sonraki tüm işlemler uygulayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccEndBatch](../extensibility/sccendbatch-function.md)