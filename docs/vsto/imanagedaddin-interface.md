---
title: IManagedAddin arabirimi
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- IManagedAddin interface
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f29356a3e11634d742d6f6022c35cf8f10871eec
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="imanagedaddin-interface"></a>IManagedAddin arabirimi
  Uygulama yükleyen bir bileşen oluşturmak için Imanagedaddin arabirimi VSTO eklentileri yönetilen. Bu arabirim 2007 Microsoft Office sistemi eklendi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```c++
[  
    object,  
    uuid(B9CEAB65-331C-4713-8410-DDDAF8EC191A),  
    pointer_default(unique),  
    oleautomation  
]  
interface IManagedAddin : IUnknown  
{  
    HRESULT Load(  
        [in] BSTR bstrManifestURL,   
        [in] IDispatch *pdispApplication);  
    HRESULT Unload();  
};  
```  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda Imanagedaddin arabirimi tarafından tanımlanan yöntemler listelenmiştir.  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IManagedAddin::Load](../vsto/imanagedaddin-load.md)|Microsoft Office olduğunda çağrılır uygulama yönetilen bir VSTO eklenti yükler.|  
|[IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)|Yalnızca Microsoft Office önce çağrılır, yönetilen bir VSTO eklenti uygulamasını kaldırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 2007 Microsoft Office sistemi ile başlayarak, Microsoft Office uygulamaları Imanagedaddin arabirimi Office VSTO eklentileri yük yardımcı olması için kullanın. Kendi VSTO Eklenti Yükleyicisi oluşturmak için Imanagedaddin arabirimi uygulayabilirsiniz ve çalışma zamanı için VSTO VSTO Eklenti Yükleyicisi kullanmak yerine eklentileri, yönetilen (*VSTOLoader.dll*) ve [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Daha fazla bilgi için bkz: [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
## <a name="how-managed-add-ins-are-loaded"></a>Yönetilen eklentileri yüklenen nasıl  
 Bir uygulama başlatıldığında aşağıdaki adımlardan oluşur:  
  
1.  Uygulama, aşağıdaki kayıt defteri anahtarı altındaki girişleri arayarak VSTO eklentileri bulur:  
  
     **HKEY_CURRENT_USER\Software\Microsoft\Office\\_\<uygulama adı >_ \Addins\**  
  
     Her giriş bu kayıt defteri anahtarı altındaki bir VSTO eklentisinin benzersiz kimliğidir. Genellikle, bu VSTO eklenti derlemesi adıdır.  
  
2.  Uygulama arar bir `Manifest` her VSTO eklenti girdisinin altındaki girişi.  
  
     Yönetilen VSTO eklentileri yolun tamamı bir bildiriminin saklayabilir `Manifest` altında girdisi **HKEY_CURRENT_USER\Software\Microsoft\Office\\_\<uygulama adı >_ \Addins\\  _\<eklenti kimliği >_**. VSTO eklenti yardımcı olmak için kullanılan bilgileri sağlayan bir dosya (genellikle, bir XML dosyası) bildirimidir.  
  
3.  Uygulama bulursa bir `Manifest` girişi, uygulama çalıştığında bir yönetilen VSTO Eklenti Yükleyicisi bileşeni yüklenemiyor. Uygulama bu Imanagedaddin arabirimi uygulayan bir COM nesnesi oluşturmak deneyerek yapar.  
  
     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] VSTO Eklenti Yükleyicisi bileşeni içerir (*VSTOLoader.dll*), ya da tarafından kendi Imanagedaddin arabirimi uygulama oluşturabilirsiniz.  
  
4.  Uygulama çağrıları [IManagedAddin::Load](../vsto/imanagedaddin-load.md) yöntemi ve değerini geçişinde `Manifest` girişi.  
  
5.  [IManagedAddin::Load](../vsto/imanagedaddin-load.md) yöntemi VSTO VSTO yüklenmekte eklenti için uygulama etki alanı ve güvenlik ilkesini yapılandırma gibi eklentiyi yüklemek için gerekli görevleri gerçekleştirir.  
  
 VSTO eklentileri yönetilen bulmak ve yüklemek için Microsoft Office uygulamalarını kullanmaktadır anahtarları kayıt defteri hakkında daha fazla bilgi için bkz: [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).  
  
## <a name="guidance-to-implement-imanagedaddin"></a>Imanagedaddin uygulamak için kılavuz  
 Imanagedaddin uygularsanız, aşağıdaki CLSID kullanarak uygulaması içeren DLL kaydetmeniz gerekir:  
  
 99D651D7-5F7C-470E-8A3B-774D5D9536AC  
  
 Microsoft Office uygulamaları bu CLSID Imanagedaddin uygulayan COM nesnesi oluşturmak için kullanın.  
  
> [!CAUTION]  
>  Bu CLSID tarafından da kullanılan *VSTOLoader.dll* içinde [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Bu nedenle, kendi VSTO Eklenti Yükleyicisi ve çalışma zamanı bileşeni oluşturma Imanagedaddin kullanırsanız VSTO Bel eklentileri çalıştıran bilgisayarlara bileşeniniz dağıtamazsınız [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Yönetilmeyen API Başvurusu &#40;Visual Studio'da Office geliştirme&#41;](../vsto/unmanaged-api-reference-office-development-in-visual-studio.md)  
  
  