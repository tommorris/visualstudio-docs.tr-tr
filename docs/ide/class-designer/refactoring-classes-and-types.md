---
title: Yeniden adlandırın ve sınıfları ve türleri Sınıf Tasarımcısı'nda taşıma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.ClassDesigner.OverrideMembersDialog
helpviewer_keywords:
- members, overriding
- overriding members
- classes [Visual Studio], refactoring
- type members, overriding
- refactoring, types
- types [Visual Studio], refactoring
- Class Designer [Visual Studio], refactoring classes
- refactoring, classes
ms.assetid: dcf07bb4-fa3b-4224-9dec-566fd924a8ce
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee534ca3c8b2a1cef441005586bc58601fb15ed7
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957439"
---
# <a name="refactor-classes-and-types-in-class-designer"></a>Sınıfları ve türleri Sınıf Tasarımcısı'nda yeniden Düzenle

Kodu yeniden düzenleyin, daha kolay anlamak, bakımını yapmak ve iç yapısını ve nesnelerine şeklini değiştirerek daha verimli şekilde tasarlandığından, dış davranışını değil. Sınıf Tasarımcısı ve yapmanız gereken iş azaltmak için sınıf Ayrıntıları penceresi ve C#, Visual Basic ya da C++ kodu Visual Studio projenizi yeniden olduğunda hataları Tanıtımı ihtimalini kullanın.

> [!NOTE]
> Proje kaynak kodu denetimi altında olduğundan ve işaretlenmediği çıkışı, başvurulan bir projedir ya da kendi dosya diskte salt okunur olarak işaretlenmiş bir proje dosyalarını salt okunur olabilir. Şu durumlardan birini projede çalışırken, çalışmanızı projenin durumuna bağlı olarak kaydetmek için çeşitli yollar ile sunulur. Yeniden düzenleme kod ve doğrudan düzenleme gibi başka bir şekilde değiştirme kodu için geçerlidir.

## <a name="common-tasks"></a>Ortak görevler

|Görev|Destekleyici İçerik|
|----------|------------------------|
|**Sınıfları yeniden düzenleme:** yeniden düzenleme işlemi bir sınıfı kısmi sınıflara bölme ya da bir Özet temel sınıf uygulamak için kullanabilirsiniz.|-   [Nasıl yapılır: bir sınıfı kısmi sınıflara bölme](how-to-split-a-class-into-partial-classes.md)|
|**Arabirimleri ile çalışma:** Sınıf Tasarımcısı'nda, uygulayabilirsiniz arabirim sınıf diyagramında arabirim yöntemleri için kod sağlayan bir sınıf bağlanarak.|-   [Nasıl yapılır: bir arabirim](how-to-implement-an-interface.md)|
|**Türleri, tür üyeleri ve parametreleri yeniden düzenleme:** Sınıf Tasarımcısı kullanarak yapabilir türleri yeniden adlandırmak, tür üyeleri geçersiz kılma veya bir türden diğerine taşıyabilirsiniz. Boş değer atanabilir türler de oluşturabilirsiniz.|-   [Yeniden Adlandır türleri ve tür üyeleri](#rename-types-and-type-members)<br />-   [Tür üyeleri bir türden diğerine taşıma](#move-type-members-from-one-type-to-another)<br />-   [Nasıl yapılır: boş değer atanabilir tür oluşturma](how-to-create-a-nullable-type.md)|

## <a name="rename-types-and-type-members"></a>Yeniden Adlandır türleri ve tür üyeleri

Sınıf Tasarımcısı'nda, bir tür veya sınıf diyagramında ya da buna bir türünün bir üyesi adlandırabilirsiniz **özellikleri** penceresi. İçinde **sınıfı ayrıntıları** penceresinde üyesi ancak bir tür adını değiştirebilirsiniz. Bir tür veya tür üyesi yeniden adlandırma, tüm windows ve burada eski adı görünen kodu konumları yayar.

### <a name="rename-in-the-class-designer"></a>Sınıf Tasarımcısı'nda yeniden adlandırın

1. Sınıf diyagramında tür veya üye seçin ve adını seçin.

     Üyenin adını düzenlenebilir olur.

2. Tür veya üye türü için yeni adı yazın

### <a name="rename-in-the-class-details-window"></a>Sınıf Ayrıntıları penceresinde yeniden adlandırma

1. Görüntülenecek **sınıfı ayrıntıları** penceresinde, tür veya tür üyesi sağ tıklatın ve seçin **sınıfı ayrıntıları**.

     **Sınıfı ayrıntıları** penceresi görüntülenir.

2. İçinde **adı** sütun türü üyesinin adını değiştirme

3. Odağı hücreden taşımak için basın **Enter** anahtar veya uzakta hücreyi tıklatın.

    > [!NOTE]
    > İçinde **sınıfı ayrıntıları** penceresinde üyesi ancak bir tür adını değiştirebilirsiniz.

### <a name="rename-in-the-properties-window"></a>Özellikler penceresinde yeniden adlandırma

1. Sınıf diyagramında veya **sınıfı ayrıntıları** penceresinde, tür veya üye sağ tıklayın ve ardından **özellikleri**.

     **Özellikleri** penceresi görüntülenir ve türü veya türü üyesinin özelliklerini görüntüler.

2. İçinde **adı** özelliği, türü adını değiştirin veya üye yazın.

     Yeni bir ad, tüm windows ve burada eski adı görünen kodu konumları geçerli projedeki yayar.

## <a name="move-type-members-from-one-type-to-another"></a>Tür üyeleri bir türden diğerine taşıma

Kullanarak **Sınıf Tasarımcısı**, bir tür üyesi başka bir türüne bir türden diğerine taşıyabilirsiniz. Her iki tür geçerli sınıf diyagramında görünür olması gerekir.

1. Tasarım yüzeyine görünür olan bir tür, başka bir türüne taşıyın ve ardından istediğiniz üye sağ **Kes**.

2. Hedef türü sağ tıklatıp **Yapıştır**.

     Özellik kaynak türünden kaldırılır ve hedef tipinde görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

- [Türleri ve İlişkileri Görüntüleme](viewing-types-and-relationships.md)
- [Sınıfları ve türleri tasarlama](designing-classes-and-types.md)