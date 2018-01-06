---
title: IDebugProgramEx2::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramEx2::Attach
helpviewer_keywords: IDebugProgramEx2::Attach
ms.assetid: 33b22b2f-431e-4205-9441-d28a9c928c97
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 440a4ce6b008efe541187d1d99d886f4c7c5f9ab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramex2attach"></a>IDebugProgramEx2::Attach
Bir oturum için bir program ekleyin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   DWORD                 dwReason,  
   IDebugSession2*       pSession  
);  
```  
  
```  
[C#]  
int Attach(   
   IDebugEventCallback2 pCallback,  
   uint                 dwReason,  
   IDebugSession2       pSession  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pCallback`  
 [in] Bir [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) olaylara bağlı hata ayıklama altyapısı gönderir geri çağırma işlevi temsil eden nesne.  
  
 `dwReason`  
 [in] Arasında bir değer [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) attach işleminin nedenini açıklayan numaralandırması.  
  
 `pSession`  
 [in] Programa ekleme oturum benzersiz olarak tanımlayan bir değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Bu yöntem döndürmelidir `E_ATTACH_DEBUGGER_ALREADY_ATTACHED` program zaten bağlı.  
  
## <a name="remarks"></a>Açıklamalar  
 Programı içeren bağlantı noktası değeri kullanabilirsiniz `pSession` hangi oturumu programa ekleme girişimi belirlemek için. Örneğin, bir bağlantı noktası aynı anda bir işlem eklemek yalnızca bir hata ayıklama oturumu izin veriyorsa, bağlantı noktası aynı oturum zaten işlemdeki diğer programları bağlı olmadığını belirleyebilirsiniz.  
  
> [!NOTE]
>  Arabirim geçirilen `pSession` yalnızca bir tanımlama bilgisi, bu programa; ekleme oturum hata ayıklama Yöneticisi benzersiz olarak tanımlayan bir değer olarak değerlendirilmesi için sağlanan arabirimde yöntemlerin hiçbiri işlev.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)