---
title: "Nasıl yapılır: XML değişmez değerleri ile XML şema Tasarımcısı'nı kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d11803e7-f81a-41a2-a145-ba494a45cc93
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: 5eea45aafebe8c20431de5b2d3bd299789bf7285
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-xml-schema-designer-with-xml-literals"></a>Nasıl yapılır: XML değişmez değerleri ile XML şema Tasarımcısı'nı kullanın
Bu konuda, bir Visual Basic projesinde değişmez değer XML ile ilişkili bir şema görüntülemeyi açıklar.  
  
### <a name="to-create-a-new-visual-basic-console-application-project"></a>Yeni bir Visual Basic konsol uygulama projesi oluşturmak için  
  
1.  Visual Studio'yu başlatın.  
  
2.  Gelen **dosya** menüsünde, select **yeni**ve ardından **proje**. **Yeni proje** iletişim kutusu görüntülenir. İçin **proje türleri**seçin **diğer diller** ve ardından **Visual Basic**. İçin **şablonları**, konsol uygulaması'nı seçin. Yazın `XMLLiterals` içinde **adı** alan ve bir proje konumda **konumu** alan. **Tamam**'ı tıklatın.  
  
     Yeni poject oluşturulur. XMLLiterals proje bir Visual Basic kaynak dosyası, Module1.vb içeriyor.  
  
### <a name="to-add-an-existing-xsd-file-to-the-project"></a>Varolan bir XSD dosyası projeye eklemek için  
  
1.  Açık bir yeni metin dosyası Notepad.Copy XML Şeması örnek kodu [satın alma siparişi şeması](../xml-tools/sample-xsd-file-simple-schema.md) ve dosyaya yapıştırın.  
  
2.  Bazı konumda PurchaseOrderSchema.xsd ada sahip dosyayı kaydedin.  
  
3.  Çözüm Gezgini'nde proje adına sağ tıklayın, seçin **Ekle**ve ardından **varolan öğeyi...** . **AddExisting öğesi** iletişim kutusu görüntülenir. PurchaseOrderSchema.xsd dosyasına göz atın, onu seçin ve ardından **Ekle**.  
  
     XMLLiterals projeyi şimdi iki dosya içerir: Module1.vb ve PurchaseOrderSchema.xsd.  
  
### <a name="to-add-visual-basic-code-with-an-xml-literal-based-on-the-xsd-file-included-in-the-project"></a>Projeye dahil XSD dosyası göre bir XML değişmez değeri ile Visual Basic kodu eklemek için  
  
1.  Module1.vb dosyasındaki kodu aşağıdaki kodla değiştirin:  
  
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
  
     XML şema Explorer ayarlamak XML değişmez değer assotiated XML Şeması sahip bir Visual Basic dosyası yan yana görüntülenir.