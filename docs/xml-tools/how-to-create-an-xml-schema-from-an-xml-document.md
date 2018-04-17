---
title: 'Nasıl yapılır: bir XML belgesinden bir XML Şeması oluşturun | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9b19421bf9cb9d974a837f557d8b75ac4d5ba89c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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