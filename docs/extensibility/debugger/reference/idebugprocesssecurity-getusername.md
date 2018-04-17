---
title: IDebugProcessSecurity::GetUserName | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 94fcc74943deb33e7f98ba24e9d7389a9d5746fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
Kullanıcı adı listesinden bağlantı noktası tedarikçi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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
 [out] Kullanıcı adını içeren dize.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, döndürür `S_OK`. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetUserName` görüntülenen kullanıcı adını döndürür **kullanıcı adı** sütunu **ekleme işlemi için** iletişim kutusu. Görüntülemek için **ekleme işlemi için** iletişim kutusu, tıklatın **ekleme işlemi için** üzerinde **Araçları** menüde [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)