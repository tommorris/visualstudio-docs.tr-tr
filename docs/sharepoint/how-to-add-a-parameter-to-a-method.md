---
title: "Nasıl yapılır: bir yönteme parametre ekleme | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], adding a method to a parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], parameter
- BDC [SharePoint development in Visual Studio], adding a method to a parameter
- BDC [SharePoint development in Visual Studio], parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], method parameters
- BDC [SharePoint development in Visual Studio], method parameters
ms.assetid: c5b6fd32-bf85-4b2a-a01e-f9199f0fb26e
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: f6810d69628c66a011123250b8e0efb8622f0be7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-parameter-to-a-method"></a>Nasıl yapılır: Bir Yönteme Parametre Ekleme
  Bir parametre yöntemin içine bilgi geçirmek için veya bir yöntemden bilgi almak için kullanın. Tüm yöntemleri en az bir parametre olması gerekir. Oluşturmak istediğiniz yöntemi türünü desteklemek için bir parametre tasarlamak hakkında daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
 Bir parametre için bir yöntem eklediğinizde, Visual Studio ekler `<Parameter>` projenizdeki model dosyası XML öğesi. Dosyanın öznitelikleri hakkında daha fazla bilgi için bir `<Parameter>` öğesi, bkz: [parametresi](http://go.microsoft.com/fwlink/?LinkId=169284).  
  
### <a name="to-add-a-parameter-to-a-method"></a>Bir yönteme parametre eklemek için  
  
1.  Bir varlık için bir yöntem ekleyin.  
  
2.  Menü çubuğunda seçin **Görünüm**, **diğer pencereler**, **BDC yöntem ayrıntıları**.  
  
     **BDC yöntem ayrıntıları** penceresi açılır. Daha fazla bilgi için bkz: [BDC modeli tasarım araçlarına genel bakış](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  İçinde **BDC yöntem ayrıntıları** penceresinde yöntemi düğümünü genişletin ve ardından genişletin **parametreleri** düğümü.  
  
4.  İçinde **bir parametre eklemek** listesinde, seçin **oluşturma parametresi**.  
  
     Altında yeni bir parametre görünür **parametreleri** düğümü.  
  
5.  Menü çubuğunda seçin **Görünüm**, **Özellikler penceresini**.  
  
6.  İçinde **özellikleri** penceresindeki ayarlayın **adı** mantıklı herhangi bir ad özelliği. Örneğin, müşteriler yöntemi verecekse yöntemi adlandırabilirsiniz **GetCustomers**.  
  
7.  İçinde **BDC yöntem ayrıntıları** penceresinde, parametre yönü için görünür listesini açın ve ardından **içinde**, **InOut**, **çıkışı**, veya **iade**.  
  
     Oluşturmakta olduğunuz türü yöntemi için seçmek için hangi yöne hakkında daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
8.  Parametrenin tür tanımlayıcısını değiştirin. Daha fazla bilgi için bkz: [nasıl yapılır: bir parametrenin tür tanımlayıcısını tanımlama](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BDC modeli tasarım araçlarına genel bakış](../sharepoint/bdc-model-design-tools-overview.md)   
 [Nasıl yapılır: bir modele bir varlık ekleme](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [Nasıl yapılır: bir parametrenin tür tanımlayıcısını tanımlama](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [Nasıl yapılır: yöntem örneği tanımlama](../sharepoint/how-to-define-a-method-instance.md)   
 [İş Verileri Bağlantı Modeli Tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  