---
title: 'Nasıl yapılır: türleri (Sınıf Tasarımcısı) arasındaki ilişkilendirmeleri oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.associationline
helpviewer_keywords:
- types [Visual Studio], associations
- association lines, defining (Class Designer)
- defining association lines (Class Designer)
- associations, types
- association lines
ms.assetid: adccb9c8-2f8a-4086-9fa9-f70f99fb6e00
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4d81e2f3bb671f5c88b08bf1cb26db42a6c4383a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-associations-between-types-class-designer"></a>Nasıl yapılır: türleri (Sınıf Tasarımcısı) arasındaki ilişkilendirmeleri oluşturma
Sınıf Tasarımcısı'nda ilişkilendirme çizgileri, bir diyagramdaki sınıfların nasıl ilişkili olduğunu gösterir. İlişkilendirme çizgisi, projenizdeki başka bir sınıfın özellik veya alan türü olan bir sınıfı temsil eder. İlişkilendirme çizgileri genellikle, projenizdeki sınıflar arasında en önemli ilişkileri göstermek için kullanılır.  
  
Tüm alanları ve özellikleri ilişkilendirmeler halinde görüntüleyebilirsiniz; bununla birlikte diyagramda vurgulamak istediğiniz unsura bağlı olarak yalnızca önemli üyeleri ilişkilendirme olarak göstermek daha anlamlı olur. (Daha az önemli üyeleri normal üye olarak gösterebilir veya bütünüyle gizleyebilirsiniz.)  
  
> [!NOTE]
>  Sınıf Tasarımcısı yalnızca tek yönlü ilişkilendirmeleri destekler.  
  
### <a name="to-define-an-association-line-in-the-class-diagram"></a>Sınıf Diyagramı'nda bir ilişkilendirme çizgisi tanımlamak için  
  
1.  Sınıf Tasarımcısı altında araç seçin **ilişkilendirme**.  
  
2.  İlişkilendirme ile bağlamak istediğiniz iki şekil arasına bir çizgi çizin.  
  
     İlk sınıfta yeni bir özellik oluşturulur. Bu özellik varsayılan ada sahip bir ilişkilendirme çizgisi görüntüler (şekildeki bir bölme içinde özellik olarak değil). Türü ise, ilişkilendirme çizgisinin işaret ettiği şekildir.
  
### <a name="to-change-the-name-of-an-association"></a>İlişkilendirmenin adını değiştirmek için  
  
-   Diyagram yüzeyinde ilişkilendirme çizgisinin etiketine tıklayın ve etiketi düzenleyin.  
  
 \- veya -  
  
1.  İlişkilendirme olarak gösterilen özelliği içeren şekle tıklayın.  
  
     Şekil odağı alır ve üyeleri Sınıf Ayrıntıları penceresinde ve Özellikler penceresinde görüntülenir.  
  
2.  Sınıf Ayrıntıları penceresinde ya da Özellikler penceresinde bu özelliğe ilişkin ad alanını düzenleyin ve Enter tuşuna basın.  
  
     Adı güncellenir **sınıfı ayrıntıları** İlişkilendirme satırında, özellikleri penceresinde ve kod penceresi.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Nasıl yapılır: üye gösterimi ile ilişkilendirme gösterimi arasında değişiklik](how-to-change-between-member-notation-and-association-notation.md)