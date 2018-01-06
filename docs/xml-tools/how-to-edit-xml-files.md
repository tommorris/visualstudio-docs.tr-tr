---
title: "Nasıl yapılır: XML dosyalarını düzenleyebilirsiniz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07fa3ecf-6345-4d30-9d85-d5ef5b083319
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8720fe94797e212cb332368572b291ce7fb40a26
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-edit-xml-files"></a>Nasıl yapılır: XML dosyalarını düzenleme
XML Düzenleyicisi'ni XML dosyaları için yeni düzenleyicisidir. Visual Studio Proje ile ilişkili bir dosya veya tek başına bir XML dosyası üzerinde kullanılabilir. XML Düzenleyicisi'ni aşağıdaki dosya uzantıları ile ilişkilidir: .config, .dtd, .xml, .xsd, .xdr, .xsl, .xslt ve .vssettings. XML Düzenleyicisi'ni, belirli bir düzenleyici kayıtlı olan ve XML veya DTD içeriği içeren başka bir dosya türü ile de ilişkilidir.  
  
> [!NOTE]
>  XHTML belgeleri, HTML düzenleyicisi tarafından işlenir.  
  
### <a name="to-edit-an-xml-file"></a>Bir XML dosyası düzenlemek için  
  
1.  Düzenlemek istediğiniz dosyayı çift tıklatın.  
  
### <a name="to-add-a-new-xml-file-to-a-project"></a>Yeni bir XML dosyası için bir proje eklemek için  
  
1.  Gelen **proje** menüsünde, select **Yeni Öğe Ekle**.  
  
2.  Seçin **XML dosyası** gelen **şablonları** bölmesi.  
  
3.  Dosya adını girin **adı** alan ve tuşuna **Ekle**.  
  
     XML dosyası projeye eklenir ve XML Düzenleyicisi'nde açılır. Varsayılan XML bildirimi dosyayı içeren `<?xml version="1.0" encoding="utf-8" ?>`.  
  
### <a name="to-add-an-existing-xml-file-to-a-project"></a>Varolan bir XML dosyasını bir projeye eklemek için  
  
1.  Gelen **proje** menüsünde, select **varolan öğeyi Ekle**.  
  
     **Varolan öğeyi Ekle** iletişim kutusu görüntülenir.  
  
2.  Bir XML dosyasını seçip tuşuna **Ekle**.  
  
### <a name="to-create-a-new-xml-or-xslt-file"></a>Yeni bir XML veya XSLT dosyası oluşturmak için  
  
1.  Gelen **dosya** menüsünde, select **yeni**.  
  
     **Yeni dosya** iletişim kutusu görüntülenir.  
  
2.  Seçin **XML dosyası** yeni bir XML dosyası; oluşturmak veya seçmek için **XSLT dosyası** yeni bir XSLT stil sayfası oluşturmak için.  
  
3.  Tıklatın **açık**.  
  
### <a name="to-create-a-project-for-xml-files"></a>XML dosyaları için bir proje oluşturmak için  
  
1.  Gelen **dosya** menüsünde, select **yeni**ve ardından **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  Kod dili, select seçin **boş proje**, tıklatıp **Tamam**.  
  
3.  XML dosyaları projeye ekleyin.  
  
     XML Düzenleyicisi'ni bu projeye eklemek şemaları bulur ve bunları doğrulama ve IntelliSense herhangi bir XML, şema veya bu proje açıkken düzenlediğiniz XSLT dosyaları için kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Düzenleyicisi](../xml-tools/xml-editor.md)   
 [XML belge özellikleri, özellik penceresi](../xml-tools/xml-document-properties-properties-window.md)   
 [Nasıl Yapılır: XML Belgesinden XML Şeması Oluşturma](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)