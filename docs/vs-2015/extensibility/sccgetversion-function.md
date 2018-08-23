---
title: SccGetVersion işlevi | Microsoft Docs
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
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2b5c5e5e6035d6ce0b81ba747efa3cea65ab2f97
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687730"
---
# <a name="sccgetversion-function"></a>SccGetVersion İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [SccGetVersion işlevi](https://docs.microsoft.com/visualstudio/extensibility/sccgetversion-function).  
  
Bu işlev, kaynak denetimi eklentisi tarafından desteklenen kaynak denetimi eklentisi API sürüm numarasını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
LONG SccGetVersion(void);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="return-value"></a>Dönüş Değeri  
 A `LONG` desteklenen kaynak denetimi eklentisi API sürüm numarasını içeren veri türü:  
  
|WORD|Açıklama|  
|----------|-----------------|  
|GET_Y_LPARAM KULLANIN|Ana sürüm|  
|GET_X_LPARAM|Alt sürüm|  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, bir kaynak denetimi Eklentisi Kaynak Denetimi Eklentisi API sürümü 1.3 destekliyorsa, bu işlev 0x0103 döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API İşlevleri](../extensibility/source-control-plug-in-api-functions.md)

