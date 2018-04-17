---
title: Bir bağlantı noktası alma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ports, getting
- debugging [Debugging SDK], ports
ms.assetid: 745c2337-cfff-4d02-b49c-3ca7c4945c5e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6c20b3e3bdc2644e7af7d9a35de06af7f96d7680
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="getting-a-port"></a>Bir bağlantı noktası alma
Bir bağlantı noktası işlemleri çalışmakta olduğu bir makineye bağlantıyı temsil eder. Bu makine yerel veya uzak makineye olabilir (büyük olasılıkla çalışan Windows tabanlı bir işletim sistemi; bkz [bağlantı noktalarını](../../extensibility/debugger/ports.md) daha fazla bilgi için).  
  
 Bir bağlantı noktası tarafından temsil edilen [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) arabirimi. Bağlantı noktası bağlı makine üzerinde çalışan işlemler hakkında bilgi edinmek için kullanılır.  
  
 Hata ayıklama altyapısı program düğümleri bağlantı noktası ile kaydetmek için ve işlem bilgi isteklerini karşılamak için bir bağlantı noktası erişimi olmalıdır. Örneğin, hata ayıklama altyapısı uyguluyorsa [IDebugProgramProvider2](../../extensibility/debugger/reference/idebugprogramprovider2.md) arabirim, uygulamasını [GetProviderProcessData](../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) yöntemi bağlantı noktası için gerekli işlemi sorun Döndürülecek bilgi.  
  
 Bu bağlantı noktası listesinden bir bağlantı noktası tedarikçi alır ve Visual Studio hata ayıklama altyapısı için gereken bağlantı noktası sağlar. Bir program bağlı değilse (veya gelen hata ayıklayıcı içinde bir özel durum nedeniyle oluşturuldu, hangi sadece zamanında [JIT] iletişim kutusu tetikler), kullanıcının Aktarım (bağlantı noktası sağlayıcı için başka bir ad) Seçimi verilir. Aksi takdirde, kullanıcı hata ayıklayıcı programı başlarsa, proje sistemi kullanmak için bağlantı noktası tedarikçi belirtir. Visual Studio tarafından temsil edilen bağlantı noktası tedarikçi ya da bir olay başlatır bir [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) arabirimi ve yeni bir bağlantı noktası için çağırarak ister [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) ile bir [ IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) arabirimi. Bu bağlantı noktasını daha sonra bir formunda hata ayıklama altyapısı veya başka bir aktarılır.  
  
## <a name="example"></a>Örnek  
 Bu kod parçası, için sağlanan bağlantı noktasını kullanacak biçimde gösterilmiştir [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) program düğümünde kaydetmek için [ResumeProcess](../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md). Bu kavram doğrudan ilgili parametreler daha anlaşılır olması için atlandı.  
  
> [!NOTE]
>  Bu örnek başlatın ve işlemini sürdürmek için bağlantı noktasını kullanır ve varsayar [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md) arabirimi bağlantı noktası üzerinde gerçekleştirilir. Bu halinde bu görevleri gerçekleştirmek için tek yoludur ve bağlantı noktası bile dışında programın sağlamak için ilişkili olabilir değil, mümkündür [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) kendisine verilen.  
  
```cpp  
// This is an IDebugEngineLaunch2 method.  
HRESULT CDebugEngine::LaunchSuspended(/* omitted parameters */,  
                                      IDebugPort2 *pPort,  
                                      /* omitted parameters */,  
                                      IDebugProcess2**ppDebugProcess)  
{  
    // do stuff here to set up for a launch (such as handling the other parameters)  
    ...  
  
    // Now get the IPortNotify2 interface so we can register a program node  
    // in CDebugEngine::ResumeProcess.  
    CComPtr<IDebugDefaultPort2> spDefaultPort;  
    HRESULT hr = pPort->QueryInterface(&spDefaultPort);  
    if (SUCCEEDED(hr))  
    {  
        CComPtr<IDebugPortNotify2> spPortNotify;  
        hr = spDefaultPort->GetPortNotify(&spPortNotify);  
        if (SUCCEEDED(hr))  
        {  
            // Remember the port notify so we can use it in ResumeProcess.  
            m_spPortNotify = spPortNotify;  
  
            // Now launch the process in a suspended state and return the  
            // IDebugProcess2 interface  
            CComPtr<IDebugPortEx2> spPortEx;  
            hr = pPort->QueryInterface(&spPortEx);  
            if (SUCCEEDED(hr))  
            {  
                // pass on the parameters we were given (omitted here)  
                hr = spPortEx->LaunchSuspended(/* omitted paramters */,ppDebugProcess)  
            }  
        }  
    }  
    return(hr);  
}  
  
HRESULT CDebugEngine::ResumeProcess(IDebugProcess2 *pDebugProcess)  
{  
    // Make a program node for this process  
    HRESULT hr;  
    CComPtr<IDebugProgramNode2> spProgramNode;  
    hr = this->GetProgramNodeForProcess(pProcess, &spProgramNode);  
    if (SUCCEEDED(hr))  
    {  
        hr = m_spPortNotify->AddProgramNode(spProgramNode);  
        if (SUCCEEDED(hr))  
        {  
            // resume execution of the process using the port given to us earlier.  
           // (Querying for the IDebugPortEx2 interface is valid here since  
           // that's how we got the IDebugPortNotify2 interface in the first place.)  
            CComPtr<IDebugPortEx2> spPortEx;  
            hr = m_spPortNotify->QueryInterface(&spPortEx);  
            if (SUCCEEDED(hr))  
            {  
                hr  = spPortEx->ResumeProcess(pDebugProcess);  
            }  
        }  
    }  
    return(hr);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program kaydetme](../../extensibility/debugger/registering-the-program.md)   
 [Ayıklanacak bir Program etkinleştirme](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)   
 [Bağlantı noktası Üreticiler](../../extensibility/debugger/port-suppliers.md)   
 [Bağlantı Noktaları](../../extensibility/debugger/ports.md)