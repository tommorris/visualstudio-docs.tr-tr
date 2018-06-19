---
title: IDebugEngineLaunch2::LaunchSuspended | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineLaunch2::LaunchSuspended
helpviewer_keywords:
- IDebugEngineLaunch2::LaunchSuspended
ms.assetid: 5dd2643e-c20a-470e-9024-2a423eb39856
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a05e8f034ec30f0f387675759cb7601f7b3fc3e7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31114631"
---
# <a name="idebugenginelaunch2launchsuspended"></a>IDebugEngineLaunch2::LaunchSuspended
Bu yöntem, hata ayıklama altyapısı (DE) yoluyla bir işlem başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT LaunchSuspended (   
   LPCOLESTR             pszMachine,  
   IDebugPort2*          pPort,  
   LPCOLESTR             pszExe,  
   LPCOLESTR             pszArgs,  
   LPCOLESTR             pszDir,  
   BSTR                  bstrEnv,  
   LPCOLESTR             pszOptions,  
   LAUNCH_FLAGS          dwLaunchFlags,  
   DWORD                 hStdInput,  
   DWORD                 hStdOutput,  
   DWORD                 hStdError,  
   IDebugEventCallback2* pCallback,  
   IDebugProcess2**      ppDebugProcess  
);  
```  
  
```csharp  
int LaunchSuspended(  
   string               pszServer,   
   IDebugPort2          pPort,   
   string               pszExe,   
   string               pszArgs,   
   string               pszDir,   
   string               bstrEnv,   
   string               pszOptions,   
   enum_LAUNCH_FLAGS    dwLaunchFlags,   
   uint                 hStdInput,   
   uint                 hStdOutput,   
   uint                 hStdError,  
   IDebugEventCallback2 pCallback,   
   out IDebugProcess2   ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszMachine`  
 [in] İşlemi başlatmak üzere makinenin adı. Yerel makine belirlemek için boş bir değer kullanın.  
  
 `pPort`  
 [in] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) program çalışır bağlantı noktasını temsil eden arabirim.  
  
 `pszExe`  
 [in] Başlatılacak yürütülebilir dosya adı.  
  
 `pszArgs`  
 [in] Yürütülebilir dosyaya geçirilecek bağımsız değişkenler. Bağımsız değişken yoksa null değeri olabilir.  
  
 `pszDir`  
 [in] Yürütülebilir dosya tarafından kullanılan çalışma dizinini adı. Çalışma dizini gerekliyse bir null değer olabilir.  
  
 `bstrEnv`  
 [in] Ek bir NULL Sonlandırıcı tarafından izlenen NULL ile sonlandırılmış dizeler ortam bloğu.  
  
 `pszOptions`  
 [in] Yürütülebilir dosya için Seçenekler.  
  
 `dwLaunchFlags`  
 [in] Belirtir [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md) bir oturum için.  
  
 `hStdInput`  
 [in] Bir alternatif giriş akışı işleyin. Yeniden yönlendirme gerekli değilse 0 olabilir.  
  
 `hStdOutput`  
 [in] Alternatif çıkış akışına işleyin. Yeniden yönlendirme gerekli değilse 0 olabilir.  
  
 `hStdError`  
 [in] Diğer hata çıkış akışına işleyin. Yeniden yönlendirme gerekli değilse 0 olabilir.  
  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) hata ayıklayıcı olayları alan nesnesi.  
  
 `ppDebugProcess`  
 [out] Döndürür elde edilen [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) başlatılan işlemi temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Normalde, [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] kullanarak bir programı başlatan [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) yöntemi ve ardından hata ayıklayıcı askıya alınmış programın ekler. Ancak, hata ayıklama altyapısı gerekebilir (örneğin hata ayıklama altyapısı bir yorumlayıcı bir parçasıdır ve ayıklanacak program yorumlanan dilidir,), bir program, bu durumda başlatmak koşullar vardır [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] kullanan `IDebugEngineLaunch2::LaunchSuspended` yöntemi .  
  
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md) yöntemi işlemi askıya alınmış durumda başarıyla başlatıldı sonra işlemini başlatmak üzere çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)   
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)