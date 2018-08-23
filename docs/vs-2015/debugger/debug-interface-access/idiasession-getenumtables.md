---
title: Idiasession::getenumtables | Microsoft Docs
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
- IDiaSession::getEnumTables method
ms.assetid: 66e0fba2-ca63-4e24-a46a-c99c7fb61dd1
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c8937bd1a04d8856c2b2a7b18c5a05e91a8070d7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692811"
---
# <a name="idiasessiongetenumtables"></a>IDiaSession::getEnumTables
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasession::getenumtables](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-getenumtables).  
  
Sembol deposu içerisinde bulunan tüm tablolar için bir numaralandırıcı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT getEnumTables (   
   IDiaEnumTables** ppEnumTables  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppEnumTables`  
 [out] Döndürür bir [Idiaenumtables](../../debugger/debug-interface-access/idiaenumtables.md) nesne. Bu arabirim, sembol deposundaki tablolar numaralandırmak için kullanın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="example"></a>Örnek  
 Bu örnekte kullanan genel bir işlev sunar `getEnumTables` belirli Numaralandırıcı nesnesi elde etmek için yöntemi. Numaralandırıcı bulunursa, işlev istendiği arayüz dönüştürülebilen bir işaretçi döndürür; Aksi halde, işlev döndürür `NULL`.  
  
```cpp#  
IUnknown *GetTable(IDiaSession *pSession, REFIID iid)  
{  
    IUnknown *pUnknown = NULL;  
    if (pSession != NULL)  
    {  
        CComPtr<IDiaEnumTables> pEnumTables;  
        if (pSession->getEnumTables(&pEnumTables) == S_OK)  
        {  
             CComPtr<IDiaTable> pTable;  
             DWORD celt = 0;  
             while(pEnumTables->Next(1,&pTable,&celt) == S_OK &&  
                   celt == 1)  
             {  
                  if (pTable->QueryInterface(iid, (void **)pUnknown) == S_OK)  
                  {  
                       break;  
                  }  
                  pTable = NULL;  
             }  
        }  
    }  
    return(pUnknown);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumtables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)



