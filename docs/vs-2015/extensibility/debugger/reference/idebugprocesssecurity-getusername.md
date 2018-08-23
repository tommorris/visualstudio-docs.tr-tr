---
title: IDebugProcessSecurity::GetUserName | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c0dee5cd71cc41c8377914ade5800976d9e7ff57
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691749"
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProcessSecurity::GetUserName](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocesssecurity-getusername).  
  
Kullanıcı adı bağlantı noktası tedarikçiden alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetUserName(  
    BSTR *pbstrUserName  
);  
```  
  
```csharp  
int GetUserName (  
    string pbstrUserName  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pbstrUserName`  
 [out] Kullanıcı adını içeren bir dize.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, döndürür `S_OK`. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetUserName` görüntülenen kullanıcı adını döndürür **kullanıcı adı** sütununun **iliştirme** iletişim kutusu. Görüntülenecek **iliştirme** iletişim kutusu, tıklayın **iliştirme** üzerinde **Araçları** menüde [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] tümleşik geliştirme ortamı (IDE).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)

