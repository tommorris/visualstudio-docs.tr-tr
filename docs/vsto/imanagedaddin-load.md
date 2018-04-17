---
title: IManagedAddin::Load | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 545560c5f02437925c2f93e9c6dc3113e1cddd0b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="imanagedaddinload"></a>IManagedAddin::Load
  Yönetilen bir VSTO Eklenti yüklendiğinde çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT Load([in] BSTR bstrManifestURL,   
             [in] IDispatch *pdispApplication);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*bstrManifestURL*|Bildirim için VSTO eklentisi için tam yolu.|  
|*pdispApplication*|VSTO Eklenti yüklenirken ana bilgisayar uygulamasını temsil eden IDispatch gösteren bir işaretçi.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntemi başarıyla tamamlanmış olup olmadığını belirten bir HRESULT değer.  
  
## <a name="remarks"></a>Açıklamalar  
 VSTO eklenti yardımcı olmak için kullanılan bilgileri sağlayan bir dosya (genellikle, bir XML dosyası) bildirimidir. Örneğin, bir bildirim VSTO eklenti derlemesi ve giriş noktası sınıfını VSTO Eklenti yüklendiğinde örneği oluşturmak için konumunu belirtebilirsiniz.  
  
 *BstrManifestURL* parametre değeri içeriyor `Manifest` HKEY_CURRENT_USER\Software\Microsoft\Office altında girdisi\\*\<uygulama adı >*\Addins\\*\<eklenti kimliği >* VSTO eklenti için kayıt defteri anahtarı. Daha fazla bilgi için bkz: [Imanagedaddin arabirimi](../vsto/imanagedaddin-interface.md).  
  
 Uygulama [IManagedAddIn::Load](../vsto/imanagedaddin-load.md) VSTO yüklenmekte eklenti için uygulama etki alanı ve güvenlik ilkesini yapılandırma gibi görevleri gerçekleştirmek için yöntem.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Imanagedaddin arabirimi](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)  
  
  