---
title: StackFrameTypeEnum | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- StackFrameTypeEnum enumeration
ms.assetid: 61e40163-eee0-4c1f-af47-cef3771bdc41
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4dcb46fc2fb3936e0cee91426b4787945bd14f59
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="stackframetypeenum"></a>StackFrameTypeEnum
Yığın çerçeve türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
enum StackFrameTypeEnum {  
   FrameTypeFPO,  
   FrameTypeTrap,  
   FrameTypeTSS,  
   FrameTypeStandard,  
   FrameTypeFrameData,  
   FrameTypeUnknown = -1  
};  
```  
  
## <a name="elements"></a>Öğeleri  
 `FrameTypeFPO`  
 Çerçeve işaretçisi atlanmış; FPO bilgileri kullanılabilir.  
  
 `FrameTypeTrap`  
 Çekirdek Tuzak Çerçevesi.  
  
 `FrameTypeTSS`  
 Çekirdek Tuzak Çerçevesi.  
  
 `FrameTypeStandard`  
 Standart EBP yığın çerçevesi.  
  
 `FrameTypeFrameData`  
 Çerçeve işaretçisi atlanmış; Çerçeve veri bilgileri kullanılabilir.  
  
 `FrameTypeUnknown`  
 Hata ayıklama bilgisi yok çerçevesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu numaralandırma değerleri için yapılan bir çağrı tarafından döndürülen [Idiastackframe::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackFrame::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)