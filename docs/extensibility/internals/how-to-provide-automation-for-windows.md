---
title: 'Nasıl yapılır: Windows için Otomasyon sağlar | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], tool windows
- tool windows, automation
ms.assetid: 512ab2a4-7987-4912-8f40-8804bf66f829
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: aa4b95a67adb4c282d90eafdd237776e7de1c911
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-provide-automation-for-windows"></a>Nasıl yapılır: Windows için Otomasyon sağlar
Belge ve aracı windows için Otomasyon sağlayabilir. Bir görev listesiyle yaptığı gibi sağlayarak Otomasyon Otomasyon nesneleri bir pencere üzerinde kullanılabilir hale getirmek istediğiniz ve ortamı hazır Otomasyon nesnesi zaten sağlamaz tavsiye edilir.

## <a name="automation-for-tool-windows"></a>Otomasyon için araç pencereleri
 Ortamı, standart bir döndürerek bir araç penceresinde Otomasyon sağlar <xref:EnvDTE.Window> nesne aşağıdaki yordamda açıklandığı gibi:

#### <a name="to-provide-automation-for-tool-windows"></a>Araç pencereleri Otomasyon sağlamak için

1.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> ortamıyla yöntemiyle <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> olarak `VSFPROPID` almak için parametre `Window` nesnesi.

2.  Araç pencerenizin VSPackage özel bir Otomasyon nesnesi çağıran isteğinde bulunduğunda <xref:EnvDTE.Window.Object%2A>, ortam çağrıları `QueryInterface` için `IExtensibleObject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>, veya `IDispatch` arabirimleri. Her ikisi de `IExtensibleObject` ve `IVsExtensibleObject` sağlayan bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject.GetAutomationObject%2A> yöntemi.

3.  Ortam sonra çağırdığında `GetAutomationObject` geçirme yöntemi `NULL`, geçirerek yanıt VSPackage özgü nesnenizin yedekleyin.

4.  Çağırma varsa `QueryInterface` için `IExtensibleObject` ve `IVsExtensibleObject` ortam çağırır sonra başarısız `QueryInterface` için `IDispatch`.

## <a name="automation-for-document-windows"></a>Belge pencereleri Otomasyon
 Standart bir <xref:EnvDTE.Document> nesnesi kullanılabilir ayrıca ortamından bir düzenleyici kendi uyarlamasını sahip olabilirsiniz, ancak <xref:EnvDTE.Document> uygulayarak nesne `IExtensibleObject` arabirimi ve yanıtlama `GetAutomationObject`.

 Ayrıca, bir düzenleyici üzerinden alınan VSPackage özgü Otomasyon nesnesi sağlayabilirsiniz <xref:EnvDTE.Document.Object%2A> uygulayarak yöntemi `IVsExtensibleObject` veya `IExtensibleObject` arabirimleri. [VSSDK örnekleri](http://aka.ms/vs2015sdksamples) RTF belge özgü Otomasyon nesneyi katkıda bulunur.

## <a name="see-also"></a>Ayrıca Bkz.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>