---
title: "Sınıfları ve türleri (Sınıf Tasarımcısı) yeniden düzenlemesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.ClassDesigner.OverrideMembersDialog
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
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 63a81fef59104d6731a782575fe1c3b23f48e304
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="refactoring-classes-and-types-class-designer"></a>Sınıfları ve Türleri Yeniden Düzenleme (Sınıf Tasarımcısı)
Kodu yeniden düzenleyin, daha kolay anlamak, bakımını yapmak ve iç yapısını ve nesnelerine şeklini değiştirerek daha verimli şekilde tasarlandığından, dış davranışını değil. Sınıf Tasarımcısı ve sınıf Ayrıntıları penceresi yapmak zorunda ve Visual Studio projenizi Visual C# .NET, Visual Basic .NET ya da C++ kodu yeniden zaman Tanıtımı ihtimalini hataları iş azaltmak için kullanın.  
  
> [!NOTE]
>  Proje kaynak kodu denetimi altında olduğundan ve kullanıma alınmadı proje dosyalarını salt okunur olabilir; Bu başvurulan bir projedir; veya, dosyaları diskte salt okunur olarak işaretlenmiş. Şu durumlardan birini projede çalışırken, çalışmanızı projenin durumuna bağlı olarak kaydetmek için çeşitli yollar ile sunulur. Yeniden düzenleme kod ve doğrudan düzenleme gibi başka bir şekilde değiştirme kodu için geçerlidir. Daha fazla bilgi için bkz: [salt okunur görüntüleme bilgileri](http://msdn.microsoft.com/en-us/33e2d3a9-1668-4d10-ae56-fa09b3156e0a).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|Destekleyici İçerik|  
|----------|------------------------|  
|**Sınıfları yeniden düzenleme:** yeniden düzenleme işlemi bir sınıfı kısmi sınıflara bölme ya da bir Özet temel sınıf uygulamak için kullanabilirsiniz.|-   [Nasıl yapılır: bir sınıfı kısmi sınıflara bölme](how-to-split-a-class-into-partial-classes.md)|  
|**Arabirimleri ile çalışma:** Sınıf Tasarımcısı'nda, uygulayabilirsiniz arabirim sınıf diyagramında arabirim yöntemleri için kod sağlayan bir sınıf bağlanarak.|-   [Nasıl yapılır: bir arabirim](how-to-implement-an-interface.md)|  
|**Türleri, tür üyeleri ve parametreleri yeniden düzenleme:** Sınıf Tasarımcısı kullanarak yapabilir türleri yeniden adlandırmak, tür üyeleri geçersiz kılma veya bir türden diğerine taşıyabilirsiniz. Boş değer atanabilir türler de oluşturabilirsiniz.|-   [Yeniden adlandırma türleri ve tür üyeleri](refactoring-classes-and-types.md#RenamingTypesAndMembers)<br />-   [Tür üyeleri bir türden diğerine taşıma](refactoring-classes-and-types.md#MovingTypeMembers)<br />-   [Nasıl yapılır: boş değer atanabilir tür oluşturma](how-to-create-a-nullable-type.md)|  
  
###  <a name="RenamingTypesAndMembers"></a>Yeniden adlandırma türleri ve tür üyeleri  
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
  
###  <a name="MovingTypeMembers"></a>Tür üyeleri bir türden diğerine taşıma  
Kullanarak **Sınıf Tasarımcısı**, her ikisi de geçerli sınıf diyagramında görünür durumdaysa başka bir tür için bir tür üyesi bir türden diğerine taşıyabilirsiniz.  
  
##### <a name="to-move-a-type-member-from-one-type-to-another"></a>Bir tür üyesi bir türden diğerine taşımak için  
  
1.  Tasarım yüzeyine görünür olan bir tür, başka bir türüne taşıyın ve ardından istediğiniz üye sağ **Kes**.  
  
2.  Hedef türünü sağ tıklatın ve ardından **Yapıştır**.  
  
     Özellik kaynak türünden kaldırılır ve hedef tipinde görüntülenir.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Türleri ve ilişkilendirmeleri görüntüleme](viewing-types-and-relationships.md)  
[Sınıfları ve türleri tasarlama](designing-classes-and-types.md)