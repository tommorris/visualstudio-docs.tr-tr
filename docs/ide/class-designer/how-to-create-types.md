---
title: 'Nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.Clr.ClrAttributesDialog
helpviewer_keywords:
- custom attributes, applying
- class diagrams, creating types
- classes [Visual Studio], creating with Class Designer
- Class Designer [Visual Studio], creating classes
- types [Visual Studio], class diagrams
- attributes [Visual Studio], applying custom
ms.assetid: 94458c31-28bc-40e2-9737-85868788a0e5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22260ee75a1c64de842da41b292fbeebeb6cf6ef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-types-by-using-class-designer"></a>Nasıl Yapılır: Sınıf Tasarımcısı Kullanarak Tür Oluşturma
C# ve Visual Basic projeleri için yeni türleri tasarlamak için bir sınıf diyagramında oluşturun. Varolan türlerini görmek için bkz: [nasıl yapılır: Varolan görünüm türleri](how-to-view-existing-types.md).  
  
-   [Yeni bir tür oluşturun](#CreateType)  
  
-   [Özel bir öznitelik türü için geçerli](#CustAttributeType)  
  
-   [Özel bir öznitelik türü üyesi Uygula](#CustAttributeMember)  
  
##  <a name="CreateType"></a> Yeni bir tür oluşturun  
  
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
    |**için**|**Ekle**|  
    |Sınıflar, soyut sınıflar, yapılar veya struct'lar|Yöntemler, özellikler, alanlar, olaylar, yapıcılar (yöntem), yıkıcılar (yöntem) ve türü tanımlayan sabitler|  
    |Numaralandırmalar|Numaralandırmayı oluşturan alan değerleri|  
    |Arabirimler|Yöntemler, özellikler ve arabirimi oluşturan olaylar|  
    |Temsilci|Temsilciyi tanımlayan parametreler|  
    |Modül|Yöntemler, özellikler, alanlar, olaylar, yapıcılar (yöntem) ve modülü tanımlayan sabitler|  
  
     Bkz: [üye oluşturma](creating-and-configuring-type-members.md#CreateMembers).  
  
##  <a name="CustAttributeType"></a> Özel bir öznitelik türü için geçerli  
  
1.  Bir sınıf diyagramında türe ait şekle tıklayın.  
  
2.  Özellikleri penceresinde yanına **özel öznitelikleri** özellik türü için üç nokta (...) düğmesini tıklatın.  
  
3.  Satır başına bir olmak üzere, bir ya da daha fazla özel öznitelik ekleyin. Bunları ayraçlar içine almayın.  
  
     İşiniz bittiğinde özel öznitelikler türe uygulanır.  
  
##  <a name="CustAttributeMember"></a> Özel bir öznitelik türü üyesi Uygula  
  
1.  Bir sınıf diyagramında kendi türünün şeklinde üyenin adına veya Sınıf Ayrıntıları penceresinde satırına tıklayın.  
  
2.  Üyenin Özellikleri penceresinde bulabilirsiniz **özel öznitelikleri** özelliği.  
  
3.  Satır başına bir olmak üzere, bir ya da daha fazla özel öznitelik ekleyin. Bunları ayraçlar içine almayın.  
  
     İşiniz bittiğinde özel öznitelikler türe uygulanır.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Nasıl yapılır: türler arasında devralmayı oluşturma](how-to-create-inheritance-between-types.md)  
[Nasıl yapılır: türler arasında ilişkiler oluşturmak](how-to-create-associations-between-types.md)
[oluşturma ve yapılandırma tür üyeleri](creating-and-configuring-type-members.md)   
[Sınıf diyagramları ile çalışma](working-with-class-diagrams.md)   
[Sınıfları ve türleri tasarlama](designing-classes-and-types.md)