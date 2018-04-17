---
title: 'Nasıl yapılır: bir arabirim (Sınıf Tasarımcısı) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- interfaces [Visual Studio], implementing
- interfaces [Visual Studio]
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c80ce802cd08a36ed299c0b24e7df729d6cce2d5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
    > Sınıf Görünümü açık değilse, sınıf görünümünden açmak **Görünüm** menüsü.
  
3.  Arabirim düğümü diyagramı sınıfı şekle sürükleyin.  
  
     Lolipop sınıfa bağlı görünür ve arabirim adı ile bir etiket devralma ilişkisi tanımlar. Visual Studio için tüm arabirim üyelerini saplamalar oluşturur; Bu noktada, arabirim uygulanır.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturma](how-to-create-types.md)   
[Nasıl yapılır: Varolan türleri görüntüleme](how-to-view-existing-types.md)   
[Nasıl yapılır: türler arasında devralmayı oluşturma](how-to-create-inheritance-between-types.md)   
[Sınıfları ve Türleri Yeniden Düzenleme](refactoring-classes-and-types.md)