---
title: Proje Fabrikalarını kullanarak proje örnekleri oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project factories
- projects [Visual Studio SDK], project factories
ms.assetid: 94c90012-8669-459c-af8e-307ac242c8c4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b3a59eee6701caf0b4d3b56df273b280f8bf6ece
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131762"
---
# <a name="creating-project-instances-by-using-project-factories"></a>Proje Fabrikalarını kullanarak proje örnekleri oluşturma
Proje türleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kullanan bir *proje Fabrika* proje nesnelerinin örneklerini oluşturmak için. Bir proje fabrikası cocreatable COM nesneleri için bir standart sınıf üreteci benzer. Ancak, proje nesneleri cocreatable değildir: Bunlar yalnızca bir proje fabrikası kullanarak oluşturulabilir.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE çağıran bir kullanıcı var olan bir proje yükler veya yeni bir proje oluşturur, VSPackage uygulanan proje Fabrika [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Yeni Proje nesnesi Çözüm Gezgini doldurmak için yeterli bilgi IDE sağlar. Yeni Proje nesnesi IDE tarafından başlatılan tüm ilgili UI eylemlerini desteklemek için gerekli arabirimleri de sağlar.  
  
 Uygulayabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> projenizi sınıfındaki arabirimi. Genellikle, kendi modülünde yer alıyor.  
  
 Bir örnek uygulaması için `IVsProjectFactory` bulunan PrjFac.cpp bkz arabirim [temel proje](http://msdn.microsoft.com/en-us/385fd2a3-d9f1-4808-87c2-a3f05a91fc36) örnek dizin.  
  
 Bir sahibi tarafından toplanan destek projeleri kendi proje dosyası sahibi anahtarında kalıcı gerekir. Zaman <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> yöntemi bir sahibi anahtarla bir proje üzerinde çağrılır, ait proje sahibi anahtarıyla GUID sonra çağıran bir proje fabrikası dönüştürür `CreateProject` gerçek oluşturma yapmak için bu proje fabrika yöntemi.  
  
## <a name="creating-an-owned-project"></a>Bir ait projesi oluşturma  
 Bir sahip iki aşamada ait bir proje oluşturur:  
  
1.  Çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.PreCreateForOwner%2A> yöntemi. Bu giriş denetleme üzerinde göre toplanmış proje nesne oluşturmak için bir fırsat ait proje verir `IUnknown`. İç ait proje geçirir `IUnknown` ve tekrar sahibi projeye toplanmış nesnesi. Bu ait proje iç depolamak için bir fırsat verir `IUnknown`.  
  
2.  Çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A> yöntemi. Bu yöntemi çağırmak yerine çağrıldığında tüm örneklemesi ait proje mu `IVsProjectFactory::CreateProject` değil ait projeleri söz konusu olduğu gibi. Giriş `VSOWNEDPROJECTOBJECT` numaralandırması genellikle toplanmış ait proje. Ait proje proje nesnesi zaten oluşturulmuş olup olmadığını belirlemek için bu değişkeni kullanabilirsiniz (tanımlama bilgisi eşit değil NULL) veya (tanımlama bilgisi eşittir NULL) oluşturulması gerekir.  
  
 Proje türleri, benzersiz bir projeye GUID, benzer bir cocreatable COM nesnesi CLSID değerine göre tanımlanır. Genellikle, bir proje Fabrika olması mümkündür rağmen tek proje türü örneklerini oluşturmaya bir proje Fabrika tanıtıcıları birden fazla proje türü GUID işleyin.  
  
 Proje türleri, belirli dosya adı uzantısı ile ilişkilendirilir. Bir kullanıcı var olan bir proje dosyayı açmaya çalıştığında veya bir şablon kopyalayarak yeni bir proje oluşturma girişimi, IDE karşılık gelen proje GUID belirlemek için dosya uzantısı kullanır.  
  
 Yeni bir proje oluşturun gerekir veya belirli bir türdeki varolan projeyi açın olup olmadığını IDE bilgileri [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0\Projects] altında sistem kayıt defterinde hangi bulmak için kullandığı IDE belirler hemen VSPackage gerekli proje Fabrika uygular. IDE bu VSPackage yükler. İçinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> yöntemi, VSPackage kaydetmeniz gerekir, proje Fabrika IDE ile çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes.RegisterProjectType%2A> yöntemi.  
  
 Birincil yöntemi `IVsProjectFactory` arabirimi <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> , iki senaryo işlemek: Varolan projeyi açarak ve yeni proje oluşturma. Çoğu projeleri proje durumlarına proje dosyasında depolar. Yeni Proje şablonu dosyasının bir kopyasını geçirilen yapma tarafından genellikle, oluşturulan `CreateProject` yöntemi ve kopyayı açma. Mevcut projeleri ait örneklerin tarafından geçirilen proje dosyasını açarak doğrudan `CreateProject` yöntemi. `CreateProject` Yöntemi gerektiği kullanıcıya ek kullanıcı Arabirimi özelliklerini görüntüleyebilirsiniz.  
  
 Bir proje ayrıca hiçbir dosya kullanabilir ve bunun yerine, bir veritabanı veya Web sunucusu gibi dosya sistemi dışındaki bir depolama mekanizmasını proje durumu depolayın. Bu durumda, dosya adı geçirilen parametre `CreateProject` yöntemi gerçekte bir dosya sistemi yoluna ancak benzersiz bir dize değil — bir URL — proje verileri tanımlamak için. Geçirilen şablon dosyalarını kopyalamak gerekmez `CreateProject` yürütülecek uygun yapım dizisi tetiklemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes>   
 [Denetim Listesi: Yeni Proje Türleri Oluşturma](../../extensibility/internals/checklist-creating-new-project-types.md)