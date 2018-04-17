---
title: XML belge doğrulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: abb353bd-6c4a-4978-b03b-a8c245bbfb55
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e226590b31a7b6b96755199bdb93cd95d438f08
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="xml-document-validation"></a>XML belge doğrulama
XML Düzenleyicisi'ni XML 1.0 sözdizimi denetler ve yazarken veri doğrulama da gerçekleştirir. Düzenleyici bir belge türü tanımı (DTD) ya da bir şema kullanarak doğrulayabilirsiniz. Kırmızı dalgalı alt çizgiler, doğru biçimlendirilmiş XML 1.0 hatalarını vurgulayın. Mavi dalgalı alt çizgiler DTD ya da şema doğrulamasını dayalı semantik hatalar gösterir. Her hata hata listesinde ilişkili bir giriş var. Dalgalı alt çizginin fare duraklatarak, hata iletisi de görüntüleyebilirsiniz.  
  
 Doğrulama kullanılan şemalar eşleştirerek bulunduğunda `targetNamespace` öğenin xmlns bildirimiyle derlenmiş şemanın. Derlenen şemalar, öncelik sırasına göre listelenen aşağıdaki konumlardan birini yüklenir:  
  
-   Belirtilen dosya adından **şemaları** belge penceresinin alan.  
  
-   Satır içi şema veya DTD.  
  
-   Bir dış DTD veya bir `xsd:schemaLocation` ve `xsd:noNamespaceSchemaLocation` özniteliği  
  
-   Bir "x-schema" XDR Şema ad alanı URI'si.  
  
Şema boş hedef ad alanı olduğunda şemaları ayrıca aşağıdaki ek konumlarda bulunabilir:  
  
-   Şema içeren başka bir düzenleyici penceresi.  
  
-   Geçerli çözümde şema.  
  
-   Şema önbellek dizini şemadan.  
  
## <a name="xslt-files"></a>XSLT dosyaları  
 XSLT dosyasının düzenlenmesi sırasında şema önbelleğinde bulunan xslt.xsd dosyasını doğrulama için kullanılır. Doğrulama hataları Mavi dalgalı alt çizgiler gösterilir. XSLT derleyici hatalarını kırmızı dalgalı alt çizgiler gösterilir.  
  
## <a name="xml-schema-xsd-files"></a>XML şema (XSD) dosyaları  
 Bir XML Şeması dosyasının düzenlenmesi sırasında şema önbelleğinde bulunan xsdschema.xsd dosyasını doğrulama için kullanılır. Doğrulama hataları Mavi dalgalı alt çizgiler gösterilir. Derleme hataları kırmızı dalgalı alt çizgi ile de gösterilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Düzenleyicisi](../xml-tools/xml-editor.md)