---
title: IDebugEngineLaunch2::LaunchSuspended | Microsoft Docs
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
- IDebugEngineLaunch2::LaunchSuspended
helpviewer_keywords:
- IDebugEngineLaunch2::LaunchSuspended
ms.assetid: 5dd2643e-c20a-470e-9024-2a423eb39856
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8fe234359d864f5df3ae568b8f3ec0c55c0ee9ff
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697396"
---
# <a name="idebugenginelaunch2launchsuspended"></a>IDebugEngineLaunch2::LaunchSuspended
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugEngineLaunch2::LaunchSuspended](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugenginelaunch2-launchsuspended).  
  
Bu yöntem, hata ayıklama altyapısı (DE) yoluyla bir işlem başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 [in] İşlemi başlatmak makinenin adı. Null değeri, yerel makine belirtmek için kullanın.  
  
 `pPort`  
 [in] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) program çalışacaktır bağlantı noktasını temsil eden arabirim.  
  
 `pszExe`  
 [in] Başlatılacak yürütülebilir dosya adı.  
  
 `pszArgs`  
 [in] Yürütülebilir dosyaya geçirilecek bağımsız değişkenler. Hiçbir bağımsız değişken varsa, null değeri olabilir.  
  
 `pszDir`  
 [in] Yürütülebilir dosya tarafından kullanılan çalışma dizininin adı. Çalışma dizini yok gerekiyorsa null değeri olabilir.  
  
 `bstrEnv`  
 [in] Ek bir NULL Sonlandırıcı tarafından izlenen, NULL ile sonlandırılmış dizeler ortam bloğu.  
  
 `pszOptions`  
 [in] Yürütülebilir dosya için Seçenekler.  
  
 `dwLaunchFlags`  
 [in] Belirtir [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md) bir oturum için.  
  
 `hStdInput`  
 [in] Alternatif bir giriş akışına işleyin. Yeniden yönlendirme gerekmiyorsa 0 olabilir.  
  
 `hStdOutput`  
 [in] Alternatif bir çıkış akışına işleyin. Yeniden yönlendirme gerekmiyorsa 0 olabilir.  
  
 `hStdError`  
 [in] Diğer hata çıkış akışına işleyin. Yeniden yönlendirme gerekmiyorsa 0 olabilir.  
  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) hata ayıklayıcı olayları alan nesnesi.  
  
 `ppDebugProcess`  
 [out] Sonuç döndürür [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) başlatılan işlem temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Normalde, [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] kullanarak bir programı başlatan [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) yöntemi ve ardından hata ayıklayıcıyı askıya alınan programa ekler. Ancak, hata ayıklama altyapısı gerekebilir (örneğin hata ayıklama altyapısı yorumlayıcıyı bir parçasıdır ve hata ayıklanan programa yorumlanan bir dildir,), bir program bu durumda başlatmak koşullar vardır [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] kullanan `IDebugEngineLaunch2::LaunchSuspended` yöntemi .  
  
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md) yöntemi askıya alınmış durumda işlemi başarıyla başlatıldı sonra işlemini başlatmak üzere çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [LAUNCH_FLAGS](../../../extensibility/debugger/reference/launch-flags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)   
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)

