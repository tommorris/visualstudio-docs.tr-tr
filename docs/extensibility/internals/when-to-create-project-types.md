---
title: "Proje türleri oluşturmak ne zaman | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: project types, conditions for creating
ms.assetid: 26adc860-ee4a-4f5c-95e1-e41b207dd7e6
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b532ad4e72fb15cd9409c362259347f6f3833d2e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="when-to-create-project-types"></a>Proje türleri oluşturma zamanı
Yeni proje türü oluşturma sağlayan bir temel özelleştirmek için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kullanıcılarınız için. Ancak, yeni bir proje türü oluşturulması için tüm gerekli değildir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] özelleştirmeleri. Aşağıdaki yönergeler yeni bir proje türü senaryonuz için gerekip gerekmediğini belirlemenize yardımcı olmalıdır.  
  
## <a name="create-a-new-project-type"></a>Yeni bir proje türü oluşturma  
 Özelleştirmek istiyorsanız, bir proje türü oluşturmalısınız [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bir veya daha fazla aşağıdaki yollardan davranmak üzere:  
  
-   Derlemede katılmak, dağıtımı, yapılandırmaları ve kaynak denetimi.  
  
-   Hata ayıklama desteği sunar.  
  
-   Proje öğeleri görüntülemek **Çözüm Gezgini**.  
  
-   Kullanım **Proje Aç** veya **yeni proje** iletişim kutusu.  
  
-   Proje iç içe geçme destekler.  
  
## <a name="extend-an-existing-project-type"></a>Varolan bir proje türünü genişletme  
 Kullanabileceğiniz yeni bir proje türü oluşturmak isteyebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] değiştirin veya varolan bir proje türü davranışını genişletmek için aşağıdaki yollarla, örneğin, derleme işlemi için değiştirme [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] projeleri:  
  
-   Birden çok dosya ile tek bir birim olarak çalışır.  
  
-   Tek bir dosya alt öğelerinin hiyerarşi olarak görüntüler.  
  
-   Bir komut içerik düzenleyicileri geçici görüntüler.  
  
-   Bir hizmet bağlamı için düzenleyicileri görüntüler.  
  
## <a name="use-an-existing-project-type"></a>Varolan bir proje türünü kullanın  
 Yeni proje oluşturma bazen gerekli değildir. Aşağıdaki tablo için bir proje türü oluşturmak zorunda değildir görevler gösterilmektedir.  
  
|Görev|Açıklama|  
|----------|-----------------|  
|Komutları işleme|Tüm VSPackage komutları işleyebilir.|  
|Bir düzenleyici oluşturma|Özel düzenleyiciler kaydedilebilir. Daha fazla bilgi için bkz: [belge pencereleri ve düzenleyicileri](http://msdn.microsoft.com/en-us/603625e1-62b6-413a-bc44-089346e166bc).|  
|Windows yapamaz|Yeni bir proje türü eklemeden araç ve belge pencereleri oluşturabilirsiniz.|  
|Özellikler penceresini özelliklerinde gösterme|Tüm nesneler özellikler getirebilir.|  
  
## <a name="create-a-project-subtype"></a>Proje alt oluşturma  
 Yeni bir proje türü oluşturmak zorunda kalmadan bir yönetilen projenin türü genişletmek için proje subtypes kullanabilirsiniz. Proje subtypes Microsoft yazılan yönetilen projeleri genişletmek için COM toplama kullanmak [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] veya [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]. COM toplama ile yönetilen projenin sistem uygulaması çoğunu yeniden ve toplama ve arabirimleri destekleyen kullanımı aracılığıyla belirli bir senaryo için hala özelleştirebilirsiniz. Proje alt türleri hakkında daha fazla bilgi için bkz: [proje Subtypes](../../extensibility/internals/project-subtypes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge pencereleri ve düzenleyiciler](http://msdn.microsoft.com/en-us/603625e1-62b6-413a-bc44-089346e166bc)   
 [Denetim listesi: Yeni proje türleri oluşturma](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Visual Studio'da hiyerarşileri](../../extensibility/internals/hierarchies-in-visual-studio.md)