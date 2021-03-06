---
title: Şekiller ve Bağlayıcıları Tanımlama
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: db80cada3f49c8ba6488af31f399373457017c18
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31949429"
---
# <a name="defining-shapes-and-connectors"></a>Şekiller ve Bağlayıcıları Tanımlama
Bir etki alanına özgü dil (DSL) şemada hakkındaki bilgileri görüntülemek için kullanılan şekiller birkaç temel tür vardır.

##  <a name="shapeTypes"></a> Şekilleri ve bağlayıcıları temel türleri
 Koleksiyonu DSL diyagramda gösterilmektedir *şekiller* çizgilerle birbirine veya *Bağlayıcılar*.  Genellikle, ancak her zaman:

-   Şekilleri model öğelerini görünür gösterimi ' dir.

-   Bağlayıcılar başvuru ilişkileri temsil eder.

-   Diyagram model kök örneğini temsil eder.

-   Model öğelerini katıştırma ilişkiler kapsamlarına göre gösterilir. Örneğin, bileşen bağlantı noktalarını temsil eden öğeleri bileşeni katıştırılır.

 Bu düzenleri uygulanmaz, ancak daha güçlü desteklenir. DSL tasarlarken, katıştırma ilişkileri tasarımını olması gereken de hesaba katılmalıdır nasıl model ekranda sunmak istediğiniz tarafından etkiler. Bunun aksine, başvuru ilişkileri iş etki alanınızın kavramlarını yansıtmalıdır.

 Şekilleri aşağıdaki türleri kullanılabilir:

|Şekil türü|Açıklama|
|----------------|-----------------|
|Geometri şekli|Genel amaçlı dikdörtgen veya Oval şekli. Metin ve simge dekoratörler belirli konumları şeklin sınırlarına göre görüntüleyebilirsiniz.<br /><br /> Geometri şekiller içindeki şekiller yerleştirmek için bkz: [iç içe geçme şekiller](../modeling/nesting-shapes.md).|
|Bölme şekli|Üstbilgi ve bir UML sınıfı gibi bölmeler içeren dikdörtgen. Her bölme metin satır listesini içerebilir.<br /><br /> Satırları genellikle şeklin temsil ettiği öğe altında katıştırılmış öğeleri temsil eder. Örneğin, DSL sınıf diyagramları çözüm şablonu oluşturun.|
|Resim şekli|Bir görüntüyü gösteren şekil.|
|Bağlantı noktası şekli|Başka bir şekil anahattına eklemek için tasarlanmış bir küçük dikdörtgen. Genellikle, bileşen modellerinde kullanılır.<br /><br /> Bir bağlantı noktası tarafından temsil edilen model öğesi, genellikle üst şeklin temsil ettiği öğe altında katıştırılır. Örneğin, DSL bileşenleri çözüm şablonu kullanarak oluşturun.<br /><br /> Varsayılan olarak, bir bağlantı noktası şekli üst tarafı kaydırabilirsiniz. Belirli bir konuma sınırlamak için bir sınır kural tanımlayabilirsiniz.<br /><br /> Çok küçük ve saydam bir bağlantı noktası şekli yaparak, bunu kendi üst şekli yüzey üzerinde bir sabit bağlantı noktası sağlamak için kullanabilirsiniz.|
|Kulvarları|Kulvarları diyagram yatay veya dikey kesimler halinde bölüm. Kulvar her zaman diğer şekiller diyagramdan altında kalır.<br /><br /> Model kökünde genellikle Kulvar model öğelerini üst öğe ve diğer öğeleri üzerlerinde üst öğe. Örneğin, DSL Görev akışı çözüm şablonu oluşturun.|
|Bağlayıcılar|Şekiller arasında genellikle çizilmiş satırları başvuru ilişkileri temsil eder. Seçenekler düz veya dikdörtgen çizgili bir bağlayıcı yapmak ve Ok ucunu farklı türde olması için ayarlayabilirsiniz.|

##  <a name="shapeInheritance"></a> Şekil devralma
 Bir şekli başka bir şekil devralabilirsiniz. Ancak, şekilleri aynı türde olmalıdır. Örneğin, yalnızca bir geometri şekli geometri şekle devralabilirsiniz. Devralınan şekilleri bölmeler ve bunların temel şeklin dekoratörler bulunur. Bağlayıcılar bağlayıcılardan devralabilirsiniz.