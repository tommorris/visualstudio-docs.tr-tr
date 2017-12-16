---
title: "Nasıl yapılır: bir arabirim (Sınıf Tasarımcısı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Studio], implementing
- interfaces [Visual Studio]
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 469e7876900c61589afac089b848bd712703b1e6
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/15/2017
---
# <a name="how-to-implement-an-interface-class-designer"></a>Nasıl Yapılır: Arabirimi Uygulama (Sınıf Tasarımcısı)
Sınıf Tasarımcısı'nda kod için arabirim yöntemleri sağlayan bir sınıf bağlanarak arabirim sınıf diyagramında uygulayabilirsiniz. Sınıf Tasarımcısı bir arabirim uygulaması oluşturur ve bir devralma ilişkisi arabirimi ve sınıfı arasındaki ilişkiyi gösterir. Arabirim arabirimi ve sınıf arasında bir devralma satırı çizim veya sınıf görünümünden arabirimi sürükleyerek uygulayabilirsiniz.  
  
> [!TIP]
>  Diğer türleri oluşturmak aynı şekilde arabirimleri oluşturabilirsiniz. Arabirim var, ancak sınıf diyagramında görünmez, ardından ilk görüntüleyin. Daha fazla bilgi için bkz: [nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturma](how-to-create-types.md) ve [nasıl yapılır: görünüm varolan türleri](how-to-view-existing-types.md).  
  
### <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>Devralma Satırı çizerek bir arabirim uygulamak için  
  
1.  Sınıf diyagramında arabirimi ve arabirimini uygulayan sınıf görüntüler.  
  
2.  Devralma Satırı sınıf ve arabirim çizin.  
  
     Lolipop sınıfa bağlı görünür ve arabirim adı ile bir etiket devralma ilişkisi tanımlar. Visual Studio için tüm arabirim üyelerini saplamalar oluşturur.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: devralma türleri arasında oluşturma](how-to-create-inheritance-between-types.md).  
  
### <a name="to-implement-an-interface-from-the-class-view-window"></a>Sınıf Görünümü penceresinden bir arabirim uygulamak için  
  
1.  Sınıf diyagramında arabirimi uygulamak istediğiniz sınıfı görüntüler.  
  
2.  Sınıf Görünümü açın ve arabirim bulun.  
  
    > [!TIP]
    >  Sınıf Görünümü açık değilse, sınıf görünümünden açmak **Görünüm** menüsü. Sınıf Görünümü hakkında daha fazla bilgi için bkz: [görüntüleme sınıflar ve Their üyeleri](http://msdn.microsoft.com/en-us/71e9e8f3-261a-4e0c-87bf-5ec48b8bf333).  
  
3.  Arabirim düğümü diyagramı sınıfı şekle sürükleyin.  
  
     Lolipop sınıfa bağlı görünür ve arabirim adı ile bir etiket devralma ilişkisi tanımlar. Visual Studio için tüm arabirim üyelerini saplamalar oluşturur; Bu noktada, arabirim uygulanır.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturma](how-to-create-types.md)   
[Nasıl yapılır: Varolan türleri görüntüleme](how-to-view-existing-types.md)   
[Nasıl yapılır: türler arasında devralmayı oluşturma](how-to-create-inheritance-between-types.md)   
[Sınıfları ve türleri yeniden düzenleme](refactoring-classes-and-types.md)