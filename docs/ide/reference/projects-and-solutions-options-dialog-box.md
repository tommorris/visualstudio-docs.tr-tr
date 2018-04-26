---
title: Projeler ve Çözümler, Seçenekler İletişim Kutusu
ms.date: 07/14/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Projects.General
- VS.ToolsOptionsPages.Projects.Locations
helpviewer_keywords:
- Projects and Solutions Options dialog box
- Options dialog box, Projects and Solutions
ms.assetid: 2801f24e-a138-488a-ae3c-e1f99a678ac0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 606af4d08ffaec87c46c394f55ffe4e37b2a940d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="projects-and-solutions-options-dialog-box"></a>Projeler ve Çözümler, Seçenekler İletişim Kutusu
Ayarlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] davranışı ilgili projeler ve çözümler. Bu seçenekler erişmek için seçin **Araçlar > Seçenekler** genişletin **projeler ve çözümler**, tıklatıp **genel**.

Proje ve şablon klasörleri için varsayılan yollar aracılığıyla ayarlanabilir **konumları** aynı iletişim kutusundaki sekmesi.

> [!NOTE]
> İletişim kutuları, adları ve menü komutlarını, gördüğünüz konumlarını Seçenekleri Yardımı'nda etkin ayarlarınıza veya sürümünüze bağlı olarak açıklanan nedir alanından farklı olabilir. Bu Yardım sayfası ile yazıldı **genel geliştirme ayarlarını** unutmayın. Ayarlarını görüntülemek veya değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).


## <a name="general-tab-options"></a>Genel sekmesi seçenekleri

**Hata listesi yapı hataları ile biter varsa her zaman göster**

Açılır **hata listesi** yapı tamamlandığında, yalnızca bir proje oluşturmak başarısızsa penceresi. Derleme işlemi sırasında oluşan hatalar görüntülenir. Bu seçenek temizlendiğinde hataları oluşmaya ancak yapı tamamlandığında penceresi açılmaz. Bu seçenek varsayılan olarak etkindir.

**Çözüm Gezgini'nde etkin öğesi izleme**

Seçili olduğunda, **Çözüm Gezgini** otomatik olarak açar ve etkin öğeyi seçilidir. Seçili öğeyi değişir proje ya da çözüm farklı dosya ya da farklı bir tasarımcı bileşenlerinde çalışırlar. Ne zaman bu seçeneği işaretli değilse, seçim **Çözüm Gezgini** otomatik olarak değişmez. Bu seçenek varsayılan olarak etkindir.

**Gelişmiş derleme yapılandırmaları Göster**

Seçili olduğunda, derleme yapılandırma seçenekleri görünür **proje özellik sayfalarını** iletişim kutusu ve **çözüm özellik sayfaları** iletişim kutusu. Yapı yapılandırma seçenekleri üzerinde görünmeyen kaldırıldığında, **proje özellik sayfalarını** iletişim kutusu ve **çözüm özellik sayfaları** iletişim kutusu için [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] ve [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] projeleri bir yapılandırma veya iki yapılandırması hata ayıklama ve yayın içeren. Bir proje kullanıcı tanımlı bir yapılandırmayı varsa, yapı yapılandırma seçenekleri gösterilmektedir.

Seçili üzerinde olmadığında komutları **yapı** menüsünde gibi **yapı çözümü**, **çözümü yeniden derle**, ve **temiz çözüm**, olan Yayın yapılandırma ve komutları üzerinde gerçekleştirilen **hata ayıklama** menüsünde gibi **hata ayıklamayı Başlat** ve **hata ayıklama olmadan Başlat**, üzerinde gerçekleştirilen hata ayıklama yapılandırması.

**Çözüm her zaman göster**

Seçili olduğunda, çözüm ve çözümlerini hareket tüm komutları her zaman IDE içinde gösterilir. Kaldırıldığında, tüm projeleri tek başına projeler olarak oluşturulur ve çözüm yalnızca bir proje içeriyorsa, Çözüm Gezgini'nde ya da hareket komutları çözüm çözümleri IDE üzerinde görmezsiniz.

**Oluştururken yeni projeler Kaydet**

Seçili olduğunda, projeniz için bir konum belirtebilirsiniz **yeni proje** iletişim kutusu. Kaldırıldığında, tüm yeni projeler geçici projeler olarak oluşturulur. Geçici projeler ile çalışırken, oluşturabilir ve bir disk konumu belirtmek zorunda kalmadan bir proje ile deneyin.

**Proje konumu güvenilir değilse, kullanıcıyı uyarır.**

Yeni bir proje oluşturun veya varolan projeyi tam olarak (örneğin, bir UNC yolu veya HTTP yolu) güvenilir bir konumda açın çalışırsanız, bir ileti görüntülenir. İleti projesi oluşturma veya bir tam olarak güvenilmeyen bir konumda açma girişiminde her zaman görüntülenip görüntülenmeyeceğini belirtmek için bu seçeneği kullanın.

**Yapı başladığında çıktı penceresini göster**

Otomatik olarak çözüm outset IDE çıktı penceresinde görüntüler oluşturur. Daha fazla bilgi için bkz: [nasıl yapılır: Çıktı penceresi denetim](http://msdn.microsoft.com/Library/91aebd15-8854-4a7a-9f7d-57376fb4e858).

**Simgesel dosyaları yeniden adlandırırken yeniden adlandırmak için sor**

Seçili olduğunda, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , ayrıca projedeki tüm başvuruları kod öğesini yeniden adlandırmanız gerekir olup olmadığını soran bir ileti kutusu görüntüler.

**Yeni bir konuma dosyaları taşınmadan önce sor**

Seçili olduğunda, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Çözüm Gezgini'nde eylemler tarafından dosya konumlarının değişmesi önce bir onaylama ileti kutusu görüntüler.

## <a name="locations-tab-options"></a>Konumları sekmesi seçenekleri

**Projeleri konumu**

Varsayılan konumu belirtir nerede [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yeni proje ve çözüm klasörleri oluşturur. Birkaç iletişim kutusu ayrıca başlangıç noktaları klasörü için bu seçeneği kümesindeki konum kullanın. Örneğin, Proje Aç iletişim kutusu bu konum için My projeleri kısayol kullanır.

**Kullanıcı proje şablonları**

Varsayılan konumu belirtir, **yeni proje** listesini oluşturmak için iletişim kutusu kullanır **My şablonları**. Daha fazla bilgi için bkz: [nasıl yapılır: bulun ve düzenleme şablonlarını](../../ide/how-to-locate-and-organize-project-and-item-templates.md).

**Kullanıcı öğesi şablonları**

Varsayılan konumu belirtir, **Yeni Öğe Ekle** listesini oluşturmak için iletişim kutusu kullanır **My şablonları**. Daha fazla bilgi için bkz: [nasıl yapılır: bulun ve düzenleme şablonlarını](../../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="see-also"></a>Ayrıca Bkz.

- [Seçenekler iletişim kutusu, projeler ve çözümler, derleme ve çalıştırma](../../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md)
- [Seçenekler iletişim kutusu, projeler ve çözümler, Web projeleri](../../ide/reference/options-dialog-box-projects-and-solutions-web-projects.md)