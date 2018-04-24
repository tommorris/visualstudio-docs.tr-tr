---
title: Idiaframedata::Execute | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::execute method
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0645d2364712769a6b4f18ef14fbbcb503a51888
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaframedataexecute"></a>IDiaFrameData::execute
Yığın geriye doğru izleme gerçekleştirir ve sonuçları bir yığın ilerlemesi çerçeve arabiriminde döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT execute (   
   IDiaStackWalkFrame* frame  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `frame`  
 [in] Bir [Idiastackwalkframe](../../debugger/debug-interface-access/idiastackwalkframe.md) çerçeve yazmaçlar durumunu tutan nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Aşağıdaki tabloda bu yöntem için olası dönüş değerleri gösterir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|E_DIA_INPROLOG|Başlangıç kodunda yığın çerçevesi yürütülemiyor.|  
|E_DIA_SYNTAX|Ayrıştırma hatası çerçeve programında karşılaştı.|  
|E_DIA_FRAME_ACCESS|Erişim kaydeder veya bellek oluşturulamıyor.|  
|E_DIA_VALUE|Bir değer (örneğin, sıfıra bölme) hesaplama hatası.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, yığın geriye doğru izleme için hata ayıklama sırasında çağrılır. [Idiastackwalkframe](../../debugger/debug-interface-access/idiastackwalkframe.md) nesne kayıtları için güncelleştirmeleri almak ve tarafından kullanılan yöntemler sağlamak için istemci uygulaması tarafından gerçekleştirilir `execute` yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)