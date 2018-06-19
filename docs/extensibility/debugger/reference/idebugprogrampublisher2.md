---
title: IDebugProgramPublisher2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramPublisher2
helpviewer_keywords:
- IDebugProgramPublisher2 interface
ms.assetid: b1d17f63-7146-4076-a588-034cfc6858b9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3f927a3215a415745c2e9004573810101c229ab5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31119565"
---
# <a name="idebugprogrampublisher2"></a>IDebugProgramPublisher2
Bu arabirim, hata ayıklama altyapısı (DE) veya hata ayıklama için programlar kaydetmek için özel bir bağlantı noktası Üreticiler verir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugProgramPublisher2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Visual Studio birden çok işlem hata ayıklama için görünür yapmak için ayıklanacak programları kaydetmek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 COM'ın arama `CoCreateInstance` ile işlev `CLSID_ProgramPublisher` elde etmek için bu arabirimi (örneğe bakın). SE veya özel bir bağlantı noktası tedarikçi ayıklanacak programları temsil eden program düğümleri kaydetmek için bu arabirimi kullanır.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Bu arabirim, aşağıdaki yöntemlerden uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)|Bir program düğümü DEs ve oturum için hata ayıklama Yöneticisi (SDM) kullanılabilmesini sağlar.|  
|[UnpublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogramnode.md)|Böylece artık kullanılabilir bir program düğümü kaldırır.|  
|[PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md)|Bir program DEs ve SDM kullanılabilmesini sağlar.|  
|[UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)|Artık kullanılabilir olması için bir program kaldırır.|  
|[SetDebuggerPresent](../../../extensibility/debugger/reference/idebugprogrampublisher2-setdebuggerpresent.md)|Bir hata ayıklayıcısı mevcut olduğunu belirten bir bayrak ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim programları ve program düğümleri kullanılabilir hale getirir (diğer bir deyişle, "kendilerini DEs ve oturum hata ayıklama Yöneticisi'ni (SDM) tarafından kullanılması için yayımlayan"). Yayımlanmış programları ve program düğümleri erişmek için [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) arabirimi. Bu, Visual Studio bir program ayıklanacak tanıyabilmesi için tek yoludur.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>Örnek  
 Bu örnek, program yayımcı örneği oluşturmak ve bir program düğümü kaydetmek gösterilmektedir. Bu öğretici alınır [Program düğüm yayımlama](http://msdn.microsoft.com/en-us/d0100e02-4e2b-4e72-9e90-f7bc11777bae).  
  
```cpp  
// This is how m_srpProgramPublisher is defined in the class definition:  
// CComPtr<IDebugProgramPublisher2> m_srpProgramPublisher.  
  
void CProgram::Start(IDebugEngine2 * pEngine)  
{  
    m_spEngine = pEngine;  
  
    HRESULT hr = m_srpProgramPublisher.CoCreateInstance(CLSID_ProgramPublisher);  
    if ( FAILED(hr) )  
    {  
        ATLTRACE("Failed to create the program publisher: 0x%x.", hr);  
        return;  
    }  
  
    // Register ourselves with the program publisher. Note that  
    // CProgram implements the IDebgProgramNode2 interface, hence  
    // the static cast on "this".  
    hr = m_srpProgramPublisher->PublishProgramNode(  
        static_cast<IDebugProgramNode2*>(this));  
    if ( FAILED(hr) )  
    {  
        ATLTRACE("Failed to publish the program node: 0x%x.", hr);  
        m_srpProgramPublisher.Release();  
        return;  
    }  
  
    ATLTRACE("Added program node.\n");  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)