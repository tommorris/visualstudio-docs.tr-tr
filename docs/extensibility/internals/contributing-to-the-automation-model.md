---
title: "Otomasyon modeli katkıda bulunan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: automation [Visual Studio SDK]
ms.assetid: 44de482d-93c8-41a4-843c-cefda995a03e
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5907f540e5f81e26b7d184352e3c38531ec5da66
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="contributing-to-the-automation-model"></a>Otomasyon modeli katkıda bulunan
Visual Studio ortamı özelleştirme için Otomasyon arabirimleri kümesi sağlar. Otomasyon modeli, son kullanıcıların Visual Studio eklentileri ve uzantıları oluşturma sağlayan nesne modelidir.  
  
 Ayrıca, sizin için uygun şekilde otomasyon modeli katkıda VSPackage geliştirici,; Bunu yaparak, son kullanıcılar, VSPackage eklentileri oluşturma ve genellikle, VSPackage kullandıklarında tutarlı bir kullanıcı modeli deneyimi sağlamak için etkinleştirme [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Böylece, VSPackage otomasyon modeli fikirlerinizi izler, VSPackage tasarlarken son kullanıcı deneyimi tutarlı hale getirmek için bir dizi yönergeleri izleyebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Otomasyon modeline genel bakış](../../extensibility/internals/automation-model-overview.md)  
 Otomasyon modeli ortak ortam ana modelleri kontrol nesnelerin ilgili gruplar tanımlar. Bu nesne kümesini otomasyon modeli şemada gösterilen.  
  
 [Otomasyon VSPackages için sağlama](../../extensibility/internals/providing-automation-for-vspackages.md)  
 Otomasyon için VSPackage sağlamak için iki ana yolu ele alınmaktadır.  
  
 [Proje nesneleri gösterme](../../extensibility/internals/exposing-project-objects.md)  
 VSPackage özgü nesneler oluşturmak için adım adım yönergeler sağlar.  
  
 [Proje Modelleme](../../extensibility/internals/project-modeling.md)  
 Yeni Proje türünüz için Otomasyon oluşturmak için gerekli olan standart proje nesneleri açıklar ve Proje Otomasyonu izleyen yol göstermektedir. Bu konu ayrıca listeleri bildirimleri ve uygulama için sınıflar sağlar.  
  
 [Olayları gösterme](../../extensibility/internals/exposing-events-in-the-visual-studio-sdk.md)  
 Otomasyon modeliniz için olaylar oluşturmak için adım adım yönergeler sağlar.  
  
 [Seçenekler sayfaları için Otomasyon desteği](../../extensibility/internals/automation-support-for-options-pages.md)  
 Özel bir VSPackage özelliklerini desteklemek için bir Otomasyon nesnesi döndürmeyi açıklar **seçenekleri** iletişim kutusundaki **aracı** genişletme tarafından menü `DTE.Properties` nesnesi.  
  
 [Otomasyon kodu için sağlama](../../extensibility/internals/providing-automation-for-code.md)  
 Kodunuz için bir otomasyon modeli oluşturma gerekli olmadığını açıklar. Bununla birlikte, kod modelleri içine ayrıntılı bilgiler sağlar, bu konudaki bir bağlantı sağladı.  
  
 [Nasıl yapılır: Windows için Otomasyon sağlar](../../extensibility/internals/how-to-provide-automation-for-windows.md)  
 Otomasyon sağlama iyi bir fikir Otomasyon nesneleri bir pencere üzerinde kullanılabilir hale getirmek istediğiniz ve ortamı hazır Otomasyon nesnesi zaten sağlamaz olduğunu anlatır. Araç pencereleri ve belge pencereleri için Otomasyon açıklanır.  
  
 [Otomasyon modelini kullanma](../../extensibility/internals/using-the-automation-model.md)  
 Bir Otomasyon tüketici ilk proje Otomasyon nesneleri nasıl alacağını Göster iki kod örnekleri sağlar.  
  
 [Otomasyon için yapılandırma ve SelectedItem nesneleri](../../extensibility/internals/automation-for-configuration-and-selecteditem-objects.md)  
 Otomasyon için yapılandırma seçeneklerini ve seçili öğeler için automation hakkında bilgi sağlar.  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>  
 Nasıl bir VSPackage DTE Otomasyon nesne modelinde katılan gösteren bir kod örneğini sağlar. Parametreler ve dönüş değerleri seçili açıklamalar listelenmektedir.  
  
## <a name="related-sections"></a>İlgili Bölümler