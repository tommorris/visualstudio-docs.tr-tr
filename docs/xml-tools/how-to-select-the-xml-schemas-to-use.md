---
title: 'Nasıl yapılır: kullanılacak XML şemaları seçin'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d835a8592108b549a109f7bb7e128a8ae5b01611
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>Nasıl yapılır: kullanılacak XML şemaları seçin

Bulunan bir şema önbelleği XML Düzenleyicisi sağlar *%InstallDir%\Xml\Schemas* dizini. Şema önbelleğinin IntelliSense ve XML belge doğrulama için kullanılan iyi bilinen XML şemaları içerir.

**Şemaları** belge özelliği kullanmak için bir veya daha fazla XML Şeması Tanım Dili (XSD) şeması/şemaları seçmek için kullanılır. Şemalar şema önbelleğinde seçin ya da önbellekte bulunmayan bir şema belirtmek için sağlar.

Belirttiğiniz şemaları gizli çözüm kullanıcı seçenekleri dosyasında kaydedilir (. *suo*), yanı sıra diğer tüm XML belge özellikleri. Sonuç olarak, bu değerleri çözüm bir sonraki açışınızda yeniden girmeniz gerekmez.

> [!NOTE]
> Düzenleyici bir satır içi şema veya başvurduğu bir şema kullanarak doğrulayabilirsiniz `xsd:schemaLocation` özniteliği. Daha fazla bilgi için bkz: [XML belge doğrulama](../xml-tools/xml-document-validation.md).

## <a name="to-select-an-xml-schema-from-the-schema-cache"></a>Bir XML Şeması şema önbelleğinde seçmek için

1.  Bir dosyasını XML düzenleyicisinde açın.

2.  Belge Özellikleri penceresinde üzerinde düğmesini **şemaları** alan.

     **XML şemaları** iletişim kutusu görüntülenir. İletişim kutusu tüm şemalarda listeler bir. *xsd* uzantı şema önbelleğinde (başvurulan şemaları dahil olmak üzere *catalog.xml* dosyası) ve ayrıca Visual Studio'da Aç Geçerli çözümde başvuru hiçbir şema bir `xsd:schemaLocation` öznitelik veya başvurulan **şemaları** özelliği.

3.  Aşağıdakilerden birini yaparak doğrulama için kullanılacak şemaları seçin:

    -   Listelenen bir şema seçin **XML şemaları** iletişim kutusunda, tıklatın **kullanım** sütun ve ardından **Bu şemayı kullanan**.

     -veya-

    -   Listede birden çok şema seçin **XML şemaları** iletişim kutusu, sağ tıklatın ve seçin **Bu şemayı kullanan**.

4.  **Tamam**'ı tıklatın.

     Seçili şemaları listesi geri kopyalanır **şemaları** belge özelliği.

## <a name="to-add-an-xml-schema-to-the-schema-cache"></a>Bir XML Şeması şema önbelleğine eklemek için

1.  Belge Özellikleri penceresinde üzerinde düğmesini **şemaları** alan.

2.  **Ekle**'yi tıklatın.

     Bu açılır **açık XSD şema** iletişim.

3.  Gözat ve şema önbelleğine eklemek için şeması/şemaları seçin.

4.  Tıklatın **açık**.

     Şemaya eklenen şeması/şemaları önbelleğe ve ise **kullanım** sütun değeri ayarlanmış **Bu şemayı kullanan**.

## <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>Bir XML Şeması şema önbelleğinde silmek için

1.  Belge Özellikleri penceresinde üzerinde düğmesini **şemaları** alan.

2.  Şemayı kaldırın ve ardından seçin **kaldırmak**.

     Şema bellek içi şema önbellekten kaldırıldı, ancak dosya sisteminden kaldırılmaz.

    > [!NOTE]
    > Hala şema başvurusu varsa bir `schemaLocation` özniteliği veya eşleşen bir `targetNamespace` sonra **kaldırmak** otomatik ilişki nedeniyle bu durumda çalışmaz. Bu durumda şeması olarak işaretlemek önerilir **seçili şemaları kullanmayın** içinde **kullanmak** sütun.

## <a name="see-also"></a>Ayrıca bkz.

- [Şema önbelleği](../xml-tools/schema-cache.md)
- [XML şemaları iletişim kutusu](../xml-tools/xml-schemas-dialog-box.md)
- [XML Düzenleyicisi](../xml-tools/xml-editor.md)