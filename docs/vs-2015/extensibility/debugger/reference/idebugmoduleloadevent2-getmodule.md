---
title: IDebugModuleLoadEvent2::GetModule | Microsoft Docs
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
- IDebugModuleLoadEvent2::GetModule
helpviewer_keywords:
- IDebugModuleLoadEvent2::GetModule
ms.assetid: c86482bb-9ce5-4e63-bbe0-969b50169424
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dcf01689b6ab133ee52870ff65293ab31e98855e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632298"
---
# <a name="idebugmoduleloadevent2getmodule"></a>IDebugModuleLoadEvent2::GetModule
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugModuleLoadEvent2::GetModule](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmoduleloadevent2-getmodule).  
  
Yüklenmekte olan modül alır yüklü veya kaldırılmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetModule(   
   IDebugModule2** pModule,  
   BSTR*           pbstrDebugMessage,  
   BOOL*           pbLoad  
);  
```  
  
```csharp  
int GetModule(   
   out IDebugModule2 pModule,  
   ref string        pbstrDebugMessage,  
   ref int           pbLoad  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pModule`  
 [out] Döndürür bir [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) yüklenmesi veya kaldırılması modülü temsil eden nesne.  
  
 `pbstrDebugMessage`  
 [out içinde] Bu olay açıklayan isteğe bağlı bir ileti döndürür. Bu parametre null değeri ise, hiçbir ileti istenir.  
  
 `pbLoad`  
 [out içinde] Sıfır olmayan (`TRUE`) Modül yükleme ve sıfır ise (`FALSE`) modülü kaldırma durumunda. Bu parametre null değeri ise, hiçbir durum istenir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)

