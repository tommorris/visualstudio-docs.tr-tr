---
title: SccBeginBatch işlevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccBeginBatch
helpviewer_keywords:
- SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e62074fa30d68e4cd283fb431f0ae64cff957ed4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686155"
---
# <a name="sccbeginbatch-function"></a>SccBeginBatch İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [SccBeginBatch işlevi](https://docs.microsoft.com/visualstudio/extensibility/sccbeginbatch-function).  
  
Bu işlev, kaynak denetim işlemlerini toplu bir dizi başlatır. [SccEndBatch](../extensibility/sccendbatch-function.md) batch sonlandırmak için çağırılır. Bu toplu bulunmayabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
SCCRTN SccBeginBatch(void);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kaynak Denetimi Eklentisi uygulanması bu işlev, aşağıdaki değerlerden birini döndürmesi beklenir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Toplu işlem başarıyla başladı.|  
|SCC_E_UNKNOWNERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak denetimi toplu birden çok proje veya birden çok bağlamları arasında aynı işlemleri yürütmek için kullanılır. Toplu işlemleri, toplu bir işlemi sırasında proje başına yedekli iletişim kutularına kullanıcı deneyiminden ortadan kaldırmak için kullanılabilir. `SccBeginBatch` İşlevi ve [SccEndBatch](../extensibility/sccendbatch-function.md) işlevi çift olarak başlangıcını ve bitişini bir işlemin belirtmek için kullanılır. Bunlar iç içe olamaz. `SccBeginBatch` bir toplu işlem sürmekte olduğunu belirten bir bayrak ayarlar.  
  
 Bir toplu işlem etkili olsa da, kaynak denetimi eklentisi en fazla kullanıcı için herhangi bir soru için bir iletişim kutusu sunar ve bu iletişim kutusu yanıtı sonraki tüm işlemleri uygulamak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccEndBatch](../extensibility/sccendbatch-function.md)

