---
title: "Nasıl yapılır: devralma türleri (Sınıf Tasarımcısı) arasındaki oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.classdesigner.inheritanceline
helpviewer_keywords:
- inheritance, relationship defining
- relationships, defining inheritance
ms.assetid: 3786a21c-8022-4bf5-9d13-740fd354e93c
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f24215230e4353c3e019f963706896505c2a32ff
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/15/2017
---
# <a name="how-to-create-inheritance-between-types-class-designer"></a>Nasıl yapılır: devralma türleri (Sınıf Tasarımcısı) arasındaki oluştur
Sınıf Tasarımcısı kullanarak bir sınıf diyagramında iki tür arasında bir devralma ilişkisi oluşturmak için türetilmiş bir tür ile temel türü veya türleri bağlayın. İki sınıf arasında bir sınıf ve bir arabirim arasında veya iki arabirimler arasında bir devralma ilişkisi olabilir.  
  
### <a name="to-create-an-inheritance-between-types"></a>Türler arasında devralmayı oluşturmak için  
  
1.  Projenizden Çözüm Gezgini'nde, bir sınıf diyagramı (.cd) dosyasını açın.  
  
     Sınıf diyagramında yoksa, oluşturun. Bkz: [nasıl yapılır: projelere sınıf diyagramları ekleme](how-to-add-class-diagrams-to-projects.md).  
  
2.  İçinde **araç**altında **Sınıf Tasarımcısı**, tıklatın **devralma**.  
  
3.  Sınıf diyagramında başlayarak istediğiniz türler arasında bir devralma çizgi çizme:  
  
    -   Türetilmiş bir sınıf için temel sınıfı  
  
    -   Uygulayan bir sınıfa uygulanan arabirimi  
  
    -   Genişletme arabirime genişletilmiş arabirimi  
  
4.  İsteğe bağlı olarak, genel bir türden türetilmiş bir tür olduğunda Devralma Satırı'ı tıklatın. İçinde **özellikleri** penceresindeki ayarlayın **tür bağımsız değişkenleri** genel türü için istediğiniz türüyle eşleşecek şekilde özelliği.  
  
    > [!NOTE]
    >  Bir üst soyut sınıf soyut en az bir üye içeriyorsa, tüm soyut üyelerini Özet olmayan türetilen sınıflar uygulanır.  
    >   
    >  Mevcut genel türleri görselleştirebilirsiniz rağmen yeni genel türler oluşturulamıyor. Ayrıca, varolan genel türleri için tür parametreleri değiştiremezsiniz.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Devralma](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)   
[Devralma temelleri](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
[Nasıl yapılır: türler arasında devralmayı görüntüleme](how-to-view-inheritance-between-types.md)   
[Sınıf Tasarımcısında Visual C++ Sınıfları](visual-cpp-classes.md)