---
title: 'Nasıl yapılır: bir XSD şemasını temel alan bir XML belgesi oluşturma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 11ec095bd3228eb2291f77bf9fadceb0b74d8a37
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>Nasıl yapılır: bir XSD şemasını temel alan bir XML belgesi oluşturma

**Örnek XML oluşturmak** özelliği XML Şeması (XSD) dosyasını temel alan bir örnek XML dosyası oluşturur.

 Aşağıdaki senaryolar için bu seçeneği kullanabilirsiniz:

-   Şemanızı çeşitli yapılardan kullanımını anlamak için.

-   Şema ne yaptığını onaylamak için bunu yapmak için tasarlanmıştır.

**Örnek XML oluşturmak** özelliği yalnızca genel öğeleri üzerinde kullanılabilir ve geçerli bir XML Şeması kümesi gerektirir.

Bu özellik genellikle geçerli XML belgelerini oluşturur. Şema bir veya daha fazlasını içeriyorsa, ancak örnek geçerli olmayabilir:

-   `xs:key`, `xs:keyref`, Ve `xs:unique` kimlik kısıtlamaları.

-   `xs:pattern` yönü.

-   Numaralandırmalar `xs:QName` türü.

-   `xs:ENTITY`, `xs:ENTITIES`, ve `xs:NOTATION` türleri.

Ayrıca, unutmayın `xs:base64Binary` içeriği yalnızca numaralandırma türü için şema oluşursa oluşturulmayacak.

## <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>XSD dosyasını temel alan bir XML örneği belgesi oluşturmak için

1.  Adımları [nasıl yapılır: oluşturma ve bir XSD şema dosyası düzenleme](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).

2.  İçinde [XML Şeması Explorer](../xml-tools/xml-schema-explorer.md), sağ `PurchaseOrder` genel öğesi. Seçin **örnek XML oluşturmak**.

     Bu seçeneği seçtiğinizde, aşağıdaki örnek XML içeriği PurchaseOrder.xml dosyasıyla oluşturulur ve XML Düzenleyicisi'nde açılır:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <PurchaseOrder OrderDate="1900-01-01" xmlns="http://tempuri.org/PurchaseOrderSchema.xsd">
      <ShipTo country="US">
        <name>name1</name>
        <street>street1</street>
        <city>city1</city>
        <state>state1</state>
        <zip>1</zip>
      </ShipTo>
      <ShipTo country="US">
        <name>name2</name>
        <street>street2</street>
        <city>city2</city>
        <state>state2</state>
        <zip>-79228162514264337593543950335</zip>
      </ShipTo>
      <BillTo country="US">
        <name>name1</name>
        <street>street1</street>
        <city>city1</city>
        <state>state1</state>
        <zip>1</zip>
      </BillTo>
    </PurchaseOrder>
    ```

## <a name="see-also"></a>Ayrıca Bkz.

- [XML Verileriyle Çalışma](../xml-tools/working-with-xml-data.md)