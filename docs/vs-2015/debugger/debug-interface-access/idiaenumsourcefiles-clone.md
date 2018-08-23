---
title: Idiaenumsourcefiles::Clone | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Clone method
ms.assetid: 87a9a9b6-3927-4131-927c-ad95f8f098b9
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5d56f2a841056c0b8f924f5f47ea3479997cccab
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634125"
---
# <a name="idiaenumsourcefilesclone"></a>IDiaEnumSourceFiles::Clone
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiaenumsourcefiles::Clone](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumsourcefiles-clone).  
  
Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Clone (   
   IDiaEnumSourceFiles** ppenum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ppenum  
 [out] Döndürür bir [Idiaenumsourcefiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md) Numaralandırıcı bir kopyasını içeren nesne. Yinelenen kaynak dosyaları değil, yalnızca Numaralandırıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)



