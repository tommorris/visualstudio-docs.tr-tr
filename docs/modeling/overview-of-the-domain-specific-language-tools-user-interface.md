---
title: Etki Alanına Özgü Dil Araçları Kullanıcı Arabirimine Genel Bakış
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.editor
helpviewer_keywords:
- Domain-Specific Language Tools, user interface
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 8ab473e4835e4ba6467a9af83e69bfabc43e8236
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748731"
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>Etki Alanına Özgü Dil Araçları Kullanıcı Arabirimine Genel Bakış
İlk açtığınızda bir etki alanına özgü dil Araçları (DSL araçları) çözümde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], kullanıcı arabirimi aşağıdaki resme benzeyecektir.

 ![DSL Tasarımcısı](../modeling/media/dsl_designer.png)

 Aşağıdaki tabloda, UI parçalarını nasıl kullanılacağını açıklar.

|**Öğesi**|**Tanım**|
|-----------------|--------------------|
|Diyagram|Etki alanı modeli diyagramını gösterir.<br /><br /> Diyagramı iki kenara sahiptir. Sütunlardan, modellerinde öğeleri türlerini tanımlar. Diğer taraftaki Modellerinizi ekranda nasıl görüneceğini tanımlar.|
|Araç Kutusu|Araçlar etki alanı sınıfları ekleme ve türleri diyagrama şekil araç çubuğuna sürükleyin. İlişkileri, bağlayıcılar ve Şekil eşlemeler eklemek için Aracı'nı tıklatın, sonra diyagramda kaynak düğümü tıklatın ve ardından hedef düğüm.|
|DSL Gezgini|**DSL Explorer** DSL tanımı etkin pencereyi olduğunda görüntülenir. Raporda DSL ağaç olarak gösterilir. DSL Explorer diyagramı görüntülenmez model özelliklerini düzenlemenize olanak tanır. Örneğin, araç kutusu öğelerini ekleme ve doğrulama işlemi üzerinde kullanarak geçiş **DSL Explorer**.|
|DSL Ayrıntıları penceresi|**DSL ayrıntıları** pencere öğeleri nasıl görüntüleneceğini ve öğeleri nasıl kopyalanır ve Silinen denetlemenize izin modelinin öğeleri etki alanının özelliklerini gösterir.<br /><br /> -Varsayılan olarak, **DSL ayrıntıları** penceresi görünür yanına **hata listesi** ve **çıkış** windows.|

## <a name="the-domain-model-diagram"></a>Etki alanı modeli diyagramı
 Etki alanı modeli diyagramını iki bölüme ayrılmıştır. Diyagramın bir yan modeldeki öğeleri ve ilişkileri gösterir. Diğer taraftaki nasıl model görüntülenecek gösterilir ve öğeleri ve model diyagramı özelliklerini görüntülemek için kullanılan şekiller içerir. Aşağıdaki resimde diyagram öğelerini gösterir.

 ![kulvarlı DSL Tasarımcısı](../modeling/media/dsl_desinger.png)

 Aşağıdaki tabloda bazı etki alanı model diyagramı öğeleri açıklanır.

|**Terim**|**Tanım**|
|--------------|--------------------|
|Etki alanı sınıfı|Etki alanı sınıflarını Modellerinizi öğelerinde türleridir.<br /><br /> Bir etki alanı sınıf bir şemada birden fazla ilişkisinin hedefidir birden çok kez görüntülenebilir.<br /><br /> Bir etki alanı sınıf eklemek için etki alanı sınıfı aracından sürükleyin **araç** için **sınıflar ve ilişkiler** yan diyagramı.|
|Etki alanı ilişkisi|Etki alanı ilişkilerini Modellerinizi öğeler arasında bağlantılar türleridir.<br /><br /> Bir *katıştırma ilişkisi* hedef öğe sahip olduğu veya kaynak öğesi tarafından bulunan gösterir ve düz bir çizgi olarak görünür. Model bir ağaç forms bir modeldeki her öğe bir katıştırma ilişki hedefi olmalıdır. A *başvuru ilişkisi* model öğeleri arasında genel bir bağlantı gösterir ve kesikli bir çizgi olarak görünür. Herhangi bir öğe referans bağlantıları herhangi bir sayıda olabilir.<br /><br /> Aracı tıklayarak bir ilişki Oluştur **araç**, kaynak etki alanı sınıf tıklattıktan sonra hedef sınıf tıklatarak.|
|Şekiller ve bağlayıcılar|Bağlayıcılar satırlarını ilişkileri görüntülemek için kullanılan bir DSL diyagramda belirlemek, nasıl model öğelerini bir DSL diyagramı. görüntülenmesi gerekir şekiller belirtin.<br /><br /> Şekil veya bağlayıcısı oluşturmak için aracı sürükleyin **diyagramı öğeleri** yan diyagramı.|
|Şekil eşlemeleri|Bir şekli harita bir satıra bir şekli bağlama gösterir, etki alanı sınıfı için etki alanı model diyagramı veya görüntülediği etki alanı ilişkisinin bir bağlayıcı olarak görünür.|

## <a name="see-also"></a>Ayrıca Bkz.

- [Etki Alanına Özgü Dil Araçlarına Genel Bakış](../modeling/overview-of-domain-specific-language-tools.md)
- [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
- [Etki Alanına Özgü Dili Özelleştirme ve Genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md)