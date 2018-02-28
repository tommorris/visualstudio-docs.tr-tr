---
title: "Otomasyon modeli katkıda bulunan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK]
ms.assetid: 44de482d-93c8-41a4-843c-cefda995a03e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bb69380913f188031c97b46530ea2659fc05fe30
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="contributing-to-the-automation-model"></a>Otomasyon modeli katkıda bulunan
Visual Studio ortamı özelleştirme için Otomasyon arabirimleri kümesi sağlar. Otomasyon modeli, son kullanıcıların Visual Studio eklentileri ve uzantıları oluşturma sağlayan nesne modelidir.  
  
 Ayrıca, sizin için uygun şekilde otomasyon modeli katkıda VSPackage geliştirici,; Bunu yaparak, son kullanıcılar, VSPackage eklentileri oluşturma ve genellikle, VSPackage kullandıklarında tutarlı bir kullanıcı modeli deneyimi sağlamak için etkinleştirme [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Böylece, VSPackage otomasyon modeli fikirlerinizi izler, VSPackage tasarlarken son kullanıcı deneyimi tutarlı hale getirmek için bir dizi yönergeleri izleyebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Otomasyon Modeline Genel Bakış](../../extensibility/internals/automation-model-overview.md)  
 Otomasyon modeli ortak ortam ana modelleri kontrol nesnelerin ilgili gruplar tanımlar. Bu nesne kümesini otomasyon modeli şemada gösterilen.  
  
 [VSPackage’lar için Otomasyon Sağlama](../../extensibility/internals/providing-automation-for-vspackages.md)  
 Otomasyon için VSPackage sağlamak için iki ana yolu ele alınmaktadır.  
  
 [Proje Nesnelerini Kullanıma Sunma](../../extensibility/internals/exposing-project-objects.md)  
 VSPackage özgü nesneler oluşturmak için adım adım yönergeler sağlar.  
  
 [Proje Modelleme](../../extensibility/internals/project-modeling.md)  
 Yeni Proje türünüz için Otomasyon oluşturmak için gerekli olan standart proje nesneleri açıklar ve Proje Otomasyonu izleyen yol göstermektedir. Bu konu ayrıca listeleri bildirimleri ve uygulama için sınıflar sağlar.  
  
 [Olayları gösterme](../../extensibility/internals/exposing-events-in-the-visual-studio-sdk.md)  
 Otomasyon modeliniz için olaylar oluşturmak için adım adım yönergeler sağlar.  
  
 [Seçenekler Sayfaları için Otomasyon Desteği](../../extensibility/internals/automation-support-for-options-pages.md)  
 Özel bir VSPackage özelliklerini desteklemek için bir Otomasyon nesnesi döndürmeyi açıklar **seçenekleri** iletişim kutusundaki **aracı** genişletme tarafından menü `DTE.Properties` nesnesi.  
  
 [Kod için Otomasyon Sağlama](../../extensibility/internals/providing-automation-for-code.md)  
 Kodunuz için bir otomasyon modeli oluşturma gerekli olmadığını açıklar. Bununla birlikte, kod modelleri içine ayrıntılı bilgiler sağlar, bu konudaki bir bağlantı sağladı.  
  
 [Nasıl Yapılır: Windows için Otomasyon Sağlama](../../extensibility/internals/how-to-provide-automation-for-windows.md)  
 Otomasyon sağlama iyi bir fikir Otomasyon nesneleri bir pencere üzerinde kullanılabilir hale getirmek istediğiniz ve ortamı hazır Otomasyon nesnesi zaten sağlamaz olduğunu anlatır. Araç pencereleri ve belge pencereleri için Otomasyon açıklanır.  
  
 [Otomasyon Modelini Kullanma](../../extensibility/internals/using-the-automation-model.md)  
 Bir Otomasyon tüketici ilk proje Otomasyon nesneleri nasıl alacağını Göster iki kod örnekleri sağlar.  
  
 [Yapılandırma ve SelectedItem Nesneleri için Otomasyon](../../extensibility/internals/automation-for-configuration-and-selecteditem-objects.md)  
 Otomasyon için yapılandırma seçeneklerini ve seçili öğeler için automation hakkında bilgi sağlar.  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>  
 Nasıl bir VSPackage DTE Otomasyon nesne modelinde katılan gösteren bir kod örneğini sağlar. Parametreler ve dönüş değerleri seçili açıklamalar listelenmektedir.  
  
## <a name="related-sections"></a>İlgili Bölümler