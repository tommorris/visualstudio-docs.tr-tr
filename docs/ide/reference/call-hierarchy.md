---
title: Bir yöntem çağrıları Bul
ms.date: 05/18/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.CallHierarchy
helpviewer_keywords:
- Call Hierarchy
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 52fdaf277d8c20801c5d48d90de472d24ab88bda
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="view-call-hierarchy"></a>Çağrı hiyerarşisini görüntüleme

Çağrı hiyerarşisi kodunuz için görüntüleyerek tüm çağrıları için ve bazı durumlarda, seçili yöntemi, özelliği veya oluşturucusu gidebilirsiniz. Bu, kodu nasıl akacağını daha iyi anlamak ve koduna değişiklikler etkilerini değerlendirmek için sağlar. Yöntem çağrıları ve ek giriş noktaları koda karmaşık zincirleri görüntülemek üzere kod birkaç düzeyini inceleyebilirsiniz. Bu, tüm olası yürütme yollarını keşfetmek sağlar.

Visual Studio'da tasarım zamanında bir çağrı hiyerarşisi görüntüleyebilirsiniz. Başka bir deyişle, bir kesme noktası ayarlama ve çalıştırma çağrı yığınını görüntülemek için hata ayıklayıcı başlatmak zorunda değilsiniz.

## <a name="use-the-call-hierarchy-window"></a>Çağrı hiyerarşisi penceresini kullanma

Görüntülenecek **çağrı hiyerarşisi** penceresinde Kod düzenleyicisinde yöntemi, özelliği veya oluşturucu çağrısı adını sağ tıklatın ve ardından **görünüm çağrı hiyerarşisi**.

Üye adı bir ağaç görünümü bölmesinde görünür **çağrı hiyerarşisi** penceresi. Üye düğümünü genişletin, **çağrıları için** *üye adı*ve C++ için **çağrıları gelen** *üye adı*, düğümlerinde görünür.

C++ kodu için çağrıları için hem bir üyeden görebilirsiniz:

![Visual Studio'da C++ kodu için çağrı hiyerarşisi](media/call-hierarchy-cpp.png)

C# ve Visual Basic kodu için bir üye çağrıları, ancak gelen çağrıları görebilirsiniz:

![C# kod Visual Studio için çağrı hiyerarşisi](media/call-hierarchy-csharp.png)

- Genişletirseniz **çağrıları için** düğümü, tüm üyeleri çağrısı seçilen üye görüntülenir.

- C++, f, genişletmek için **çağrıları gelen** düğümü, seçili üyesi tarafından çağrılan tüm üyeleri görüntülenir.

Ardından görmek için arama her üye genişletin, **çağrıları için**ve C++ için **çağrıları gelen** düğümleri. Bu, arayanlar, yığına gitmek aşağıdaki görüntüde gösterildiği gibi sağlar:

![Çağrı hiyerarşisi penceresi düzeylerinde genişletilmiş](media/call-hierarchy-csharp-expanded.png)

Sanal ya da soyut olarak tanımlanmış bir üye için bir **geçersiz kılmaları yöntem adı** düğümü görüntülenir. Arabirim üyeleri için bir **uygulayan yöntem adı** düğümü görüntülenir. Bu Genişletilebilir düğümler aynı düzeyde görünür **çağrıları için** ve **çağrıları gelen** düğümleri.

**Arama kapsamı** araç kutusu içeren seçenekleri için **My çözüm**, **geçerli projenin**, ve **geçerli belge**.

Bir alt üye seçtiğinizde **çağrı hiyerarşisi** ağaç görünümü bölmesinde:

- **Çağrı hiyerarşisi** Ayrıntılar bölmesinde o alt üyenin üst üyeden çağrıldığı kod tüm satırları görüntüler.

- **Kod tanımı** penceresi açık görüntüler kodu seçilen üye için (yalnızca C++). Bu pencere hakkında daha fazla bilgi için bkz: [kod yapısını görüntüleme](../../ide/viewing-the-structure-of-code.md).

> [!NOTE]
> **Çağrı hiyerarşisi** özelliği bulamazsa yöntemi grup başvuruları, burada bir yöntem olay işleyici eklenir veya bir temsilciye atanmış yerler içerir. Bir yöntem yapılan tüm başvuruları Bul için kullanabileceğiniz **tüm başvuruları Bul** komutu.

## <a name="shortcut-menu-items"></a>Kısayol menü öğeleri

Aşağıdaki tabloda, ağaç görünümü bölmesinde bir düğüm sağ tıklattığınızda, kullanılabilen birkaç kısayol menü seçenekleri açıklanmaktadır.

|Bağlam menüsü öğesini|Açıklama|
|-----------------------|-----------------|
|**Yeni bir kökü olarak Ekle**|Seçili düğümün ağaç görünümü bölmesinde yeni bir kök düğümü ekler. Bu, üzerinde belirli bir alt ağacı dikkat etmeniz odaklanmanıza olanak sağlar.|
|**Kök Kaldır**|Seçili kök düğümü ağaç görünümü bölmesindeki kaldırır. Bu seçenek, yalnızca bir kök düğümü kullanılabilir.<br /><br /> Aynı zamanda **kaldırmak kök** seçili kök düğümünü kaldırmak için araç çubuğu düğmesi.|
|**Tanıma gitme**|Tanıma Git komutu seçili düğüm üzerinde çalışır. Bu üye çağrısı için özgün tanımı veya değişken tanımını gider.<br /><br /> Tanıma Git komutu çalıştırmak için Seçili düğümün çift tıklatın veya seçili düğümde F12 tuşuna basın.|
|**Tüm başvuruları Bul**|Tüm başvuruları Bul komutu seçili düğüm üzerinde çalışır. Bu kod tüm satırları projenizde bu başvuru bir sınıf veya üye bulur.<br /><br /> SHIFT + F12, seçili düğümde tüm başvuruları Bul komutu çalıştırmak için de kullanabilirsiniz.|
|**Kopyala**|Seçili düğümün (ancak alt düğümlerini) içeriğini kopyalar.|
|**Yenileme**|Seçili düğümün daraltır. böylece yeniden genişletmeden geçerli bilgilerini görüntüler.|