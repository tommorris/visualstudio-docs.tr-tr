---
title: IDebugProcess2::GetAttachedSessionName | Microsoft Docs
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
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1ba2ad04d96f8970ca43c4f1a136d2676ed70fad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697493"
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProcess2::GetAttachedSessionName](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess2-getattachedsessionname).  
  
Bu işlem hata ayıklama oturumu adını alır. Bir IDE bir kullanıcı belirli bir makinenin belirli bir işlemde hata ayıklama için bu bilgileri görüntüleyebilirsiniz.  
  
> [!NOTE]
>  Bu metot kullanımdan kaldırılmıştır ve uygulaması her zaman döndürmelidir `E_NOTIMPL`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetAttachedSessionName(  
   BSTR* pbstrSessionName  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pbstrSessionName`  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem her zaman döndürmelidir `E_NOTIMPL`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

