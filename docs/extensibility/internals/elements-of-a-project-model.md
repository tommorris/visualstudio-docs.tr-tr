---
title: Proje modeli öğeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], implementation considerations
- project models
- projects [Visual Studio SDK], elements
ms.assetid: a1dbe0dc-68da-45d7-8704-5b43ff7e4fc4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4933e73df93c1f8a3bcf62e03b6883c0096f1d8f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="elements-of-a-project-model"></a>Proje modeli öğeleri
Tüm projelerde uygulamaları ve arabirimleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] temel yapısını paylaşır: Proje türünüz için proje modeli. Geliştirdiğiniz VSPackage olan proje modelinde tasarım kararlarınızı ile uyumlu ve IDE tarafından sağlanan genel işlevselliği ile birlikte çalışma nesneleri oluşturun. Örneğin, bir proje öğesi nasıl kalıcı denetim karşın, bir dosya kalıcı gerekir bildirim kontrol. Ne zaman bir kullanıcı bir açık projeye öğe odağı yerleştirir ve seçer **kaydetmek** üzerinde **dosya** menüsünde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] menü çubuğunda, proje türü kodunuza gerekir IDE komuttan müdahale, dosya kalıcı hale getirmek ve bildirim dosyası artık değiştirilir IDE yeniden gönderin.  
  
 VSPackage IDE arabirimlerine erişim sağlayan hizmetler aracılığıyla IDE ile etkileşim kurar. Örneğin, belirli hizmetleri aracılığıyla, İzleyici ve rota komutları ve projesinde yapılan seçimleri bağlam bilgilerini sağlar. VSPackage için gereken tüm genel IDE işlevi Hizmetleri tarafından sağlanır. Hizmetler hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir hizmet elde](../../extensibility/how-to-get-a-service.md).  
  
 Diğer uygulama dikkate alınacak noktalar:  
  
-   Bir tek proje model birden fazla proje türü içerebilir.  
  
-   Proje türleri ve Katılımcısı proje fabrikalarını GUID'lerini aşağıdaki ile bağımsız olarak kaydedilir.  
  
-   Her proje bir şablon dosyası ya da bir kullanıcı ile yeni bir proje oluşturduğunda yeni proje dosyası başlatmak için Sihirbazı olmalıdır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] UI. Örneğin, [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] şablonları başlatma ne sonunda .vcproj dosyaları haline gelir.  
  
 Aşağıdaki çizimde, birincil arabirimleri, hizmetleri ve tipik bir proje uygulama oluştur nesneleri gösterir. Uygulama Yardımcısı, HierUtil7, arka plandaki nesneleri ve diğer programlama Demirbaş oluşturmak için kullanabilirsiniz. HierUtil7 uygulama Yardımcısı hakkında daha fazla bilgi için bkz: [yapı içinde değil: Proje türü (C++) uygulamak için HierUtil7 proje sınıflarını kullanarak](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346).  
  
 ![Visual Studio Proje Modeli grafiği](../../extensibility/internals/media/vsprojectmodel.gif "vsProjectModel")  
Proje modeli  
  
 Arabirimler ve önceki diyagramda listelenen hizmetleri ve diğer isteğe bağlı arabirimler diyagramda yer almayan hakkında daha fazla bilgi için bkz: [proje modeli çekirdek bileşenleri](../../extensibility/internals/project-model-core-components.md).  
  
 Projeleri komutları destekleyebilir ve bu nedenle uygulamalıdır <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> komutu içerikle GUID'ler komut yönlendirme içinde katılmak için arabirim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim listesi: Yeni proje türleri oluşturma](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Yapı içinde değil: Proje türü (C++) uygulamak için HierUtil7 proje sınıflarını kullanma](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346)   
 [Proje modeli çekirdek bileşenleri](../../extensibility/internals/project-model-core-components.md)   
 [Proje Fabrikalarını kullanarak proje örnekleri oluşturma](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)   
 [Nasıl yapılır: bir hizmeti Al](../../extensibility/how-to-get-a-service.md)   
 [Proje Türleri Oluşturma](../../extensibility/internals/creating-project-types.md)