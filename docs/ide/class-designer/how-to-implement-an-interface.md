---
title: 'Nasıl Yapılır: Arabirimi Uygulama (Sınıf Tasarımcısı)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
ms.openlocfilehash: 5ccfde67a46ac1ae1b74a031a9ec030942d12b3d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-implement-an-interface-class-designer"></a>Nasıl yapılır: bir arabirim (Sınıf Tasarımcısı)

İçinde **Sınıf Tasarımcısı**, arabirim yöntemleri için kod sağlayan bir sınıf bağlanarak sınıf diyagramında bir arabirimi uygulayabilirsiniz. **Sınıf Tasarımcısı** bir arabirim uygulaması oluşturur ve bir devralma ilişkisi arabirimi ve sınıfı arasındaki ilişkiyi gösterir. Arabirim arabirimi ve sınıf arasında bir devralma satırı çizim veya sınıf görünümünden arabirimi sürükleyerek uygulayabilirsiniz.

> [!TIP]
> Diğer türleri oluşturmak aynı şekilde arabirimleri oluşturabilirsiniz. Arabirim var, ancak sınıf diyagramında görünmez, ardından ilk görüntüleyin. Daha fazla bilgi için bkz: [nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturma](how-to-create-types.md) ve [nasıl yapılır: Varolan türleri görüntüleme](how-to-view-existing-types.md).

## <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>Devralma Satırı çizerek bir arabirim uygulamak için

1.  Sınıf diyagramında arabirimi ve arabirimini uygulayan sınıf görüntüler.

2.  Devralma Satırı sınıf ve arabirim çizin.

     Lolipop sınıfa bağlı görünür ve arabirim adı ile bir etiket devralma ilişkisi tanımlar. Visual Studio için tüm arabirim üyelerini saplamalar oluşturur.

 Daha fazla bilgi için bkz: [nasıl yapılır: türler arasında devralmayı oluşturma](how-to-create-inheritance-between-types.md).

## <a name="to-implement-an-interface-from-the-class-view-window"></a>Sınıf Görünümü penceresinden bir arabirim uygulamak için

1.  Sınıf diyagramında arabirimi uygulamak istediğiniz sınıfı görüntüler.

2.  Açık **sınıf görünümü** ve arabirim bulun.

    > [!TIP]
    > Varsa **sınıf görünümü** açık, açık değil **sınıf görünümü** gelen **Görünüm** menüsü veya tuşuna **Ctrl**+**Shift** + **C**.

3.  Arabirim düğümü diyagramı sınıfı şekle sürükleyin.

     Lolipop sınıfa bağlı görünür ve arabirim adı ile bir etiket devralma ilişkisi tanımlar. Visual Studio için tüm arabirim üyelerini saplamalar oluşturur; Bu noktada, arabirim uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: Sınıf Tasarımcısı Kullanarak Tür Oluşturma](how-to-create-types.md)
- [Nasıl yapılır: Varolan türleri görüntüleme](how-to-view-existing-types.md)
- [Nasıl yapılır: türler arasında devralmayı oluşturma](how-to-create-inheritance-between-types.md)
- [Sınıfları ve Türleri Yeniden Düzenleme](refactoring-classes-and-types.md)