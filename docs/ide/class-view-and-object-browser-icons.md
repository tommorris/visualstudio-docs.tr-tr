---
title: Sınıf Görünümü ve Nesne Tarayıcısı simgeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- icons, in Object Browser
- signal icons
- Class View tool, symbols
- graphic symbols
- IntelliSense, icons
- icons, IntelliSense
- symbols, Object Browser icons
- Object Browser, icons in Class View
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4893b38ceed7709f6b306b0cb84da47f205c911f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="class-view-and-object-browser-icons"></a>Sınıf Görünümü ve Nesne Tarayıcısı simgeleri

**Sınıf Görünümü** ve **Nesne Tarayıcısı** kodu varlıkları, örneğin temsil eden simgeleri, ad alanları, sınıflar, işlevleri ve değişkenler görüntüler. Aşağıdaki tabloda gösterilmiştir ve simgeleri açıklar.

|Simge|Açıklama|Simge|Açıklama|
|----------|-----------------|----------|-----------------|
|![Namespace simgesi](../ide/media/vxnamespace_icon.gif "vxNamespace_Icon")|Ad Alanı|![Bildirim sembolü](../ide/media/vxmethod_icon.gif "vxMethod_Icon")|Yöntem veya işlevi|
|![Simge sınıf](../ide/media/vxclass_icon.gif "vxClass_Icon")|örneği|![İşleç simgesi](../ide/media/vxoperator_icon.gif "vxOperator_Icon")|İşleç|  
|![Lolipop arabirimi sembolü](../ide/media/vxinterface_icon.gif "vxInterface_Icon")|Arabirim|![Özellik simgesi](../ide/media/vxproperty_icon.gif "vxProperty_Icon")|Özellik|
|![Yapı simgesi](../ide/media/vxstruct_icon.gif "vxStruct_Icon")|Yapı|![Alan simgesi](../ide/media/vxfield_icon.gif "vxField_Icon")|Alan veya değişken|  
|![Birleşim simgesi](../ide/media/vxunion_icon.gif "vxUnion_Icon")|UNION|![Olay simgesi](../ide/media/vxevent_icon.gif "vxEvent_Icon")|Olay|  
|![Numaralandırma simgesi](../ide/media/vxenum_icon.gif "vxEnum_Icon")|Enum|![Sabit simgesi](../ide/media/vxconstant_icon.gif "vxConstant_Icon")|Sabit|  
|![Tür tanımı simgesi](../ide/media/vxtypedef_icon.gif "vxTypeDef_Icon")|TypeDef|![Öğe numaralandırma sembolü](../ide/media/vxenumitem_icon.gif "vxEnumItem_Icon")|Enum öğesi|  
|![Visual Studio modülü simgesi](../ide/media/vxmodule_icon.gif "vxModule_Icon")|Modül|![Eşleme öğesi sembolü](../ide/media/vxmapitem_icon.gif "vxMapItem_Icon")|Harita öğesi|  
|![Uzantı yöntemi simgesi](../ide/media/extensionmethod.gif "ExtensionMethod")|Genişletme yöntemi|![Bildirim sembolü](../ide/media/vxmethod_icon.gif "vxMethod_Icon")|Dış bildirimi|  
|![Sembol temsilci](../ide/media/vxdelegate_icon.gif "vxDelegate_Icon")|Temsilci|![Sınıf Görünümü ve nesne tarayıcısı için hata simgesi](../ide/media/erroricon.gif "ErrorIcon")|Hata|  
|![Özel durum simgesi](../ide/media/vxexception_icon.gif "vxException_Icon")|Özel Durum|![Şablon simgesi](../ide/media/vxtemplate_icon.gif "vxTemplate_Icon")|Şablon|  
|![Eşleme Sembolü](../ide/media/vxmap_icon.gif "vxMap_Icon")|eşleme|![Hata ünlem işareti sembolü](../ide/media/vxerror_icon.gif "vxError_Icon")|Bilinmiyor|  
|![Tür iletme simgesi](../ide/media/ob_type_forward.gif "ob_type_forward")|Tür iletme|||  

## <a name="signal-icons"></a>Sinyal simgeleri

Aşağıdaki sinyal simgeleri tüm önceki simgeleri uygulamak ve kendi erişilebilirlik gösterir.

|Simge|Açıklama|
|----------|-----------------|  
|\<Sinyal simge yok >|Ortak. Erişilebilen herhangi bir yerden bu bileşeni ve başvurduğu herhangi bir bileşeni.|  
|![Sinyal korumalı simgesi](../ide/media/vxsignal_icon_key.gif "vxSignal_Icon_Key")|Korumalı. Kapsayan sınıfı veya türü veya bunları içeren sınıf ya da türü türetilen erişilebilir.|  
|![Sinyal özel simge](../ide/media/vxsignal_icon_lock.gif "vxSignal_Icon_Lock")|Özel. Yalnızca içeren sınıf ya da türü erişilebilir.|  
|![Sinyal korumalı simgesi](../ide/media/vxsignal_icon_envelope.gif "vxSignal_Icon_Envelope")|Korumalı.|  
|![Sinyal arkadaş&#47;iç simge](../ide/media/vxsignal_icon_diamond.gif "vxSignal_Icon_Diamond")|Arkadaş/iç hata. Yalnızca proje erişilebilir.|  
|![Sinyal simgesi ok](../ide/media/vxsignal_icon_arrow.gif "vxSignal_Icon_Arrow")|Kısayol. Nesne için bir kısayol.|

> [!NOTE]
> Projenizi bir kaynak denetimi veritabanında varsa, ek sinyal simgeleri kaynak denetimi durumu göstermek için görüntülenen, gibi iade veya olabilir kullanıma alınmış.

## <a name="see-also"></a>Ayrıca bkz.

[Kod yapısını görüntüleme](../ide/viewing-the-structure-of-code.md)