---
title: IDebugProcessEx2::AddImplicitProgramNodes | Microsoft Docs
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
- IDebugProcessEx2::AddImplicitProgramNodes
helpviewer_keywords:
- IDebugProcessEx2::AddImplicitProgramNodes method
ms.assetid: 8b491b00-f9e7-45b3-9115-fe58c3464289
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2552731cf9150e4e86a7ef4bf6d927aaac33cc7a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692185"
---
# <a name="idebugprocessex2addimplicitprogramnodes"></a>IDebugProcessEx2::AddImplicitProgramNodes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProcessEx2::AddImplicitProgramNodes](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes).  
  
Bu yöntem, belirtilen her hata ayıklama altyapısı (DE) için bir program düğüm ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT AddImplicitProgramNodes(  
   REFGUID guidLaunchingEngine,  
   GUID*   rgguidSpecificEngines,  
   DWORD   celtSpecificEngines  
);  
```  
  
```csharp  
int AddImplicitProgramNodes(  
   ref Guid guidLaunchingEngine,  
   Guid[]   rgguidSpecificEngines,  
   uint     celtSpecificEngines  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guidLaunchingEngine`  
 [in] `GUID` , Program başlatmak için kullanılacak olan (ve kendi program düğümleri eklemek için kabul edilir) bir DE.  
  
 `rgguidSpecificEngines`  
 [in] Dizi `GUID`DEs hangi programın düğümleri eklenir, s.  
  
 `celtSpecificEngines`  
 [in] Sayısını `GUID`s'te `rgguidSpecificEngines` dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 [Program düğümleri](../../../extensibility/debugger/program-nodes.md) her DE listelenen için eklenecek `rgguidSpecificEngines`— başlatma altyapısı hariç (belirtildiği `guidLaunchingEngine`), bir program başlattığında kendi program düğümü eklemek için kabul.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)   
 [Program Düğümleri](../../../extensibility/debugger/program-nodes.md)

