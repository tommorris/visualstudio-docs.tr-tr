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
ms.openlocfilehash: f77a079a32cadb4a994e8874df2e9ae97dd93bf0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-implement-an-interface-class-designer"></a>Nasıl Yapılır: Arabirimi Uygulama (Sınıf Tasarımcısı)
Sınıf Tasarımcısı'nda kod için arabirim yöntemleri sağlayan bir sınıf bağlanarak arabirim sınıf diyagramında uygulayabilirsiniz. Sınıf Tasarımcısı bir arabirim uygulaması oluşturur ve bir devralma ilişkisi arabirimi ve sınıfı arasındaki ilişkiyi gösterir. Arabirim arabirimi ve sınıf arasında bir devralma satırı çizim veya sınıf görünümünden arabirimi sürükleyerek uygulayabilirsiniz.  
  
> [!TIP]
>  Diğer türleri oluşturmak aynı şekilde arabirimleri oluşturabilirsiniz. Arabirim var, ancak sınıf diyagramında görünmez, ardından ilk görüntüleyin. Daha fazla bilgi için bkz: [nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturma](../ide/how-to-create-types-by-using-class-designer.md) ve [nasıl yapılır: görünüm varolan türleri (Sınıf Tasarımcısı)](../ide/how-to-view-existing-types-class-designer.md).  
  
### <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>Devralma Satırı çizerek bir arabirim uygulamak için  
  
1.  Sınıf diyagramında arabirimi ve arabirimini uygulayan sınıf görüntüler.  
  
2.  Devralma Satırı sınıf ve arabirim çizin.  
  
     Lolipop sınıfa bağlı görünür ve arabirim adı ile bir etiket devralma ilişkisi tanımlar. Visual Studio için tüm arabirim üyelerini saplamalar oluşturur.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: oluşturmak devralma arasında türleri (Sınıf Tasarımcısı)](../ide/how-to-create-inheritance-between-types-class-designer.md).  
  
### <a name="to-implement-an-interface-from-the-class-view-window"></a>Sınıf Görünümü penceresinden bir arabirim uygulamak için  
  
1.  Sınıf diyagramında arabirimi uygulamak istediğiniz sınıfı görüntüler.  
  
2.  Sınıf Görünümü açın ve arabirim bulun.  
  
    > [!TIP]
    >  Sınıf Görünümü açık değilse, sınıf görünümünden açmak **Görünüm** menüsü. Sınıf Görünümü hakkında daha fazla bilgi için bkz: [görüntüleme sınıflar ve Their üyeleri](http://msdn.microsoft.com/en-us/71e9e8f3-261a-4e0c-87bf-5ec48b8bf333).  
  
3.  Arabirim düğümü diyagramı sınıfı şekle sürükleyin.  
  
     Lolipop sınıfa bağlı görünür ve arabirim adı ile bir etiket devralma ilişkisi tanımlar. Visual Studio için tüm arabirim üyelerini saplamalar oluşturur; Bu noktada, arabirim uygulanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturma](../ide/how-to-create-types-by-using-class-designer.md)   
 [Nasıl yapılır: Varolan türleri (Sınıf Tasarımcısı) görüntüleme](../ide/how-to-view-existing-types-class-designer.md)   
 [Nasıl yapılır: devralma türleri (Sınıf Tasarımcısı) arasındaki oluştur](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [Yeniden düzenleme sınıfları ve türleri (Sınıf Tasarımcısı)](../ide/refactoring-classes-and-types-class-designer.md)