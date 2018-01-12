---
title: "Nasıl yapılır: eklenti kullanıcı arayüzü hatalarını gösterme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], user interface errors
- errors [Office development in Visual Studio], user interface errors
- user interfaces [Office development in Visual Studio], errors
- application-level add-ins [Office development in Visual Studio], user interface errors
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4ce5204855cd6ebe468d652b8420cddc7fd19a1a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-show-add-in-user-interface-errors"></a>Nasıl Yapılır: Eklenti Kullanıcı Arayüzü Hatalarını Gösterme
  Bir VSTO eklenti Microsoft Office kullanıcı arabirimi (UI) ve başarısız olursa, değiştirmeyi denerse, varsayılan olarak, hata iletisi görüntülenir. Ancak, Microsoft Office uygulamaları için kullanıcı Arabirimi ile ilgili hataları için iletileri görüntülemek için yapılandırabilirsiniz. Bu iletiler neden özel bir Şerit görünmez, belirlemenize yardımcı olması için kullanabileceğiniz veya neden bir Şerit görünür ancak denetim yok görünüyor.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-show-vsto-add-in-user-interface-errors"></a>VSTO eklenti kullanıcı arayüzü hatalarını göstermek için  
  
1.  Uygulamayı başlatın.  
  
2.  Tıklatın **dosya** sekmesi.  
  
3.  Tıklatın **seçenekleri**.  
  
4.  Kategoriler bölmesinde **Gelişmiş**.  
  
5.  Ayrıntılar bölmesinde seçin **Göster VSTO eklenti kullanıcı arayüzü hatalarını**ve ardından **Tamam**.  
  
    > [!NOTE]  
    >  Outlook için **Göster VSTO eklenti kullanıcı arayüzü hatalarını** onay kutusunu bulunduğu **Geliştirici** ayrıntılar bölmesindeki bölümü. Diğer uygulamalar için onay kutusunu bulunan **genel** ayrıntılar bölmesindeki bölümü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Eylemler Bölmesine Genel Bakış](../vsto/actions-pane-overview.md)  
  
  