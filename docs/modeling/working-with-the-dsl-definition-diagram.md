---
title: "DSL tanımı diyagram ile çalışma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.diagram
- vs.dsltools.dsldesigner.dsldiagram
helpviewer_keywords:
- Domain-Specific Language Tools, diagram
- Domain-Specific Language Tools, Split Tree
- Domain-Specific Language Tools, Show Map Lines
- Domain-Specific Language Tools, Show As Class
- Domain-Specific Language Tools, Bring Tree Here
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5da1da2b7c74f6c95651eeb0120b213ad1e1d394
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="working-with-the-dsl-definition-diagram"></a>DSL Tanım Diyagramı ile Çalışma
Diyagramı bir [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] tanımı etki alanına özgü dil tanımlamak için önemli bir araçtır. Etki alanınızı öğelerine model ve diyagramı ilişkileri tanımlayın ve daha okunabilir yapmak için diyagramın düzenini değiştirebilirsiniz ekleyebilirsiniz.  
  
## <a name="the-layout-of-the-diagram"></a>Diyagramın düzenini  
 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] Tanımı diyagramı sahip iki bölüm **sınıflar ve ilişkiler** bölüm ve **diyagramı öğeleri** bölüm. **Sınıflar ve ilişkiler** bölüm, etki alanı sınıfları, etki alanı ilişkilerini ve devralma görüntüler. **Diyagramı öğeleri** bölüm şekil sınıfları, bağlayıcı sınıfları, Kulvar sınıfları ve oluşturulan Tasarımcısı Diyagramı görüntüler.  
  
 Etki alanı sınıflarını birden çok yerde görünebilir **sınıflar ve ilişkiler** bölümler. Katıştırma veya başvuru ilişkileri kaynak ise diğer etki alanı sınıfları ve ilişkileri ağacı için temel sınıf ise, bir etki alanı sınıf tanımı bir devralma ağacında görüntüler. Etki alanı sınıfı yer tutucuları katıştırma veya başvuru ilişkileri hedefleri olarak görünür. Varsayılan olarak, yer tutucu öğeleri ile görüntülenen **etki alanı özellikleri** daraltılmış bölme. Bunlar, devralma veya katıştırma veya başvuru ilişkileri gösterme.  
  
 Bir etki alanı sınıf eklediğinizde, alt kısmında görünür **sınıflar ve ilişkiler** bölüm. Bir katıştırma eklediğinizde veya ilişki başvuru altında ve kaynak etki alanı sınıfının sağındaki çizilir.  
  
 Etki alanı sınıfları ve ilişkileri eklediğinizde, belirli bir etki alanı sınıfı bulması zor olabilir. Sağ tıklayarak bir etki alanı sınıfı bulabilirsiniz **DSL Explorer** ve ardından **diyagramındaki bulun**.  
  
 Aşağıdaki bölümlerde okunmasını kolaylaştırmak için diyagram görünümünü nasıl değiştirebileceğiniz açıklanır.  
  
## <a name="copying-elements"></a>Öğeleri kopyalama  
 Kopya kullanın, kesin ve DSL tanımı diyagramdaki öğelerde yapıştırın.  
  
## <a name="zooming-in-or-out-on-the-diagram"></a>Diyagramda yakınlaştırma veya uzaklaştırma  
 Kullanarak veya diyagram uzaklaştırma yakınlaştırabilirsiniz **DSL Tasarımcısı** yakınlaştırma düzeyini ayarlamak için araç.  
  
## <a name="hiding-map-lines"></a>Gizleme eşleme satırları  
 Bir etki alanı sınıf veya etki alanı ilişkisinin ve şekli arasında çizilmiş satırları veya eşlenmiş bağlayıcı eşleme satırları markalarıdır. Tıklatarak eşleme satırları gizleyebilirsiniz **eşleme satırları göster** düğmesini **DSL Tasarımcısı** araç. Satırları göstermek için yeniden düğmesini tıklatın.  
  
## <a name="changing-the-diagram-layout"></a>Diyagram düzeni değiştirme  
 Düzenini değiştirebilirsiniz **sınıflar ve ilişkiler** gibi bölüm.  
  
### <a name="expandcollapse"></a>Genişlet/Daralt  
 Bir etki alanı sınıf veya bir şekli tıklattıktan sonra'ı tıklatarak temsil eden bir bölme şekli öğesi boyutunu küçültebilirsiniz **Daralt**. Bu gizler **etki alanı özellikleri** şeklin bölme. Göstermek için **etki alanı özellikleri** yeniden compartment, şekli sağ tıklatın ve ardından **genişletme**.  
  
### <a name="move-updown"></a>Yukarı/Aşağı Taşı  
 Öğeyi sağ tıklayarak ve ardından bölümünde bir etki alanı sınıfı ya da diyagram öğesi yukarı veya aşağı taşıyabilirsiniz **Yukarı Taşı** veya **Aşağı Taşı**. Katıştırma veya reference bir ilişki hedefi olarak görüntülenen bir yer tutucu öğesi taşırsanız, ilişki ile taşınır.  
  
### <a name="expandcollapse-relationships-tree"></a>İlişkileri ağaç Genişlet/Daralt  
 Bir etki alanı sınıf katıştırma veya reference ilişkilerinde diğer etki alanı sınıflarla Kaynak rolü yürütülürse, etki alanı sınıf tanımını sağ tıklayarak ve ardından ilişkileri gizleyebilirsiniz **Daralt ilişkileri ağaç**. İlişkileri göstermek için tanımı öğeye sağ tıklayın ve ardından **ilişkileri ağacı genişletin**.  
  
### <a name="expandcollapse-inheritance-tree"></a>Devralma ağacında Genişlet/Daralt  
 Bir etki alanı sınıf diğer etki alanı sınıfların temel sınıfı ise, etki alanı sınıf tanımını sağ tıklayarak ve ardından devralma ağacında gizleyebilirsiniz **Daralt devralma ağacında**. Devralma ağacında göstermek için tanımı öğeye sağ tıklayın ve ardından **genişletin devralma ağacında**.  
  
### <a name="bring-tree-here"></a>Buraya Ağacı Getir  
 Bir yer tutucu etki alanı sınıfına sağ tıklayarak ve ardından diyagramı birleştirebilir **getirin ağacı burada**. Yer tutucu etki alanı sınıf tanımı öğe haline gelir ve devralma ve ilişkileri ağaçları görüntüler. Bir ilişki veya bir devralma ilişkisi alt hedefi ise eski tanım öğesi bir yer tutucu öğe haline gelir; Aksi takdirde kaybolur.  
  
### <a name="split-tree"></a>Ağacı Böl  
 Bunları görüntüler etki alanı sınıf tanımını sağ tıklayarak ve ardından devralma veya ilişkiler ağaçları bölünebilir **bölünmüş ağaç**. Bir yer tutucu öğesi tanım öğesi olur ve tanımı etki alanı sınıf devralma ve ilişkileri ağaçları birlikte şimdi bölümünün altında görüntülenir.  
  
### <a name="show-as-class"></a>Sınıf Olarak Göster  
 Bir etki alanı ilişkisinin ilişkileri türetilmiş ya da diğer etki alanı ilişkilerini katıştırma veya başvuru ilişkileri varsa, ilişki bir sınıf olarak ilişki sağ tıklayarak ve ardından görüntüleyebileceğiniz **Göster sınıfı** . İlişki ile görüntülenen bir **etki alanı özellikleri** compartment ve devralma ve ilişkileri ağaçları gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)