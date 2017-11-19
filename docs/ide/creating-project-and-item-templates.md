---
title: "Proje ve öğe şablonları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [Visual Studio], projects
- item templates, about item templates
- templates [Visual Studio], item
- Visual Studio templates, item
- Visual Studio templates, about templates
- project templates [Visual Studio], about project templates
- Visual Studio templates, project
- templates [Visual Studio], about templates
ms.assetid: a6ce501a-699b-4e3e-ade8-c81895645c20
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7d95781c2c5c4370e09c13b382016b015ec1a0d5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-project-and-item-templates"></a>Proje ve öğe şablonları oluşturma
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Proje ve öğe şablonları, bazı temel kod ve kendi amaçları için kullanabilecekleri yapısı kullanıcılara vermek yeniden kullanılabilir saplamalar sağlar.  
  
## <a name="visual-studio-templates"></a>Visual Studio şablonları  
 Bir dizi önceden tanımlanmış proje ve öğe şablonları yüklediğinizde yüklenen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Ve [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] kullanılabilir olan Windows Forms uygulaması ve sınıf kitaplığı şablonları **yeni proje** iletişim kutusunda proje şablonları bir örnekleridir. Yüklü öğe şablonları kullanılabilir **Yeni Öğe Ekle** iletişim kutusuna ve kod dosyaları, XML dosyalarını, HTML sayfaları ve stil sayfalarını gibi öğeleri içerir.  
  
 Bu şablonlar, kullanıcıların proje oluşturma ve genişleyen geçerli projeleri başlamak bir başlangıç noktası sağlar. Proje şablonları belirli proje türü için gerekli olan dosyalar sağlamak, standart derleme başvurularını içerir ve varsayılan proje özelliklerini ve derleyici seçeneklerini ayarlama. Öğe şablonları tek içeriyor, örneğin bir çok dosyalı öğe için doğru dosya adı uzantısına sahip boş dosya, saplama koda sahip kaynak kodu dosyaları, Tasarımcı bilgi dosyaları ve katıştırılmış kaynakları karmaşıklığı aralığında değişebilir.  
  
 Yüklü Şablonlar, ek olarak **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları, kendi şablonları veya indirme ve topluluk tarafından oluşturulan kullanım şablonları yazabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md) ve [nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md).  
  
## <a name="contents-of-a-template"></a>Bir şablon içeriği  
 Tüm proje ve öğe şablonlarını, ile birlikte yüklü olup olmadığını [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] veya tarafından oluşturulan, işlev aynı ilkeleri kullanarak ve benzer içeriğe sahip. Tüm şablonları aşağıdaki öğeleri içerir:  
  
-   Şablon kullanıldığında, oluşturulan dosyalar. Bu, kaynak kodu dosyaları, katıştırılmış kaynakları, proje dosyalarını vb. içerir.  
  
-   Bir .vstemplate dosyası. Bu dosya sağlar meta veriler içeriyor. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şablonda görüntülemek için gereken bilgileri **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları ve bir proje oluşturun veya gelen öğesi Şablon. .Vstemplate dosyaları hakkında daha fazla bilgi için bkz: [şablon parametreleri](../ide/template-parameters.md).  
  
 Bu dosyaları bir .zip dosyasına sıkıştırılmış ve doğru klasöre yerleştirin [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bunları otomatik olarak görüntüler. Proje şablonları görünür **My şablonları** bölümünü **yeni proje** iletişim kutularını ve öğe şablonları görünür **Yeni Öğe Ekle** iletişim kutuları. Şablon klasörleri hakkında daha fazla bilgi için bkz: [nasıl yapılır: bulun ve düzenleme şablonlarını](../ide/how-to-locate-and-organize-project-and-item-templates.md).  
  
## <a name="starter-kits"></a>Başlangıç Paketleri  
 Başlangıç paketleri diğer topluluk üyeleriyle paylaşılabilir Gelişmiş şablonlarıdır. Starter Kit, belgeleri ve yararlı, gerçek uygulamaları derleme oluştururken yeni araçları ve programlama tekniklerinin öğrenin kullanıcılara yardımcı olmak için diğer kaynakları derle kod örnekleri içerir. Temel içeriğini ve yordamlar başlangıç paketleri için şablonlar olanlarla aynıdır. Daha fazla bilgi için bkz: [nasıl yapılır: başlangıç paketleri oluşturma](../ide/how-to-create-starter-kits.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md)   
 [Nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md)   
 [Şablon parametreleri](../ide/template-parameters.md)   
 [Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)   
 [Nasıl yapılır: başlangıç paketleri oluşturma](../ide/how-to-create-starter-kits.md)