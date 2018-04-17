---
title: POPLISTFUNC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- POPDIRLISTFUNC
helpviewer_keywords:
- POPLISTFUNC callback function
ms.assetid: b2199fd5-d707-4628-92dd-e2a01e2f507a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 950807b0568a28763b369fef4041c69b264d12fc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="poplistfunc"></a>POPLISTFUNC
Bu geri çağırma için sağlanan [SccPopulateList](../extensibility/sccpopulatelist-function.md) IDE tarafından ve kaynak denetimi eklentisi tarafından bir dosya veya dizinlerin listesini güncelleştirmek için kullanılır (Ayrıca için sağlanan `SccPopulateList` işlevi).  
  
 Bir kullanıcının ne zaman seçer **almak** komutu IDE'de IDE kullanıcı alabilirsiniz tüm dosyaların bir liste kutusu görüntüler. Ne yazık ki, IDE kullanıcı alabilirsiniz tüm dosyaların tam listesini bilmez; Bu liste yalnızca eklentiye sahiptir. Diğer kullanıcılar için kaynak kodu denetimi projesinde dosyaları eklediyseniz, bu dosyalar listede görünür, ancak IDE bunlarla ilgili bilmez. IDE kullanıcı alabilirsiniz düşündüğü dosyaların bir listesini oluşturur. Bu liste kullanıcıya görüntüler önce çağırır [SccPopulateList](../extensibility/sccpopulatelist-function.md) `,` eklenti kaynak denetimi vermiş eklemek ve listeden dosyaları silmek için bir fırsat.  
  
## <a name="signature"></a>İmza  
 Kaynak Denetim eklentisi aşağıdaki prototipe ile bir IDE uygulanan işlevini çağırarak listesini değiştirir:  
  
```cpp  
typedef BOOL (*POPLISTFUNC) (  
   LPVOID pvCallerData,  
   BOOL fAddRemove,  
   LONG nStatus,  
   LPSTR lpFileName  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 pvCallerData  
 `pvCallerData` Parametresi için (IDE) çağıran tarafından geçirilen [SccPopulateList](../extensibility/sccpopulatelist-function.md). Kaynak Denetim eklentisi bu parametrenin içeriği hakkında hiçbir şey varsayın.  
  
 fAddRemove  
 Varsa `TRUE`, `lpFileName` dosya listesine eklenmelidir bir dosyadır. Varsa `FALSE`, `lpFileName` dosya listesinden silinmiş bir dosyadır.  
  
 nStatus  
 Durumu `lpFileName` (bir birleşimini `SCC_STATUS` BITS; bkz: [dosya durum kodu](../extensibility/file-status-code-enumerator.md) Ayrıntılar için).  
  
 lpDosyaAdı  
 Dosya adı eklemek veya listeden silmek için tam dizin yolu.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`TRUE`|Eklenti bu işlev çağırma devam edebilirsiniz.|  
|`FALSE`|(Örneğin bellek durum dışı bir) IDE tarafında bir sorun oluştu. Eklenti işlem durdurmanız gerekir.|  
  
## <a name="remarks"></a>Açıklamalar  
 İsteğe bağlı olarak ekleyin veya dosya listesinden silmek için kaynak denetim eklentisi istediği her dosya için tümleştirilmesidir bu işlev çağrıları `lpFileName`. `fAddRemove` Bayrağı listesine eklemek için yeni bir dosya veya silmek için eski bir dosya gösterir. `nStatus` Parametre dosyanın durumunu verir. Eklenti SCC ekleme ve dosya silme sona erdiğinde arasında döndürür [SccPopulateList](../extensibility/sccpopulatelist-function.md) çağırın.  
  
> [!NOTE]
>  `SCC_CAP_POPULATELIST` Yetenek bit Visual Studio için gereklidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDE tarafından uygulanan geri arama işlevleri](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [Kaynak Denetim Eklentileri](../extensibility/source-control-plug-ins.md)   
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)   
 [Dosya durum kodu](../extensibility/file-status-code-enumerator.md)