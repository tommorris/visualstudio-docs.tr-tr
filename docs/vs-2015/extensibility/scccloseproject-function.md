---
title: SccCloseProject işlevi | Microsoft Docs
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
- SccCloseProject
helpviewer_keywords:
- SccCloseProject function
ms.assetid: 259c2069-d349-4814-810f-1c3151b7fb84
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aebc9d43ebf712d8add7e2aee4f7884ef2754da6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632125"
---
# <a name="scccloseproject-function"></a>SccCloseProject İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [SccCloseProject işlevi](https://docs.microsoft.com/visualstudio/extensibility/scccloseproject-function).  
  
Bu işlev, belirli bir oturum sonunu işaretlemek için bir proje, kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
SCCRTN SccCloseProject (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 Kaynak Denetimi Eklentisi bağlam yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kaynak Denetimi Eklentisi uygulanması bu işlev, aşağıdaki değerlerden birini döndürmesi beklenir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Proje başarıyla kapatıldı.|  
|SCC_E_PROJNOTOPEN|Proje şu anda açıktır.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 [SccOpenProject](../extensibility/sccopenproject-function.md) her zaman önce bu işlev çağrılır. Bu işlev çağrısı öğelerine yönelik çağrıdan sonra takip `SccOpenProject` işlevi veya [SccUninitialize](../extensibility/sccuninitialize-function.md), sona erdiği kaynak denetim sistemi bağlantısı tamamen.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [Sccınitialize](../extensibility/sccinitialize-function.md)

