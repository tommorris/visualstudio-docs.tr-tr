---
title: 'Nasıl yapılır: özellik bağımlılıkları ekleme ve kaldırma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- MICROSOFT.VISUALSTUDIO.SHAREPOINT.DESIGNERS.CUSTOMDEPENDENCYWINDOW
- VS.SHAREPOINTTOOLS.RAD.FEATUREDESIGNERDEPENDENCY
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, features
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: eeda1b63132de49785b2f2ba5743dbd683504a71
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-and-remove-feature-dependencies"></a>Nasıl yapılır: Özellik Bağımlılıkları Ekleme ve Kaldırma
  SharePoint özelliği işlev veya veri için diğer özellikleri bağlı. Bu durumlarda, bu diğer özellikleri, özellik için bağımlılıklar olarak işaretleyebilirsiniz. Bu şekilde, özellik etkinleştirilmeden önce bağımlı özellikleri etkinleştirilir SharePoint sunucusu sağlar.  
  
## <a name="adding-dependencies"></a>Bağımlılıkları ekleme  
 Bağımlılıklar olarak çözümünüzde diğer özellikleri ekleyebilirsiniz. Bu şekilde, gerekli özellikleri yüklü ve, özellik yüklenmeden önce etkinleştirilmiş olduğundan emin olabilirsiniz.  
  
#### <a name="to-add-a-dependency-on-a-feature-in-the-solution"></a>Bir bağımlılık çözümünün bir özelliği eklemek için  
  
1.  Özellik Tasarımcısı'nı açın, **özellik etkinleştirme bağımlılıkları** düğümünü ve ardından **Ekle** düğmesi.  
  
2.  İçinde **özelliğini etkinleştirme bağımlılıklar ekleme** iletişim kutusunda, seçin **bir bağımlılık özelliklerini çözümünde eklemek** seçenek düğmesi, bir bağımlılık olarak eklemek istediğiniz özelliğin başlığını seçin ve ardından seçin **Ekle** düğmesi.  
  
     Ctrl tuşunu seçerken birden çok başlığını seçerek birden fazla özellik ekleyebilirsiniz.  
  
## <a name="adding-custom-dependencies"></a>Özel bağımlılıkları ekleme  
 Bağımlılık olarak bir SharePoint sunucusu üzerine zaten dağıtılmış olan özellikleri ekleyebilirsiniz. Bu şekilde, SharePoint etkinleştirme işlemi, özellik yüklenmeden önce tüm bağımlı özellikler etkinleştirildiğinden emin olmak için denetler.  
  
#### <a name="to-add-a-dependency-by-the-feature-id"></a>Özellik kimliği ile bir bağımlılık eklemek için  
  
1.  Özellik Tasarımcısı'nı açın, **özellik etkinleştirme bağımlılıkları** düğümünü ve ardından **Ekle** düğmesi.  
  
2.  İçinde **özelliğini etkinleştirme bağımlılıklar ekleme** iletişim kutusunda, seçin **özel bir bağımlılık ekleme** seçenek düğmesi.  
  
3.  İçinde **özellik kimliği** metin kutusunda, bir etkinleştirme bağımlılık olarak işaretleyin ve ardından istediğiniz özellik için GUID girin **Ekle** düğmesi.  
  
## <a name="editing-custom-dependencies"></a>Özel bağımlılıkları düzenleme  
 Daha önce eklediğiniz özel bağımlılıkları düzenleyebilirsiniz. Ancak, yalnızca, çözüm can kaldırılır, bağımlı özellikler düzenlenemez.  
  
#### <a name="to-change-a-dependency-on-a-feature-in-the-solution"></a>Bir bağımlılığı çözümünün bir özelliği değiştirmek için  
  
1.  Özellik Tasarımcısı'nı açın ve ardından genişletin **özellik etkinleştirme bağımlılıkları** düğümü.  
  
2.  Düzenle ve ardından istediğiniz özelliğin adını seçin **Düzenle** düğmesi.  
  
3.  İçinde **Düzenle özel özelliğini etkinleştirme bağımlılık** iletişim kutusu, başlık, özellik kimliği veya açıklamayı değiştirmek ve ardından **gönderme** düğmesi.  
  
## <a name="removing-dependencies"></a>Bağımlılıklarını kaldırma  
  
#### <a name="to-remove-a-dependency-on-a-feature-in-the-solution"></a>Çözümde bir özelliği bir bağımlılığı kaldırmak için  
  
1.  Özellik Tasarımcısı'nda genişletin **özellik etkinleştirme bağımlılıkları** düğümü, kaldırın ve ardından istediğiniz özelliğin adını seçin **kaldırmak** düğmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint özellikleri oluşturma](../sharepoint/creating-sharepoint-features.md)   
 [Nasıl yapılır: bir SharePoint özelliğini özelleştirme](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [Nasıl yapılır: SharePoint Özelliklerine Öğe Ekleme ve Kaldırma](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
  
  