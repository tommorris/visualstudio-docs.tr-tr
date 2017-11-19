---
title: "Nasıl yapılır: kullanılacak XML şemaları seçin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 50077e430d6d9f273dd4cd3e247de3df043804c4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>Nasıl yapılır: kullanılacak XML şemaları seçin
XML Düzenleyicisi'ni %InstallDir%\Xml\Schemas dizininde yer alan bir şema önbelleği sağlar. Şema önbelleğinin IntelliSense ve XML belge doğrulama için kullanılan iyi bilinen XML şemaları içerir.  
  
 **Şemaları** belge özelliği kullanmak için bir veya daha fazla XML Şeması Tanım Dili (XSD) şeması/şemaları seçmek için kullanılır. Şemalar şema önbelleğinde seçin ya da önbellekte bulunmayan bir şema belirtmek için sağlar.  
  
 Belirttiğiniz şemaları diğer yanı sıra tüm XML belge özellikleri gizli bir çözüm kullanıcı seçenekleri dosyasında (.suo) kaydedilir. Sonuç olarak, bu değerleri çözüm bir sonraki açışınızda yeniden girmeniz gerekmez.  
  
> [!NOTE]
>  Düzenleyici bir satır içi şema veya başvurduğu bir şema kullanarak doğrulayabilirsiniz `xsd:schemaLocation` özniteliği. Daha fazla bilgi için bkz: [XML belge doğrulama](../xml-tools/xml-document-validation.md).  
  
### <a name="to-select-an-xml-schema-from-the-schema-cache"></a>Bir XML Şeması şema önbelleğinde seçmek için  
  
1.  Bir dosyasını XML düzenleyicisinde açın.  
  
2.  Belge Özellikleri penceresinde üzerinde düğmesini **şemaları** alan.  
  
     **XML şemaları** iletişim kutusu görüntülenir. İletişim kutusu (catalog.xml dosyasında başvurulan şemaları dahil) şema önbelleğinde .xsd uzantısına sahip tüm şemaları listeler ve geçerli çözümde olduğu herhangi bir şema açmak için ayrıca başvurulan Visual Studio bir `xsd:schemaLocation` özniteliği ya da başvuru **şemaları** özelliği.  
  
3.  Aşağıdakilerden birini yaparak doğrulama için kullanılacak şemaları seçin:  
  
    -   Listelenen bir şema seçin **XML şemaları** iletişim kutusunda, tıklatın **kullanım** sütun ve ardından **Bu şemayı kullanan**.  
  
     veya  
  
    -   Listede birden çok şema seçin **XML şemaları** iletişim kutusu, sağ tıklatın ve seçin **Bu şemayı kullanan**.  
  
4.  **Tamam**'ı tıklatın.  
  
     Seçili şemaları listesi geri kopyalanır **şemaları** belge özelliği.  
  
### <a name="to-add-an-xml-schema-to-the-schema-cache"></a>Bir XML Şeması şema önbelleğine eklemek için  
  
1.  Belge Özellikleri penceresinde üzerinde düğmesini **şemaları** alan.  
  
2.  **Ekle**'yi tıklatın.  
  
     Bu açılır **açık XSD şema** iletişim.  
  
3.  Gözat ve şema önbelleğine eklemek için şeması/şemaları seçin.  
  
4.  Tıklatın **açık**.  
  
     Şemaya eklenen şeması/şemaları önbelleğe ve ise **kullanım** sütun değeri ayarlanmış **Bu şemayı kullanan**.  
  
### <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>Bir XML Şeması şema önbelleğinde silmek için  
  
1.  Belge Özellikleri penceresinde üzerinde düğmesini **şemaları** alan.  
  
2.  Şemayı kaldırın ve ardından seçin **kaldırmak**.  
  
     Şema bellek içi şema önbellekten kaldırıldı, ancak dosya sisteminden kaldırılmaz.  
  
    > [!NOTE]
    >  Hala şema başvurusu varsa bir `schemaLocation` özniteliği veya eşleşen bir `targetNamespace` sonra **kaldırmak** otomatik ilişki nedeniyle bu durumda çalışmaz. Bu durumda şeması olarak işaretlemek önerilir **seçili şemaları kullanmayın** içinde **kullanmak** sütun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şema önbelleği](../xml-tools/schema-cache.md)   
 [XML şemaları iletişim kutusu](../xml-tools/xml-schemas-dialog-box.md)   
 [XML Düzenleyicisi](../xml-tools/xml-editor.md)