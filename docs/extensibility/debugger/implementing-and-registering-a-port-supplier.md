---
title: "Uygulama ve bir bağlantı noktası Tedarikçi kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], registering port suppliers
- port suppliers, registering
ms.assetid: fb057052-ee16-4272-8e16-a4da5dda0ad4
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fa7378493c8df41b70be6fda17b2763f90fd7f04
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="implementing-and-registering-a-port-supplier"></a>Uygulama ve bir bağlantı noktası Tedarikçi kaydetme
Bağlantı noktası tedarikçi izlemek ve sırayla işlemlerini yönetmek bağlantı noktalarını tedarik rolüdür. Bir bağlantı noktası oluşturulmalıdır aynı anda bağlantı noktası sağlayıcı bağlantı noktası tedarikçi GUID (oturum hata ayıklama Yöneticisi [SDM] bağlantı noktası sağlayıcınızla seçilen kullanıcı ya da proje sistem tarafından belirtilen bağlantı noktası tedarikçi kullanırsınız) CoCreate kullanarak örneği. SDM sonra çağıracak [CanAddPort](../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) herhangi bir bağlantı eklenen olmadığını görmek için. Bir bağlantı noktası eklenebilir, yeni bir bağlantı noktası çağırarak istenen [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) ve onu bir [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) bağlantı noktası açıklar. `AddPort`tarafından temsil edilen yeni bir bağlantı noktası döndürülecek bir [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) arabirimi.  
  
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
 [Bağlantı noktası Üreticiler](../../extensibility/debugger/port-suppliers.md)