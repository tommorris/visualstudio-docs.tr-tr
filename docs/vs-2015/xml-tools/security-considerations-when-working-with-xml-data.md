---
title: XML verileriyle çalışırken güvenlik konuları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce2b708-1aef-454f-be59-52b76f359351
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9acd701c4e279d02cae874768b18a3d89b58203d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692074"
---
# <a name="security-considerations-when-working-with-xml-data"></a>XML Verileriyle Çalışırken Dikkat Edilecek Güvenlik Konuları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [güvenlik XML verileriyle çalışırken dikkat edilmesi gerekenler](https://docs.microsoft.com/visualstudio/xml-tools/security-considerations-when-working-with-xml-data).  
  
  
Bu konuda hakkında XML Düzenleyicisi'ni veya XSLT hata ayıklayıcısı ile çalışırken bilmeniz gereken güvenlik konuları açıklanmaktadır.  
  
## <a name="xml-editor"></a>XML Düzenleyicisi  
 XML Düzenleyicisi Visual Studio Metin Düzenleyicisi üzerinde temel alır. Kullanır <xref:System.Xml> ve <xref:System.Xml.Xsl> XML işlemlerin çoğunu işlemek için sınıflar.  
  
-   XSLT dönüşümleri, yeni bir uygulama etki alanında yürütülür. XSLT dönüşümleri olan *korumalı*; diğer bir deyişle, kod erişimi güvenlik ilkesi bilgisayarınızın XSLT stil sayfası bulunduğu yeri üzerinde temel kısıtlı izinleri belirlemek için kullanılır. Örneğin, stil sayfaları tam güven ile çalışacak sabit diske kopyalanır, ancak bir Internet konumundan stil sayfaları en kısıtlı izinlere sahip.  
  
-   <xref:System.Xml.Xsl.XslCompiledTransform> Sınıfı XSLT Microsoft Ara dili yürütme sırasında daha hızlı performans için derlemek için kullanılır.  
  
-   XML Düzenleyicisi'ni ilk yüklendiğinde dış bir katalog dosyası konumuna işaret eden şemaları otomatik olarak yüklenir. <xref:System.Xml.Schema.XmlSchemaSet> Sınıfı şemaları derlemek için kullanılır. XML Düzenleyicisi ile birlikte gelen katalog dosyası bağlantılarını herhangi bir Dış şemalara sahip değil. Kullanıcının XML Düzenleyicisi şema dosyası indirir önce dış şema başvuru açıkça eklemeniz gerekir. HTTP indirmeyi devre dışı bırakılabilir aracılığıyla **çeşitli Araçlar Seçenekler** sayfası XML Düzenleyicisi için.  
  
-   XML Düzenleyicisi kullanan <xref:System.Net> şemaları indirmek için sınıflar  
  
## <a name="xslt-debugger"></a>XSLT hata ayıklayıcısı  
 XSLT hata ayıklayıcı, Visual Studio yönetilen hata ayıklama motorunu kullanır ve gelen sınıflar <xref:System.Xml> ve <xref:System.Xml.Xsl> ad alanı.  
  
-   XSLT hata ayıklayıcısı, koruma alanlı uygulama etki alanında her XSLT dönüşümü çalıştırır. Kod erişimi güvenlik ilkesi bilgisayarınızın XSLT stil sayfası bulunduğu yeri üzerinde temel kısıtlı izinleri belirlemek için kullanılır. Örneğin, stil sayfaları tam güven ile çalışacak sabit diske kopyalanır, ancak bir Internet konumundan stil sayfaları en kısıtlı izinlere sahip.  
  
-   XSLT stil sayfası kullanılarak derlenmiş <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı.  
  
-   XSLT ifade değerlendiricisi yönetilen hata ayıklama altyapısı tarafından yüklenir. Yönetilen hata ayıklama altyapısı, tüm kod kullanıcının yerel bilgisayarınızdan çalıştırıldığını varsayar. Buna <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı kullanıcının yerel bilgisayarına XSLT dosyasını indirir. Sınırlı izinler ile yeni bir uygulama etki alanındaki tüm XSLT dönüşümleri yürüterek, yürütme ayrıcalık yükselmesi oluşabilir olasılığı azaltılabilir  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama Etki Alanları](http://msdn.microsoft.com/en-us/39e57d07-a740-4cd4-ae82-e119ea3856c1)



