---
title: IDebugContainerField::EnumFields | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugContainerField::EnumFields
helpviewer_keywords: IDebugContainerField::EnumFields method
ms.assetid: 9e5e681b-ad49-4c62-bd95-4afa11d61a57
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a262d2f4aa90bc9ae638fb6cfbfe8af605f2446a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcontainerfieldenumfields"></a>IDebugContainerField::EnumFields
Kapsayıcı alanlar için bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumFields(   
   FIELD_KIND         dwKindFilter,  
   FIELD_MODIFIERS    dwModifiersFilter,  
   LPCOLESTR          pszNameFilter,  
   NAME_MATCH         nameMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumFields(  
   enum_ FIELD_KIND      dwKindFilter,   
   enum_ FIELD_MODIFIERS dwModifiersFilter,   
   string                pszNameFilter,   
   NAME_MATCH            nameMatch,   
   out IEnumDebugFields  ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwKindFilter`  
 [in] Bir birleşimini [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) sabitleri sıralanması alanları seçin. Alan türleri depolama türlerini, sınıf veya ilkel veya belirli bilgileri gibi yerel, parametre veya "Bu" işaretçi gibi tanımlayabilirsiniz.  
  
 `dwModifiersFilter`  
 [in] Bir birleşimini [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) sabitleri sıralanması alanları seçin. Alan değiştiricilerini ortak veya özel ya da sanal, statik ya da son gibi depolama bilgileri gibi erişim izinlerini olabilir.  
  
 `pszNameFilter`  
 [in] Numaralandırılacak alanının adı. Tüm alanları döndürülecek ise bu boş bir değer olabilir.  
  
 `nameMatch`  
 [in] Arasında bir değer [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md) arama olup olmadığını denetler numaralandırması büyük küçük harfe duyarlı veya değil.  
  
 `ppEnum`  
 [out] Döndürür bir [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) alanlarının listesini temsil eden nesne. Alanı yoksa null değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Alanı yoksa başarılı olursa, S_OK veya S_FALSE döndürür. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `dwKindFilter`, `dwModifiersFilter`, Ve `pszNameFilter` parametreleri birleştirilebilir, örneğin, "MyMethod" adlı tüm genel sanal yöntemler seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)   
 [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)   
 [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md)