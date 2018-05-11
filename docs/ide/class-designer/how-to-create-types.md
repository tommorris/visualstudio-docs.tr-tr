---
title: 'Nasıl Yapılır: Sınıf Tasarımcısı Kullanarak Tür Oluşturma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
ms.openlocfilehash: c7c41f7c5a9fb9540661440a19462ee12b1aadd9
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
# <a name="how-to-create-types-by-using-class-designer"></a>Nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturma

C# ve Visual Basic projeleri için yeni türleri tasarlamak için bir sınıf diyagramında oluşturun. Varolan türlerini görmek için bkz: [nasıl yapılır: Varolan görünüm türleri](how-to-view-existing-types.md).

##  <a name="CreateType"></a> Yeni bir tür oluşturun

1.  İçinde **araç**altında **Sınıf Tasarımcısı**, bunlardan birini sınıf diyagramı üzerine sürükleyin:

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

     Bkz: [üye oluşturma](creating-and-configuring-type-members.md#create-members).

##  <a name="CustAttributeType"></a> Özel bir öznitelik türü için geçerli

1.  Bir sınıf diyagramında türe ait şekle tıklayın.

2.  İçinde **özellikleri**, yanına **özel öznitelikleri** özellik türü için üç nokta (...) düğmesini tıklatın.

3.  Satır başına bir olmak üzere, bir ya da daha fazla özel öznitelik ekleyin. Bunları ayraçlar içine almayın.

   Özel özniteliklerin türü için uygulanır.

##  <a name="CustAttributeMember"></a> Özel bir öznitelik türü üyesi Uygula

1.  Bir sınıf diyagramında kendi türünün şeklinde üyenin adına veya Sınıf Ayrıntıları penceresinde satırına tıklayın.

2.  İçinde **özellikleri**, üyenin Bul **özel öznitelikleri** özelliği.

3.  Satır başına bir olmak üzere, bir ya da daha fazla özel öznitelik ekleyin. Bunları ayraçlar içine almayın.

   Özel özniteliklerin türü için uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: türler arasında devralmayı oluşturma](how-to-create-inheritance-between-types.md)
- [Nasıl yapılır: türleri arasındaki ilişkilendirmeleri oluşturma](how-to-create-associations-between-types.md)
- [Tür Üyeleri Oluşturma ve Yapılandırma](creating-and-configuring-type-members.md)
- [Sınıf Diyagramları ile Çalışma](working-with-class-diagrams.md)
- [Sınıfları ve türleri tasarlama](designing-and-viewing-classes-and-types.md)
