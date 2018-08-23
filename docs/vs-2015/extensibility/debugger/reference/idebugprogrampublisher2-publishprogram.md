---
title: IDebugProgramPublisher2::PublishProgram | Microsoft Docs
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
- IDebugProgramPublisher2::PublishProgram
helpviewer_keywords:
- IDebugProgramPublisher2::PublishProgram
ms.assetid: 92ff63f0-e869-4040-b3ae-b2c899e708ff
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b38c371cdfd6b6d37ac90f57981b429f2ef2a1dc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687588"
---
# <a name="idebugprogrampublisher2publishprogram"></a>IDebugProgramPublisher2::PublishProgram
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgramPublisher2::PublishProgram](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogrampublisher2-publishprogram).  
  
Bu yöntem, bir program hata ayıklama altyapısı (DEs) için kullanılabilir ve oturum hata ayıklama Yöneticisi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   LPCOLESTR        szFriendlyName,  
   IUnknown*        pDebuggeeInterface  
);  
```  
  
```csharp  
int PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   string           szFriendlyName,  
   object           pDebuggeeInterface  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Engines`  
 [in] Başlatabilir veya bu programa ekleme GUID'ler DEs için bir dizi.  
  
 `szFriendlyName`  
 [in] (Bu Bu menüler ya da iletişim kutuları kullanıcıya görünür) programı için kolay ad.  
  
 `pDebuggeeInterface`  
 [in] `IUnknown` programı arabirimi (Bu değer bir tanımlama bilgisi program benzersiz olarak tanımlanabilmesi için kullanılır; bu değer "program yayımdan kaldırmak için" kullanılır)  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir programı hata ayıklama için artık kullanılabilir hale getirmek için çağrı [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)

