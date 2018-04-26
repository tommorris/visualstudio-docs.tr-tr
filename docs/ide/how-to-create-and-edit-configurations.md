---
title: 'Nasıl yapılır: oluşturma ve düzenleme yapılandırmaları'
ms.date: 06/21/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- solution build configurations, editing
- build configurations, creating
- solution build configurations, creating
- build configurations, editing
- builds [Visual Studio], setting up
- property pages
- Configuration Manager
- project build configurations, creating
- project build configurations, editing
ms.assetid: 19be121c-148e-4ece-bbfc-d20b08cfc3f7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3aa3aaa197f392d300e8787d582314846e789f47
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-and-edit-configurations"></a>Nasıl yapılır: oluşturma ve düzenleme yapılandırmaları

Bir çözüm için birkaç derleme yapılandırmaları oluşturabilirsiniz. Örneğin, sınayıcılar bulmak ve sorunları gidermek için kullanabileceğiniz bir hata ayıklama derlemesi yapılandırabilirsiniz ve farklı müşterilere dağıtabilirsiniz derlemeleri farklı türde yapılandırabilirsiniz.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="create-build-configurations"></a>Yapı yapılandırmaları oluşturma

Kullanabileceğiniz **Configuration Manager** iletişim kutusunu işaretleyin veya var olan yapı yapılandırmaları değiştirmek için ya da yeni bir tane oluşturmak için.

Açmak için **Configuration Manager** iletişim kutusunda **Çözüm Gezgini**, çözüm için kısayol menüsünü açın ve ardından **Configuration Manager**.

> [!NOTE]
> Varsa **Configuration Manager** komutu görünmüyor kısayol menüsünde arama altında **yapı** menü çubuğundaki menüsü. Menü çubuğunda, ya da seçin var. görünmüyorsa **Araçları** > **seçenekleri**ve ardından sol bölmesinde **seçenekleri** iletişim kutusunda, genişletin**Projeler ve çözümler** > **genel**, sağ bölmede seçip **Göster Gelişmiş derleme yapılandırmaları** onay kutusu.

İçinde **Configuration Manager** kullanabileceğiniz iletişim kutusu, **etkin çözüm yapılandırması** bir çözüm genelinde yapı yapılandırması seçin, mevcut bir değiştirin veya yeni bir oluşturmak için aşağı açılan liste yapılandırma. Kullanabileceğiniz **etkin çözüm platformu** yapılandırma hedefleri mevcut bir değiştirme veya yeni bir platformu ekleme platform seçmek için aşağı açılan liste. **Proje bağlamları** bölmesi, çözümdeki projelerin listeler. Her proje için bir proje özgü yapılandırması ve platformu seçin, var olanları değiştirin veya yeni bir yapılandırma oluşturabilir veya yeni bir platformu ekleyin. Derleme veya çözümü dağıtmak için çözüm genelinde yapılandırması kullandığınızda her proje dahil olup olmadığını gösteren onay kutularını öğesini de seçebilirsiniz.

 İstediğiniz yapılandırmaları ayarladıktan sonra bu yapılandırmalar için uygun olan proje özellikleri ayarlayabilirsiniz.

### <a name="to-set-properties-based-on-configurations"></a>Yapılandırmalarını temel alan özelliklerini ayarlamak için

-   İçinde **Çözüm Gezgini**, bir proje için kısayol menüsünü açın ve ardından **özellikleri**.

     **Özellik sayfaları** penceresi açılır.

     Yapılandırmalarınızı için özellikleri ayarlayabilirsiniz. Örneğin, bir yayın yapılandırma için kod çözüm yerleşik olarak bulunur ve bu belirttiğinizde bir hata ayıklama yapılandırması için optimize edilmiştir belirtebilirsiniz `DEBUG` koşullu derleme simge bulunur. Özellik sayfası ayarları hakkında daha fazla bilgi için bkz: [proje ve çözüm özelliklerini yönetme](../ide/managing-project-and-solution-properties.md).

## <a name="create-and-modify-project-configurations"></a>Oluşturma ve proje yapılandırmaları değiştirme

### <a name="to-create-a-project-configuration"></a>Bir proje yapılandırma oluşturmak için

1.  Açık **Configuration Manager** iletişim kutusu.

2.  Bir projedeki seçin **proje** sütun.

3.  İçinde **yapılandırma** açılan listesinden bu proje için seçme **yeni**.

     **Yeni proje yapılandırması** iletişim kutusu açılır.

4.  İçinde **adı** kutusuna, yeni yapılandırma için bir ad girin.

5.  Varolan bir proje yapılandırma özelliği ayarlarından kullanmak **ayarları kopyalamak** aşağı açılan listesinde, bir yapılandırma seçin.

6.  Aynı anda bir çözüm genelinde yapılandırması oluşturmak için seçin **oluştur yeni çözüm yapılandırması** onay kutusu.

### <a name="to-rename-a-project-configuration"></a>Bir proje yapılandırma yeniden adlandırmak için

1.  Açık **Configuration Manager** iletişim kutusu.

2.  İçinde **proje** sütunu yeniden adlandırmak istediğiniz proje yapılandırmasına sahip projesini seçin.

3.  İçinde **yapılandırma** açılan listesinden bu proje için seçme **Düzenle**.

     **Düzenle proje yapılandırmaları** iletişim kutusu açılır.

4.  Değiştirmek istediğiniz proje yapılandırma adı seçin.

5.  Seçin **yeniden adlandırma**ve ardından yeni bir ad girin.

## <a name="create-and-modify-solution-wide-build-configurations"></a>Oluşturma ve çözüm genelinde yapı yapılandırmalarını değiştirme

### <a name="to-create-a-solution-wide-build-configuration"></a>Bir çözüm genelinde yapı yapılandırması oluşturmak için

1.  Açık **Configuration Manager** iletişim kutusu.

2.  İçinde **etkin çözüm yapılandırması** aşağı açılan listesinde, seçin **yeni**.

     **Yeni çözüm yapılandırması** iletişim kutusu açılır.

3.  İçinde **adı** metin kutusuna, yeni yapılandırma için bir ad girin.

4.  Varolan bir çözüm yapılandırma ayarları kullanmak **ayarları kopyalamak** aşağı açılan listesinde, bir yapılandırma seçin.

5.  Proje yapılandırmaları aynı anda oluşturmak isteyip istemediğinizi seçin **yeni proje yapılandırmaları oluşturma** onay kutusu.

### <a name="to-rename-a-solution-wide-build-configuration"></a>Bir çözüm genelinde yapı yapılandırması yeniden adlandırmak için

1.  Açık **Configuration Manager** iletişim kutusu.

2.  İçinde **etkin çözüm yapılandırması** aşağı açılan listesinde, seçin **Düzenle**.

     **Düzenle çözüm yapılandırmaları** iletişim kutusu açılır.

3.  Değiştirmek istediğiniz çözüm yapılandırma adı seçin.

4.  Seçin **yeniden adlandırma**ve ardından yeni bir ad girin.

### <a name="to-modify-a-solution-wide-build-configuration"></a>Bir çözüm genelinde derleme yapılandırmasını değiştirmek için

1.  Açık **Configuration Manager** iletişim kutusu.

2.  İçinde **etkin çözüm yapılandırması** aşağı açılan listesinde, kullanmak istediğiniz yapılandırma seçin.

3.  İçinde **proje bağlamları** bölmesinde, select her proje için **yapılandırma** ve **Platform** ve seçin kullanılıp kullanılmayacağını **Yapı**onu görünüp görünmeyeceğini **dağıtma** onu.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)
- [Derleme ve projeler ve çözümler Visual Studio'da Temizle](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Proje ve çözüm özelliklerini yönetme](managing-project-and-solution-properties.md)