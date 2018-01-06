---
title: IManagedAddin::Load | Microsoft Docs
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: 
ms.assetid: 3faf9312-8ab4-4960-b2e7-8ca9859a3dcf
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 91a2909d407dbdc7629e189585333a3e4702483d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
  
  