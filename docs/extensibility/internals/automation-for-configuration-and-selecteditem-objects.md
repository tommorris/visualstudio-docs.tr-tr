---
title: Otomasyon için yapılandırma ve SelectedItem nesneleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], SelectedItem object
- automation [Visual Studio SDK], builds
ms.assetid: 120377f1-51aa-4445-b2f7-06ab7fc2b47f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4d4ac269664136aed51542e53900ffc1c87f21fe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="automation-for-configuration-and-selecteditem-objects"></a>Otomasyon için yapılandırma ve SelectedItem nesneleri
Derleme ve seçilen öğeyi işlemlerini otomatik hale getirebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="automation-for-builds"></a>Otomasyon için derlemeleri  
 Derleme veya yapılandırma sahip uyguladığınızda, sağlanan bir otomasyon modeli <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider>. Daha fazla bilgi için bkz: [derleme yapılandırmalarını anlama](../../ide/understanding-build-configurations.md).  
  
 Bir VSPackage oluşturma ve yapılandırma seçeneklerini denetlemek istiyorsanız, otomasyon modeli kullanmanız gerekir.  
  
## <a name="automation-for-selecteditem"></a>Otomasyon SelectedItem için  
 İçin bir uygulama sunmak gerekmez `SelectedItem` Visual Studio standart bir uygulaması içerdiğinden nesne. Ancak, uygulayabilirsiniz `SelectedItem` tercih ederseniz nesne. İçeren bir nesne uygulamalıdır `SelectedItem` arabirim ve bir çağrı yanıt dönmek <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> VSITEMID yöntemiyle kümesine <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A>   
 [Otomasyon modeli katkıda bulunan](../../extensibility/internals/contributing-to-the-automation-model.md)   
 [Derleme Yapılandırmalarını Anlama](../../ide/understanding-build-configurations.md)