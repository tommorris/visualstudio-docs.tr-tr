---
title: "Genel Bakış etki alanına özgü dil araçları kullanıcı arabirimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.dsldesigner.editor
helpviewer_keywords: Domain-Specific Language Tools, user interface
ms.assetid: 81ae6b35-6819-41d0-953b-6b4ed81f9227
caps.latest.revision: "25"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: d76ed4d14e7333678fcf927dfa1b2f21d8573be5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>Etki Alanına Özgü Dil Araçları Kullanıcı Arabirimine Genel Bakış
İlk açtığınızda bir etki alanına özgü dil Araçları (DSL araçları) çözümde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], kullanıcı arabirimi aşağıdaki resme benzeyecektir.  
  
 ![DSL Tasarımcısı](../modeling/media/dsl_designer.png "dsl_designer")  
  
 Aşağıdaki tabloda, UI parçalarını nasıl kullanılacağını açıklar.  
  
|**Öğesi**|**Tanım**|  
|-----------------|--------------------|  
|Diyagram|Etki alanı modeli diyagramını gösterir.<br /><br /> Diyagramı iki kenara sahiptir. Sütunlardan, modellerinde öğeleri türlerini tanımlar. Diğer taraftaki Modellerinizi ekranda nasıl görüneceğini tanımlar.|  
|Araç Kutusu|Araçlar etki alanı sınıfları ekleme ve türleri diyagrama şekil araç çubuğuna sürükleyin. İlişkileri, bağlayıcılar ve Şekil eşlemeler eklemek için Aracı'nı tıklatın, sonra diyagramda kaynak düğümü tıklatın ve ardından hedef düğüm.|  
|DSL Gezgini|**DSL Explorer** DSL tanımı etkin pencereyi olduğunda görüntülenir. Raporda DSL ağaç olarak gösterilir. DSL Explorer diyagramı görüntülenmez model özelliklerini düzenlemenize olanak tanır. Örneğin, araç kutusu öğelerini ekleme ve doğrulama işlemi üzerinde kullanarak geçiş **DSL Explorer**.|  
|DSL Ayrıntıları penceresi|**DSL ayrıntıları** pencere öğeleri nasıl görüntüleneceğini ve öğeleri nasıl kopyalanır ve Silinen denetlemenize izin modelinin öğeleri etki alanının özelliklerini gösterir.<br /><br /> -Varsayılan olarak, **DSL ayrıntıları** penceresi görünür yanına **hata listesi** ve **çıkış** windows.|  
  
## <a name="the-domain-model-diagram"></a>Etki alanı modeli diyagramı  
 Etki alanı modeli diyagramını iki bölüme ayrılmıştır. Diyagramın bir yan modeldeki öğeleri ve ilişkileri gösterir. Diğer taraftaki nasıl model görüntülenecek gösterilir ve öğeleri ve model diyagramı özelliklerini görüntülemek için kullanılan şekiller içerir. Aşağıdaki resimde diyagram öğelerini gösterir.  
  
 ![kulvarlı DSL Tasarımcısı](../modeling/media/dsl_desinger.png "dsl_desinger")  
  
 Aşağıdaki tabloda bazı etki alanı model diyagramı öğeleri açıklanır.  
  
|**Terim**|**Tanım**|  
|--------------|--------------------|  
|Etki alanı sınıfı|Etki alanı sınıflarını Modellerinizi öğelerinde türleridir.<br /><br /> Bir etki alanı sınıf bir şemada birden fazla ilişkisinin hedefidir birden çok kez görüntülenebilir.<br /><br /> Bir etki alanı sınıf eklemek için etki alanı sınıfı aracından sürükleyin **araç** için **sınıflar ve ilişkiler** yan diyagramı.|  
|Etki alanı ilişkisi|Etki alanı ilişkilerini Modellerinizi öğeler arasında bağlantılar türleridir.<br /><br /> Bir *katıştırma ilişkisi* hedef öğe sahip olduğu veya kaynak öğesi tarafından bulunan gösterir ve düz bir çizgi olarak görünür. Model bir ağaç forms bir modeldeki her öğe bir katıştırma ilişki hedefi olmalıdır. A *başvuru ilişkisi* model öğeleri arasında genel bir bağlantı gösterir ve kesikli bir çizgi olarak görünür. Herhangi bir öğe referans bağlantıları herhangi bir sayıda olabilir.<br /><br /> Aracı tıklayarak bir ilişki Oluştur **araç**, kaynak etki alanı sınıf tıklattıktan sonra hedef sınıf tıklatarak.|  
|Şekiller ve bağlayıcılar|Bağlayıcılar satırlarını ilişkileri görüntülemek için kullanılan bir DSL diyagramda belirlemek, nasıl model öğelerini bir DSL diyagramı. görüntülenmesi gerekir şekiller belirtin.<br /><br /> Şekil veya bağlayıcısı oluşturmak için aracı sürükleyin **diyagramı öğeleri** yan diyagramı.|  
|Şekil eşlemeleri|Bir şekli harita bir satıra bir şekli bağlama gösterir, etki alanı sınıfı için etki alanı model diyagramı veya görüntülediği etki alanı ilişkisinin bir bağlayıcı olarak görünür.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları genel bakış](../modeling/overview-of-domain-specific-language-tools.md)   
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)   
 [Özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md)