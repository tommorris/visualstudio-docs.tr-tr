---
title: "Nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.Clr.ClrAttributesDialog
helpviewer_keywords:
- custom attributes, applying
- class diagrams, creating types
- classes [Visual Studio], creating with Class Designer
- Class Designer [Visual Studio], creating classes
- types [Visual Studio], class diagrams
- attributes [Visual Studio], applying custom
ms.assetid: 94458c31-28bc-40e2-9737-85868788a0e5
caps.latest.revision: "41"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cf8691e4e38ae19aa1e8e04257f208241c02efac
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-types-by-using-class-designer"></a>Nasıl Yapılır: Sınıf Tasarımcısı Kullanarak Tür Oluşturma
Visual C# .NET ve Visual Basic .NET projeleri için yeni türleri tasarlamak için bir sınıf diyagramında oluşturun. Varolan türlerini görmek için bkz: [nasıl yapılır: görünüm varolan türleri (Sınıf Tasarımcısı)](../ide/how-to-view-existing-types-class-designer.md).  
  
-   [Yeni bir tür oluşturun](#CreateType)  
  
-   [Özel bir öznitelik türü için geçerli](#CustAttributeType)  
  
-   [Özel bir öznitelik türü üyesi Uygula](#CustAttributeMember)  
  
##  <a name="CreateType"></a>Yeni bir tür oluşturun  
  
1.  Araç Kutusu'nda, Sınıf Tasarımcısı'nın altında aşağıdakilerden birini bir sınıf diyagramına sürükleyin:  
  
    -   **Sınıf** veya **soyut sınıf**  
  
    -   **Enum**  
  
    -   **Arabirimi**  
  
    -   **Yapı** (VB) veya **yapısı** (C#)  
  
    -   **Temsilci**  
  
    -   **Modül** (yalnızca VB)  
  
2.  Türü adlandırın. Daha sonra erişim düzeyini seçin.  
  
3.  Tür için başlangıç kodunu eklemek istediğiniz dosyayı seçin:  
  
    -   Yeni bir dosya oluşturun ve geçerli projeye eklemek için seçin **oluştur yeni dosya** ve dosya adı.  
  
    -   Kod için varolan bir dosyayı eklemek için seçin **eklemek için var olan dosya**.  
  
         Çözümünüzün birden çok uygulama arasında kod paylaşan proje varsa, ancak yalnızca karşılık gelen sınıf dosyası aynı uygulama projesinde olması veya paylaşılan projesinde uygulama projesi sınıf diyagramında yeni türü ekleyebilirsiniz.  
  
4.  Şimdi, türü tanımlamak için diğer öğeleri ekleyin:  
  
    |||  
    |-|-|  
    |**İçin**|**Ekle**|  
    |Sınıflar, soyut sınıflar, yapılar veya struct'lar|Yöntemler, özellikler, alanlar, olaylar, yapıcılar (yöntem), yıkıcılar (yöntem) ve türü tanımlayan sabitler|  
    |Numaralandırmalar|Numaralandırmayı oluşturan alan değerleri|  
    |Arabirimler|Yöntemler, özellikler ve arabirimi oluşturan olaylar|  
    |Temsilci|Temsilciyi tanımlayan parametreler|  
    |Modül|Yöntemler, özellikler, alanlar, olaylar, yapıcılar (yöntem) ve modülü tanımlayan sabitler|  
  
     Bkz: [üye oluşturma](../ide/creating-and-configuring-type-members-class-designer.md#CreateMembers).  
  
##  <a name="CustAttributeType"></a>Özel bir öznitelik türü için geçerli  
  
1.  Bir sınıf diyagramında türe ait şekle tıklayın.  
  
2.  Özellikleri penceresinde yanına **özel öznitelikleri** özellik türü için üç nokta (...) düğmesini tıklatın.  
  
3.  Satır başına bir olmak üzere, bir ya da daha fazla özel öznitelik ekleyin. Bunları ayraçlar içine almayın.  
  
     İşiniz bittiğinde özel öznitelikler türe uygulanır.  
  
##  <a name="CustAttributeMember"></a>Özel bir öznitelik türü üyesi Uygula  
  
1.  Bir sınıf diyagramında kendi türünün şeklinde üyenin adına veya Sınıf Ayrıntıları penceresinde satırına tıklayın.  
  
2.  Üyenin Özellikleri penceresinde bulabilirsiniz **özel öznitelikleri** özelliği.  
  
3.  Satır başına bir olmak üzere, bir ya da daha fazla özel öznitelik ekleyin. Bunları ayraçlar içine almayın.  
  
     İşiniz bittiğinde özel öznitelikler türe uygulanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: devralma türleri (Sınıf Tasarımcısı) arasındaki oluştur](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [Nasıl yapılır: türleri (Sınıf Tasarımcısı) arasındaki ilişkilendirmeleri oluşturma](../ide/how-to-create-associations-between-types-class-designer.md)   
 [Oluşturma ve yapılandırma türü üyeleri (Sınıf Tasarımcısı)](../ide/creating-and-configuring-type-members-class-designer.md)   
 [Sınıf diyagramları (Sınıf Tasarımcısı) ile çalışma](../ide/working-with-class-diagrams-class-designer.md)   
 [Sınıfları ve türleri (Sınıf Tasarımcısı) tasarlama](../ide/designing-classes-and-types-class-designer.md)