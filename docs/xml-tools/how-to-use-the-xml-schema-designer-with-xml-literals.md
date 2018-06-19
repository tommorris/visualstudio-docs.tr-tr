---
title: "Nasıl yapılır: XML değişmez değerleri ile XML şema Tasarımcısı'nı kullanın"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d11803e7-f81a-41a2-a145-ba494a45cc93
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 589bfa54a0ba1a7efb2964cf5b74446ca9ffe10d
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2018
ms.locfileid: "34548223"
---
# <a name="how-to-use-the-xml-schema-designer-with-xml-literals"></a>Nasıl yapılır: XML değişmez değerleri ile XML şema Tasarımcısı'nı kullanın

Bu konuda, bir Visual Basic projesinde değişmez değer XML ile ilişkili bir şema görüntülemeyi açıklar.

## <a name="to-create-a-new-visual-basic-console-application-project"></a>Yeni bir Visual Basic konsol uygulama projesi oluşturmak için

1.  Visual Studio'yu başlatın.

2.  Gelen **dosya** menüsünde, select **yeni**ve ardından **proje**. **Yeni proje** iletişim kutusu görüntülenir. İçin **proje türleri**seçin **diğer diller** ve ardından **Visual Basic**. İçin **şablonları**, konsol uygulaması'nı seçin. Yazın `XMLLiterals` içinde **adı** alan ve bir proje konumda **konumu** alan. **Tamam**'ı tıklatın.

     Yeni poject oluşturulur. XMLLiterals proje bir Visual Basic kaynak dosyası içeren *Module1.vb*.

## <a name="to-add-an-existing-xsd-file-to-the-project"></a>Varolan bir XSD dosyası projeye eklemek için

1.  Yeni bir metin dosyasını Not Defteri'nde açın. XML Şeması örnek kodunu kopyalama [satın alma siparişi şeması](../xml-tools/sample-xsd-file-simple-schema.md) ve dosyaya yapıştırın.

2.  Bazı konumda adlı dosyayı kaydedin *PurchaseOrderSchema.xsd*.

3.  Çözüm Gezgini'nde proje adına sağ tıklayın, seçin **Ekle**ve ardından **varolan öğeyi**. **AddExisting öğesi** iletişim kutusu görüntülenir. Gözat *PurchaseOrderSchema.xsd* dosya, onu seçin ve ardından **Ekle**.

     XMLLiterals projeyi şimdi iki dosya içerir: *Module1.vb* ve *PurchaseOrderSchema.xsd*.

## <a name="to-add-visual-basic-code-with-an-xml-literal-based-on-the-xsd-file-included-in-the-project"></a>Projeye dahil XSD dosyası göre bir XML değişmez değeri ile Visual Basic kodu eklemek için

1.  Kodla *Module1.vb* aşağıdaki kod ile dosya:

   ```vb
   Imports <xmlns:ns="http://tempuri.org/PurchaseOrderSchema.xsd">

   Module Module1
       Sub Main()

           Dim XMLLiteral = <ns:PurchaseOrder OrderDate="1900-01-01">
                                <ns:ShipTo country="US">
                                    <ns:name>name1</ns:name>
                                    <ns:street>street1</ns:street>
                                    <ns:city>city1</ns:city>
                                    <ns:state>state1</ns:state>
                                    <ns:zip>1</ns:zip>
                                </ns:ShipTo>
                                <ns:BillTo country="US">
                                    <ns:name>name1</ns:name>
                                    <ns:street>street1</ns:street>
                                    <ns:city>city1</ns:city>
                                    <ns:state>state1</ns:state>
                                    <ns:zip>1</ns:zip>
                                </ns:BillTo>
                            </ns:PurchaseOrder>

       End Sub
   End Module
   ```

2.  XML değişmez değeri veya bir XML ad alanı içe aktardığınız tüm XML düğümünü sağ tıklatın ve seçin **Göster şema Explorer'da**.

     **XML Şeması Explorer** XML Şeması kümesiyle ilişkili XML değişmez değeri olan bir Visual Basic dosyayı yan yana görüntülenir.