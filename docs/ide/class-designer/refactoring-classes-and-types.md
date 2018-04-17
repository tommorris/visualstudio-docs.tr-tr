---
title: Sınıfları ve türleri (Sınıf Tasarımcısı) yeniden düzenlemesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
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
ms.openlocfilehash: d9f84c0b6fe661b480f13f03221360c8f7bc6583
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="refactoring-classes-and-types-class-designer"></a>Sınıfları ve Türleri Yeniden Düzenleme (Sınıf Tasarımcısı)

Kodu yeniden düzenleyin, daha kolay anlamak, bakımını yapmak ve iç yapısını ve nesnelerine şeklini değiştirerek daha verimli şekilde tasarlandığından, dış davranışını değil. Sınıf Tasarımcısı ve yapmanız gereken iş azaltmak için sınıf Ayrıntıları penceresi ve C#, Visual Basic ya da C++ kodu Visual Studio projenizi yeniden olduğunda hataları Tanıtımı ihtimalini kullanın.

> [!NOTE]
> Proje kaynak kodu denetimi altında olduğundan ve işaretlenmediği çıkışı, başvurulan bir projedir ya da kendi dosya diskte salt okunur olarak işaretlenmiş bir proje dosyalarını salt okunur olabilir. Şu durumlardan birini projede çalışırken, çalışmanızı projenin durumuna bağlı olarak kaydetmek için çeşitli yollar ile sunulur. Yeniden düzenleme kod ve doğrudan düzenleme gibi başka bir şekilde değiştirme kodu için geçerlidir.

## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|Destekleyici İçerik|  
|----------|------------------------|  
|**Sınıfları yeniden düzenleme:** yeniden düzenleme işlemi bir sınıfı kısmi sınıflara bölme ya da bir Özet temel sınıf uygulamak için kullanabilirsiniz.|-   [Nasıl yapılır: bir sınıfı kısmi sınıflara bölme](how-to-split-a-class-into-partial-classes.md)|  
|**Arabirimleri ile çalışma:** Sınıf Tasarımcısı'nda, uygulayabilirsiniz arabirim sınıf diyagramında arabirim yöntemleri için kod sağlayan bir sınıf bağlanarak.|-   [Nasıl yapılır: bir arabirim](how-to-implement-an-interface.md)|  
|**Türleri, tür üyeleri ve parametreleri yeniden düzenleme:** Sınıf Tasarımcısı kullanarak yapabilir türleri yeniden adlandırmak, tür üyeleri geçersiz kılma veya bir türden diğerine taşıyabilirsiniz. Boş değer atanabilir türler de oluşturabilirsiniz.|-   [Yeniden adlandırma türleri ve tür üyeleri](refactoring-classes-and-types.md#RenamingTypesAndMembers)<br />-   [Tür üyeleri bir türden diğerine taşıma](refactoring-classes-and-types.md#MovingTypeMembers)<br />-   [Nasıl yapılır: boş değer atanabilir tür oluşturma](how-to-create-a-nullable-type.md)|  
  
###  <a name="RenamingTypesAndMembers"></a> Yeniden adlandırma türleri ve tür üyeleri  
Sınıf Tasarımcısı'nda bir tür veya üye türü sınıf diyagramında veya özellikleri penceresinde adlandırabilirsiniz. Sınıf Ayrıntıları penceresinde üyesi ancak bir tür adını değiştirebilirsiniz. Bir tür veya tür üyesi yeniden adlandırma, tüm windows ve burada eski adı görünen kodu konumları yayar.  
  
##### <a name="to-rename-a-name-in-the-class-designer"></a>Sınıf Tasarımcısı'nda bir ad yeniden adlandırmak için  
  
1.  Sınıf diyagramında tür veya üye seçin ve adına tıklayın.  
  
     Üyenin adını düzenlenebilir olur.  
  
2.  Tür veya üye türü için yeni adı yazın  
  
##### <a name="to-rename-a-name-in-the-class-details-window"></a>Sınıf Ayrıntıları penceresinde bir adı yeniden adlandırmak için  
  
1.  Sınıf ayrıntıları penceresini görüntülemek için türü veya tür üyesi sağ tıklayın ve ardından **sınıfı ayrıntıları**.  
  
     Sınıf Ayrıntıları penceresi görünür.  
  
2.  İçinde **adı** sütun türü üyesinin adını değiştirme  
  
3.  Odağı hücreden taşımak için basın **ENTER** anahtar veya uzakta hücreyi tıklatın.  
  
    > [!NOTE]
    >  Sınıf Ayrıntıları penceresinde üyesi ancak bir tür adını değiştirebilirsiniz.  
  
##### <a name="to-rename-a-name-in-the-properties-window"></a>Bir ad Özellikleri penceresinde yeniden adlandırmak için  
  
1.  Sınıf diyagramında veya sınıf Ayrıntıları penceresi, tür veya üye sağ tıklayın ve ardından **özellikleri**.  
  
     Özellikler penceresi görüntülenir ve türü veya türü üyesinin özelliklerini görüntüler.  
  
2.  İçinde **adı** özelliği, türü adını değiştirin veya üye yazın.  
  
     Yeni bir ad, tüm windows ve burada eski adı görünen kodu konumları geçerli projedeki yayar.  
  
###  <a name="MovingTypeMembers"></a> Tür üyeleri bir türden diğerine taşıma  
Kullanarak **Sınıf Tasarımcısı**, her ikisi de geçerli sınıf diyagramında görünür durumdaysa başka bir tür için bir tür üyesi bir türden diğerine taşıyabilirsiniz.  
  
##### <a name="to-move-a-type-member-from-one-type-to-another"></a>Bir tür üyesi bir türden diğerine taşımak için  
  
1.  Tasarım yüzeyine görünür olan bir tür, başka bir türüne taşıyın ve ardından istediğiniz üye sağ **Kes**.  
  
2.  Hedef türünü sağ tıklatın ve ardından **Yapıştır**.  
  
     Özellik kaynak türünden kaldırılır ve hedef tipinde görüntülenir.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Türleri ve İlişkileri Görüntüleme](viewing-types-and-relationships.md)  
[Sınıfları ve türleri tasarlama](designing-classes-and-types.md)