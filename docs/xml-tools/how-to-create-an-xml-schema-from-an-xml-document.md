---
title: "Nasıl yapılır: bir XML belgesinden bir XML Şeması oluşturun | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0541e89e72670905172129ffbb141ae8ae9e727f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>Nasıl yapılır: bir XML belgesinden bir XML Şeması oluşturun
XML düzenleyicisini, bir XML belgesinden bir XML Şeması Tanım Dili (XSD) şeması oluşturmanıza olanak sağlar. XML örneği Belge Şeması aşağıdaki şekilde nasıl oluşturulacağını belirler:  
  
-   XML belge şeması yok veya belge türü tanımı (DTD) ilişkili varsa XML belgedeki verileri yeni bir XML Şeması anlamak için kullanılır.  
  
-   XML belge ilişkili DTD içeriyorsa, dış DTD ve iç alt karşılık gelen bir XML Şeması dönüştürülür.  
  
-   XML belge bir satır içi XML verileri azaltılmış (XDR) şema içeriyorsa, XDR şema karşılık gelen bir XML Şeması dönüştürülür.  
  
Oluşturulan şemaları, daha sonra XML belgesi için IntelliSense sağlamak için kullanılır.  
  
Şema çıkarımı altyapısının hakkında daha fazla bilgi için bkz: [bir XML Şeması çıkarımını yapma](/dotnet/standard/data/xml/inferring-an-xml-schema).  
  
### <a name="to-create-an-xml-schema"></a>Bir XML şeması oluşturmak için  
  
1.  Bir XML örneği belgesi içine XML Düzenleyicisi'ni yükleyin.  
  
2.  Tıklatın **Create Schema** gelen düğmesini **araç**.  
  
     Bir XML Şeması belgesi oluşturulur ve XML örneği belgesinde bulunan her ad alanı için açıldı. Her şema geçici çeşitli dosya olarak açılır.  
  
     Şemalar, projenize eklenir veya atılan diske kaydedilir.  
  
    > [!NOTE]
    >  **Create Schema** komutu kullanılabilir de kısayol menüsünden XML Düzenleyicisi'nin ve altında **XML** menüsü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Düzenleyicisi](../xml-tools/xml-editor.md)