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
ms.openlocfilehash: dbd3fe20377cd2aa4954e904fec50702cc9b7120
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34843997"
---
# <a name="projects-and-solutions-page-options-dialog-box"></a>Projeler ve çözümler sayfasında, Seçenekler iletişim kutusu

Visual Studio davranışı projeler ve çözümler için ilgili ayarlar. Bu seçenekler erişmek için seçin **Araçları** > **seçenekleri**, genişletin **projeler ve çözümler**ve ardından **genel** .

Proje ve şablon klasörleri için varsayılan yollar aracılığıyla ayarlanabilir **konumları** aynı iletişim kutusundaki sekmesi.

> [!NOTE]
> Kullanıcı Arabiriminde kullanılabilir seçenekler ne Burada, etkin ayarlarınıza veya sürümünüze bağlı olarak açıklanan alanından farklı olabilir. Bu makale ile yazılmıştır **genel geliştirme ayarlarını** unutmayın. Ayarlarını görüntülemek veya değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="general-page"></a>Genel sayfası

Aşağıdaki seçenekler mevcuttur **genel** sayfası.

### <a name="always-show-error-list-if-build-finishes-with-errors"></a>Hata listesi yapı hataları ile biter varsa her zaman göster

Açılır **hata listesi** yapı tamamlandığında, yalnızca bir proje oluşturmak başarısızsa penceresi. Derleme işlemi sırasında oluşan hatalar görüntülenir. Bu seçenek temizlendiğinde hataları oluşmaya ancak yapı tamamlandığında penceresi açılmaz. Bu seçenek varsayılan olarak etkindir.

### <a name="track-active-item-in-solution-explorer"></a>Çözüm Gezgini'nde etkin öğesi izleme

Seçili olduğunda, **Çözüm Gezgini** otomatik olarak açar ve etkin öğeyi seçilidir. Seçili öğeyi değişir proje ya da çözüm farklı dosya ya da farklı bir tasarımcı bileşenlerinde çalışırlar. Ne zaman bu seçeneği işaretli değilse, seçim **Çözüm Gezgini** otomatik olarak değişmez. Bu seçenek varsayılan olarak etkindir.

### <a name="show-advanced-build-configurations"></a>Gelişmiş derleme yapılandırmaları Göster

Seçili olduğunda, derleme yapılandırma seçenekleri görünür **proje özellik sayfalarını** iletişim kutusu ve **çözüm özellik sayfaları** iletişim kutusu. Yapı yapılandırma seçenekleri üzerinde görünmeyen kaldırıldığında, **proje özellik sayfalarını** iletişim kutusu ve **çözüm özellik sayfaları** bir içermelidir Visual Basic ve C# projeleri için iletişim kutusu yapılandırma veya iki yapılandırması hata ayıklama ve yayın. Bir proje kullanıcı tanımlı bir yapılandırmayı varsa, yapı yapılandırma seçenekleri gösterilmektedir.

Seçili üzerinde olmadığında komutları **yapı** menüsünde gibi **yapı çözümü**, **çözümü yeniden derle**, ve **temiz çözüm**, olan Yayın yapılandırma ve komutları üzerinde gerçekleştirilen **hata ayıklama** menüsünde gibi **hata ayıklamayı Başlat** ve **hata ayıklama olmadan Başlat**, üzerinde gerçekleştirilen hata ayıklama yapılandırması.

### <a name="always-show-solution"></a>Çözüm her zaman göster

Seçili olduğunda, çözüm ve çözümlerini hareket tüm komutları her zaman IDE içinde gösterilir. Kaldırıldığında, tüm projeleri tek başına projeler olarak oluşturulur ve çözüm yalnızca bir proje içeriyorsa, Çözüm Gezgini'nde ya da hareket komutları çözüm çözümleri IDE üzerinde görmezsiniz.

### <a name="save-new-projects-when-created"></a>Oluştururken yeni projeler Kaydet

Seçili olduğunda, projeniz için bir konum belirtebilirsiniz **yeni proje** iletişim kutusu. Kaldırıldığında, tüm yeni projeler geçici projeler olarak oluşturulur. Geçici projeler ile çalışırken, oluşturabilir ve bir disk konumu belirtmek zorunda kalmadan bir proje ile deneyin.

### <a name="warn-user-when-the-project-location-is-not-trusted"></a>Proje konumu güvenilir değilse, kullanıcıyı uyarır.

Yeni bir proje oluşturun veya varolan projeyi tam olarak (örneğin, bir UNC yolu veya HTTP yolu) güvenilir bir konumda açın çalışırsanız, bir ileti görüntülenir. İleti projesi oluşturma veya bir tam olarak güvenilmeyen bir konumda açma girişiminde her zaman görüntülenip görüntülenmeyeceğini belirtmek için bu seçeneği kullanın.

### <a name="show-output-window-when-build-starts"></a>Yapı başladığında çıktı penceresini göster

Otomatik olarak görüntüler [çıktı penceresi](../../ide/reference/output-window.md) çözümün outset IDE içinde oluşturur.

### <a name="prompt-for-symbolic-renaming-when-renaming-files"></a>Simgesel dosyaları yeniden adlandırırken yeniden adlandırmak için sor

Seçili olduğunda, Visual Studio, ayrıca projedeki tüm başvurularını kod öğesine yeniden adlandırmanız gerekir olup olmadığını soran bir ileti kutusu görüntüler.

### <a name="prompt-before-moving-files-to-a-new-location"></a>Yeni bir konuma dosyaları taşınmadan önce sor

Eylemler tarafından dosya konumlarının değişmesi önce seçili olduğunda, Visual Studio onaylama ileti kutusu görüntüler **Çözüm Gezgini**.

### <a name="reopen-documents-on-solution-load"></a>Çözüm yük belgelerde yeniden açın

**Visual Studio 2017 sürüm 15,8 önizleme 2 ve daha yeni**

Çözüm açıldığında seçili olduğunda, önceki zaman çözüm kapalı açık bırakılmış belgeleri otomatik olarak açılır.

Belirli türde bir dosya ya da tasarımcıları açmayı çözüm yük gecikmeye yol açabilir. Bu seçeneğin işaretini kaldırmanız [çözüm yük performansı](../../ide/visual-studio-performance-tips-and-tricks.md#disable-automatic-file-restore) çözümün önceki bağlamı geri yüklemek istemiyorsanız.

## <a name="locations-page"></a>Konumları sayfası

Aşağıdaki seçenekler mevcuttur **konumları** sayfası.

### <a name="projects-location"></a>Projeleri konumu

Visual Studio yeni proje ve çözüm klasörleri oluşturur varsayılan konumu belirtir. Birkaç iletişim kutusu ayrıca başlangıç noktaları klasörü için bu seçeneği kümesindeki konum kullanın. Örneğin, **Proje Aç** iletişim kutusu, bu konum için kullanır **My projeleri** kısayol.

### <a name="user-project-templates-location"></a>Kullanıcı proje şablonları

Varsayılan konumu belirtir, **yeni proje** listesini oluşturmak için iletişim kutusu kullanır **My şablonları**. Daha fazla bilgi için bkz: [nasıl yapılır: bulun ve düzenleme şablonlarını](../../ide/how-to-locate-and-organize-project-and-item-templates.md).

### <a name="user-item-templates-location"></a>Kullanıcı öğesi şablonları

Varsayılan konumu belirtir, **Yeni Öğe Ekle** listesini oluşturmak için iletişim kutusu kullanır **My şablonları**. Daha fazla bilgi için bkz: [nasıl yapılır: bulun ve düzenleme şablonlarını](../../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Seçenekler iletişim kutusu, projeler ve çözümler, derleme ve çalıştırma](../../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md)
- [Seçenekler iletişim kutusu, projeler ve çözümler, Web projeleri](../../ide/reference/options-dialog-box-projects-and-solutions-web-projects.md)
