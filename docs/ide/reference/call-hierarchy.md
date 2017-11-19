---
title: "Çağrı hiyerarşisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.CallHierarchy
helpviewer_keywords: Call Hierarchy
ms.assetid: c55bda01-d7de-4823-8f9a-1bcc37dbb74a
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 065806ec223273bbacba6da7702f21bc25510983
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="call-hierarchy"></a>Çağrı Hiyerarşisi
Çağrı hiyerarşisi seçili yöntemi, özelliği veya oluşturucusu gelen ve giden tüm çağrıları görüntüleyerek kodunuz gezinmenizi sağlar. Bu, kodu nasıl akacağını daha iyi anlamak ve koduna değişiklikler etkilerini değerlendirmek için sağlar. Yöntem çağrıları ve tüm olası yürütme yollarını keşfetmek sağlar koduna ek giriş noktaları karmaşık zincirleri görüntülemek üzere kod birkaç düzeyini inceleyebilirsiniz.  
  
 Çağrı hiyerarşisi, hata ayıklayıcı tarafından görüntülenen çağrı yığını farklı tasarım zamanında kullanılabilir.  
  
## <a name="using-call-hierarchy"></a>Çağrı hiyerarşisi kullanma  
 Görüntülenecek **çağrı hiyerarşisi** penceresinde bir yöntemi, özelliği veya oluşturucu çağrısı adına sağ tıklayın ve ardından **görünüm çağrı hiyerarşisi**.  
  
 Üye adı bir ağaç görünümü bölmesinde görünür **çağrı hiyerarşisi** penceresi. Üye düğümünü genişletin, **çağrıları için***üye adı* ve **çağrıları gelen***üye adı* düğümlerinde görünür. Bu düğümler aşağıda gösterilmiştir **çağrı hiyerarşisi** penceresi.  
  
 ![Çağrı hiyerarşisi tek bir düğüm açık](../../ide/reference/media/onenode.png "OneNode")  
Çağrı hiyerarşisi penceresi  
  
-   Genişletirseniz **çağrıları için** düğümü, tüm üyeleri çağrısı seçilen üye görüntülenir.  
  
-   Genişletirseniz **çağrıları gelen** düğümü, seçili üyesi tarafından çağrılan tüm üyeleri görüntülenir.  
  
Bu alt düğüm üyelerinin her biri daha sonra genişletebilirsiniz **çağrıları için** ve **çağrıları gelen** düğümleri. Bu, arayanlar, yığına gitmek aşağıdaki çizimde gösterildiği gibi sağlar.  
  
![Çağrı hiyerarşisi birden çok düğümü açık](../../ide/media/multiplenodes.png "MultipleNodes")  
Çağrı hiyerarşisi penceresi  
  
Sanal ya da soyut olarak tanımlanmış bir üye için bir **geçersiz kılmaları yöntem adı** düğümü görüntülenir. Arabirim üyeleri için bir **uygulayan yöntem adı** düğümü görüntülenir. Bu Genişletilebilir düğümler aynı düzeyde görünür **çağrıları için** ve **çağrıları gelen** düğümleri.  
  
**Arama kapsamı** araç kutusu içeren seçenekleri için **My çözüm**, **geçerli projenin**, ve **geçerli belge**.  
  
Bir alt üye seçtiğinizde **çağrı hiyerarşisi** ağaç görünümü bölmesinde:  
  
-   **Çağrı hiyerarşisi** Ayrıntılar bölmesinde o alt üyenin üst üyeden çağrıldığı kod tüm satırları görüntüler.  
  
-   **Kod tanımı penceresi**, açık değilse, seçilen üye için kod görüntüler. Bu pencere, C# ve C++ içinde kullanılabilir. Bu pencere hakkında daha fazla bilgi için bkz: [kodunu yapısı görüntüleme](../../ide/viewing-the-structure-of-code.md).  
  
> [!NOTE]
>  Çağrı hiyerarşisi grup başvuruları, burada bir yöntem olay işleyici eklenir veya bir temsilciye atanmış yerler içeren yöntemi bulmaz. Bir yöntem yapılan tüm başvuruları Bul için kullanabileceğiniz **tüm başvuruları Bul** komutu.  
  
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