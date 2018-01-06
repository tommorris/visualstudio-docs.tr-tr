---
title: "Kaynak denetimi tümleştirmesine genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], about source control
ms.assetid: 3a46e4eb-e677-49c3-8647-d927d035a19a
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dd7b6a48b00e8bef62ff801519fc35cdc163902d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="source-control-integration-overview"></a>Kaynak denetimi tümleştirmesine genel bakış
Bu bölümde, Visual Studio kaynak denetimine tümleştirmek için iki yol karşılaştırır; Kaynak denetimi eklenti ve yeni kaynak denetimi özellikleri vurgular ve kaynak denetimi çözümü sağlayan bir VSPackage. Visual Studio kaynak denetimi VSPackages ve kaynak denetimi eklentiler arasında elle değiştirme yanı sıra çözüm tabanlı otomatik geçiş yapmanın sağlar.  
  
## <a name="source-control-integration"></a>Kaynak denetimi tümleştirmesi  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]iki tür kaynak denetimi tümleştirmesi seçeneği destekler. Tüm sürümlerinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], hala bir eklenti kaynak denetim eklentisi (daha önce de MSSCCI API adlandırılır), Visual Studio kaynak denetimi kullanıcı arabirimi (kullanırken temel kaynak denetim işlevselliği sağlayan API göre tümleştirebilirsiniz UI). Kaynak denetimi VSPackage, diğer yandan, bir yeni, derin tümleştirme sağlar [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] yüksek düzeyde açıdan çok yönlülük ve kendi kaynak denetimi modelinde otonomisi talep kaynak denetimi tümleştirmesi için uygun yolu.  
  
 ![Kaynak denetimine genel bakış](../../extensibility/internals/media/sourcectnrloverview.gif "SourceCtnrlOverview")  
  
## <a name="source-control-plug-in"></a>Kaynak Denetimi Eklentisi  
 Visual Studio tüm sürümleri, kaynak denetim eklentisi API Belirtimi sürüm 1.2 tümleştirme yolu olarak destekler. Kaynak Denetim eklentisi uygulayan açıklandığı gibi kaynak denetimi tümleştirmesi ve kayıt için kaynak denetimi eklentisi API işlevleri uygulayan DLL Yazar [kaynak denetim eklentisi oluşturma](../../extensibility/internals/creating-a-source-control-plug-in.md). Bu yaklaşımda, tümleşik geliştirme ortamı (IDE) kullanan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] iade, checkout, Araçlar/Seçenekler özellik sayfaları, araç çubukları ve kaynak denetimi karakterlerin gibi iletişim kutuları için kullanıcı Arabirimi. Kaynak Denetim eklentisi API katı bağlılığı Visual Studio ve sorunsuz bir deneyim kullanıcı için bir kolay tümleştirme oluşturmasını sağlar. Bu eklenti kaynak denetimi API'si ayrıntılı geri aramalar ve işlevleri çoğunu uygulamalıdır anlamına gelir.  
  
 Kaynak Denetim eklentisi API kullanarak eklenti bir kaynak denetimi için şu adımları izleyin:  
  
1.  Belirtilen işlevler uygulayan DLL oluşturma [kaynak denetimi eklentileri](../../extensibility/source-control-plug-ins.md).  
  
2.  Uygun kayıt defteri girdileri yaparak DLL'yi kaydetme (açıklanan [nasıl yapılır: kaynak denetimi eklentisi yükleme](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)).  
  
3.  Yardımcıyı kullanıcı Arabirimi ve kaynak denetimi bağdaştırıcı paketi (kaynak denetimi işlevlerinin kaynak denetim eklentileri aracılığıyla işleyen Visual Studio bileşeni) tarafından istendiğinde görüntü oluşturma  
  
 Komutuna yanıt olarak bir kaynak denetimi, Visual Studio IDE temel işlemleri için standart bir kullanıcı Arabirimi sunar ve daha sonra bilgileri için kaynak denetimi eklenti kaynak denetim eklentisi API tanımlanan işlevler aracılığıyla geçirir. Gelişmiş Seçenekler için kaynak denetimi eklenti üzerinde kendi Arabirim sunmak için örneğin, kaynak denetimindeki bir proje için gözatma çağrılabilir. Bu kullanıcının kaynak denetimiyle ilgilenirken UI iki farklı olması olası stilleri ile gelebilir anlamına gelir: Visual Studio sunan UI ve eklenti kaynak denetimi sunan UI. Gelişmiş kaynak denetimi işlemleri ile en dikkat çeken budur.  
  
### <a name="drawbacks-to-implementing-a-source-control-plug-in"></a>Kaynak denetimi eklenti uygulamak için dezavantajları  
  
-   Gelişmiş özellikler için olası Karışıklığı önlemek için önde gelen kullanıcı arabirimleri, iki farklı türlerde görebilirsiniz.  
  
-   Kaynak Denetim Eklentisi Kaynak Denetim eklentisi API tarafından kapsanan kaynak denetim modeli için sınırlıysa.  
  
-   Kaynak Denetim eklentisi API bazı kaynak denetimi senaryoları için çok kısıtlayıcı olabilir.  
  
### <a name="advantages-to-implementing-a-source-control-plug-in"></a>Kaynak Denetim eklentisi uygulama avantajları  
  
-   Potansiyel olarak karmaşık UI uygulamak kaynak denetimi eklenti yok böylece visual Studio tüm temel kaynak denetimi işlemleri için tüm kullanıcı Arabirimi sağlar.  
  
-   Katı API nedeniyle eklenti kaynak denetimi taşımalarına daha kapsamlı işlevsellik sağlamak için dış kaynak denetimi programlarla etkileşime; Visual Studio çok çok nasıl kaynak denetim işlevselliği, yalnızca o kaynak denetim eklentisi API'sine göre gerçekleştirilir yapıldığını ilgilenmez.  
  
-   Kaynak denetimi kaynak denetimden VSPackage eklenti uygulamanız daha kolaydır.  
  
## <a name="source-control-vspackage"></a>Kaynak denetimi VSPackage  
 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]Kaynak denetimi işlevlerin tam denetim ve Visual Studio tarafından sağlanan kaynak denetimi kullanıcı arabiriminin tam değiştirme Visual Studio uygulamasına derin tümleştirme sağlar. Kaynak denetimi VSPackage Visual Studio ile kayıtlı ve kaynak denetimi işlevsellik sağlar. Visual Studio ile birkaç kaynak denetimi VSPackages kaydedilebilir rağmen yalnızca bunlardan birinin herhangi bir zamanda etkin olabilir. Etkin durumdayken kaynak denetimi VSPackage Visual Studio'da kaynak denetim işlevleri ve görünüm üzerinde tam denetime sahiptir. Tüm diğer kaynak denetimi sistemde kayıtlı VSPackages etkin değildir ve herhangi bir UI hiç görüntülemez.  
  
 Kaynak denetimi VSPackage uygulama "tümü veya hiçbiri" stratejisi gerektirir. Kaynak denetimi VSPackage oluşturan bir dizi kaynak denetim arabirimleri ve yeni kullanıcı Arabirimi öğeleri (iletişim kutuları, menüleri ve araç çubuklarını) tüm kaynak denetim işlevselliği karşılamak üzere uygulamaya çaba önemli miktarda yatırım gerekir. Bkz: [kaynak denetimi VSPackage oluşturma](../../extensibility/internals/creating-a-source-control-vspackage.md) daha fazla ayrıntı için.  
  
### <a name="drawbacks-to-implementing-a-source-control-vspackage"></a>Kaynak denetimi VSPackage uygulamak için dezavantajları  
  
-   VSPackage başarıyla Visual Studio ile tümleştirmek için karmaşık arabirimleri sayısı uygulamalıdır.  
  
-   VSPackage kaynak denetimi için gerekli tüm UI sağlamanız gerekir; Visual Studio bu alandaki hiçbir Yardım sağlar.  
  
-   Kaynak denetimi VSPackage içkin şekilde Visual Studio'ya bağlıdır ve tek başına programlarla işlevselliğini kolayca dış bir kaynak denetimi program sürümü ile paylaşılamaz şekilde çalışamaz.  
  
### <a name="advantages-to-implementing-a-source-control-vspackage"></a>Kaynak denetimi VSPackage uygulama avantajları  
  
-   Kaynak denetimi UI üzerinde tam denetim ve işlevselliği VSPackage sahip olduğundan, kullanıcının kaynak denetimi için sorunsuz bir arabirim sunulur.  
  
-   Belirli kaynak denetim modeli için VSPackage sınırlı değildir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak denetimi](../../extensibility/internals/source-control.md)   
 [Kaynak Denetimi Eklentisi oluşturma](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [Kaynak denetimi VSPackage oluşturma](../../extensibility/internals/creating-a-source-control-vspackage.md)   
 [Kaynak Denetimindeki Yenilikler](../../extensibility/internals/what-s-new-in-source-control.md)