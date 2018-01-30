---
title: "Nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: db46a4fa0faa568597deccddb528d8765e048e22
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-create-types-by-using-class-designer"></a>Nasıl Yapılır: Sınıf Tasarımcısı Kullanarak Tür Oluşturma
C# ve Visual Basic projeleri için yeni türleri tasarlamak için bir sınıf diyagramında oluşturun. Varolan türlerini görmek için bkz: [nasıl yapılır: Varolan görünüm türleri](how-to-view-existing-types.md).  
  
-   [Yeni bir tür oluşturun](#CreateType)  
  
-   [Özel bir öznitelik türü için geçerli](#CustAttributeType)  
  
-   [Özel bir öznitelik türü üyesi Uygula](#CustAttributeMember)  
  
##  <a name="CreateType"></a>Yeni bir tür oluşturun  
  
1.  Araç Kutusu'nda, Sınıf Tasarımcısı'nın altında aşağıdakilerden birini bir sınıf diyagramına sürükleyin:  
  
    -   **Sınıf** veya **soyut sınıf**  
  
    -   **Enum**  
  
    -   **Interface**  
  
    -   **Yapı** (VB) veya **yapısı** (C#)  
  
    -   **Delegate**  
  
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
  
     Bkz: [üye oluşturma](creating-and-configuring-type-members.md#CreateMembers).  
  
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
  
## <a name="see-also"></a>Ayrıca bkz.
[Nasıl yapılır: türler arasında devralmayı oluşturma](how-to-create-inheritance-between-types.md)  
[Nasıl yapılır: türler arasında ilişkiler oluşturmak](how-to-create-associations-between-types.md)
[oluşturma ve yapılandırma tür üyeleri](creating-and-configuring-type-members.md)   
[Sınıf diyagramları ile çalışma](working-with-class-diagrams.md)   
[Sınıfları ve türleri tasarlama](designing-classes-and-types.md)