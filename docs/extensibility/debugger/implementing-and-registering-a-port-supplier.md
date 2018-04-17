---
title: Uygulama ve bir bağlantı noktası Tedarikçi kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], registering port suppliers
- port suppliers, registering
ms.assetid: fb057052-ee16-4272-8e16-a4da5dda0ad4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 54d6a4ab90b5ad169c5c940f52322dfd9b4974a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="implementing-and-registering-a-port-supplier"></a>Uygulama ve bir bağlantı noktası Tedarikçi kaydetme
Bağlantı noktası tedarikçi izlemek ve sırayla işlemlerini yönetmek bağlantı noktalarını tedarik rolüdür. Bir bağlantı noktası oluşturulmalıdır aynı anda bağlantı noktası sağlayıcı bağlantı noktası tedarikçi GUID (oturum hata ayıklama Yöneticisi [SDM] bağlantı noktası sağlayıcınızla seçilen kullanıcı ya da proje sistem tarafından belirtilen bağlantı noktası tedarikçi kullanırsınız) CoCreate kullanarak örneği. SDM sonra çağıracak [CanAddPort](../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) herhangi bir bağlantı eklenen olmadığını görmek için. Bir bağlantı noktası eklenebilir, yeni bir bağlantı noktası çağırarak istenen [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) ve onu bir [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) bağlantı noktası açıklar. `AddPort` tarafından temsil edilen yeni bir bağlantı noktası döndürülecek bir [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) arabirimi.  
  
## <a name="discussion"></a>Tartışma  
 Bir bağlantı noktası, bir makine ya da hata ayıklama sunucusuyla ilişkilendirilmiş bir bağlantı noktası tedarikçi tarafından oluşturulur. Bir sunucu bağlantı noktası tedarikçileri aracılığıyla numaralandırabilir[EnumPortSuppliers](../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md) yöntemi ve bağlantı noktası sağlayıcı üzerinden bağlantı noktalarını listeleme [EnumPorts](../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) yöntemi.  
  
 Tipik COM kayıt ek olarak, bir bağlantı noktası tedarikçi kendisi ile Visual Studio belirli kayıt defteri konumunda CLSID ve adını koyarak kaydetmeniz gerekir. Hata ayıklama SDK yardımcı işlevini çağırdı `SetMetric` Bu işler: her öğe, bu nedenle kaydedilmesi bir kez çağrılır:  
  
```cpp  
SetMetric(metrictypePortSupplier,  
          <GUID of your port supplier>,  
          metricCLSID,  
          <CLSID of your port supplier>,  
          false,  
          NULL)  
SetMetric(metrictypePortSupplier,  
          <GUID of your port supplier>,  
          metricName,  
          <name of your port supplier>,  
          false,  
          NULL);  
```  
  
 Bir bağlantı noktası tedarikçiye kendini çağırarak kaydını siler `RemoveMetric` (başka bir hata ayıklama SDK yardımcı işlevi), böylece kaydedildiği her bir öğe için bir kez:  
  
```cpp  
RemoveMetric(metrictypePortSupplier,  
             <GUID of your port supplier>,  
             metricCLSID,  
             NULL);  
RemoveMetric(metrictypePortSupplier,  
             <GUID of your port supplier>,  
             metricName,  
             NULL);  
```  
  
> [!NOTE]
>  [Hata ayıklama için SDK Yardımcıları](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) `SetMetric` ve `RemoveMetric` dbgmetric.h içinde tanımlanan ve ad2de.lib derlenmiş statik işlevleri. `metrictypePortSupplier`, `metricCLSID`, Ve `metricName` Yardımcıları de dbgmetric.h tanımlanır.  
  
 Bir bağlantı noktası sağlayıcının adını ve GUID yöntemlerle sağlayabilir [GetPortSupplierName](../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md) ve [GetPortSupplierId](../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)sırasıyla.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir bağlantı noktası sağlayıcı uygulama](../../extensibility/debugger/implementing-a-port-supplier.md)   
 [Hata ayıklama için SDK Yardımcıları](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Bağlantı Noktası Sağlayıcıları](../../extensibility/debugger/port-suppliers.md)