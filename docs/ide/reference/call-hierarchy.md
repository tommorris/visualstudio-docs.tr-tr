---
title: Çağrı hiyerarşisi Visual Studio'da görüntüleme | Microsoft Docs
ms.custom: ''
ms.date: 01/10/2018
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.CallHierarchy
helpviewer_keywords:
- Call Hierarchy
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d18af9f159c663cb061a32a61343eaa0a14d7503
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="view-call-hierarchy"></a>Çağrı hiyerarşisini görüntüleme

Çağrı hiyerarşisi kodunuz için görüntüleyerek seçili yöntemi, özelliği veya oluşturucusu gelen ve giden tüm çağrıları gidebilirsiniz. Bu, kodu nasıl akacağını daha iyi anlamak ve koduna değişiklikler etkilerini değerlendirmek için sağlar. Yöntem çağrıları ve ek giriş noktaları koda karmaşık zincirleri görüntülemek üzere kod birkaç düzeyini inceleyebilirsiniz. Bu, tüm olası yürütme yollarını keşfetmek sağlar.

Visual Studio'da tasarım zamanında bir çağrı hiyerarşisi görüntüleyebilirsiniz. Başka bir deyişle, bir kesme noktası ayarlama ve çalıştırma çağrı yığınını görüntülemek için hata ayıklayıcı başlatmak zorunda değilsiniz.

## <a name="use-the-call-hierarchy-window"></a>Çağrı hiyerarşisi penceresini kullanma

Görüntülenecek **çağrı hiyerarşisi** penceresinde bir yöntemi, özelliği veya oluşturucu çağrısı adına sağ tıklayın ve ardından **görünüm çağrı hiyerarşisi**.

Üye adı bir ağaç görünümü bölmesinde görünür **çağrı hiyerarşisi** penceresi. Üye düğümünü genişletin, **çağrıları için** *üye adı* ve **çağrıları gelen** *üye adı* düğümlerinde görünür. Bu düğümler aşağıda gösterilmiştir **çağrı hiyerarşisi** penceresi.

![Çağrı hiyerarşisi tek bir düğüm açık](../../ide/reference/media/onenode.png "OneNode")

- Genişletirseniz **çağrıları için** düğümü, tüm üyeleri çağrısı seçilen üye görüntülenir.

- Genişletirseniz **çağrıları gelen** düğümü, seçili üyesi tarafından çağrılan tüm üyeleri görüntülenir.

Bu alt düğüm üyelerinin her biri daha sonra genişletebilirsiniz **çağrıları için** ve **çağrıları gelen** düğümleri. Bu, arayanlar, yığına gitmek aşağıdaki çizimde gösterildiği gibi sağlar.

![Çağrı hiyerarşisi birden çok düğümü açık](../../ide/media/multiplenodes.png "MultipleNodes")

Sanal ya da soyut olarak tanımlanmış bir üye için bir **geçersiz kılmaları yöntem adı** düğümü görüntülenir. Arabirim üyeleri için bir **uygulayan yöntem adı** düğümü görüntülenir. Bu Genişletilebilir düğümler aynı düzeyde görünür **çağrıları için** ve **çağrıları gelen** düğümleri.

**Arama kapsamı** araç kutusu içeren seçenekleri için **My çözüm**, **geçerli projenin**, ve **geçerli belge**.

Bir alt üye seçtiğinizde **çağrı hiyerarşisi** ağaç görünümü bölmesinde:

- **Çağrı hiyerarşisi** Ayrıntılar bölmesinde o alt üyenin üst üyeden çağrıldığı kod tüm satırları görüntüler.

- **Kod tanımı penceresi**, açık değilse, seçilen üye (yalnızca C++) için kodunu görüntüler. Bu pencere hakkında daha fazla bilgi için bkz: [kodunu yapısı görüntüleme](../../ide/viewing-the-structure-of-code.md).

> [!NOTE]
> Çağrı hiyerarşisi özelliği yöntemi, grup başvuruları, burada bir yöntem olay işleyici eklenir veya bir temsilciye atanmış basamak içeren bulmaz. Bir yöntem yapılan tüm başvuruları Bul için kullanabileceğiniz **tüm başvuruları Bul** komutu.

### <a name="shortcut-menu-items"></a>Kısayol menü öğeleri

Aşağıdaki tabloda, ağaç görünümü bölmesinde bir düğüm sağ tıklattığınızda, kullanılabilen birkaç kısayol menü seçenekleri açıklanmaktadır.

|Bağlam menüsü öğesini|Açıklama|
|-----------------------|-----------------|
|**Yeni bir kökü olarak Ekle**|Seçili düğümün ağaç görünümü bölmesinde yeni bir kök düğümü ekler. Bu, üzerinde belirli bir alt ağacı dikkat etmeniz odaklanmanıza olanak sağlar.|
|**Kök Kaldır**|Seçili kök düğümü ağaç görünümü bölmesindeki kaldırır. Bu seçenek, yalnızca bir kök düğümü kullanılabilir.<br /><br /> Aynı zamanda **kaldırmak kök** seçili kök düğümünü kaldırmak için araç çubuğu düğmesi.|
|**Tanıma gitme**|Tanıma Git komutu seçili düğüm üzerinde çalışır. Bu üye çağrısı için özgün tanımı veya değişken tanımını gider.<br /><br /> Tanıma Git komutu çalıştırmak için Seçili düğümün çift tıklatın veya seçili düğümde F12 tuşuna basın.|
|**Tüm başvuruları Bul**|Tüm başvuruları Bul komutu seçili düğüm üzerinde çalışır. Bu kod tüm satırları projenizde bu başvuru bir sınıf veya üye bulur.<br /><br /> SHIFT + F12, seçili düğümde tüm başvuruları Bul komutu çalıştırmak için de kullanabilirsiniz.|
|**Kopyala**|Seçili düğümün (ancak alt düğümlerini) içeriğini kopyalar.|
|**Yenileme**|Seçili düğümün daraltır. böylece yeniden genişletmeden geçerli bilgilerini görüntüler.|