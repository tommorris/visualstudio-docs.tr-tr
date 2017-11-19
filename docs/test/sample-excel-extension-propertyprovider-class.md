---
title: "Örnek Excel uzantısı: PropertyProvider Sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 075d9b8d-8658-4fca-8711-08304dbac1c5
caps.latest.revision: "9"
ms.author: douge
manager: douge
ms.openlocfilehash: 28cc3774c48eabc240f2f51b9b40f23faba74377
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="sample-excel-extension-propertyprovider-class"></a>Örnek Excel Uzantısı: PropertyProvider Sınıfı
Bu dahili sınıfını genişleten <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> sınıf ve özellik hizmetleri sağlar. [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] kaydetmek ve kullanıcı arabirimi (UI) testleri oynatmak için öğeleri.  
  
## <a name="getcontrolsupportlevel-method"></a>GetControlSupportLevel yöntemi  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetControlSupportLevel%2A> Yöntemi için sağlanan denetim özellik sağlayıcısı sunan destek düzeyini gösteren bir sayı döndürür. Döndürülen değer arttıkça daha fazla özellik sağlayıcısı denetimi destekleyebilir. Bu durumda, yöntem denetler <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.TechnologyName%2A> sağlanan denetiminin özelliği. Değer "Excel" ise ve <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.ControlTypeName%2A> olduğu gösteren bir `CellElement`, yöntemi en yüksek değeri döndürür; Aksi takdirde hiçbir destek sağlanmadığını gösteren sıfır döndürür.  
  
## <a name="getpropertynames-method"></a>GetPropertyNames yöntemi  
 Özellik adları ve özellik tanımlayıcıları bir Excel hücre denetiminin desteklenen özellikleri için bir sözlüğü döndürür.  
  
## <a name="getpropertydescriptor-method"></a>GetPropertyDescriptor yöntemi  
 Bu yöntem, önceden tanımlanmış özellik tanımlayıcısı için belirtilen özellik adı almak için test çerçevesi tarafından çağrılır.  
  
## <a name="getpropertyvalue-and-setpropertyvalue-methods"></a>GetPropertyValue ve SetPropertyValue Yöntemleri  
 `GetPropertyValue` Yöntemi kullanan `Communicator` Excel'den özellik değeri döndürmek için bu uzantının sınıfı. `SetPropertyValue` Yöntemi kullanan <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard> sınıfı ve `Communicator` özellik değerini ayarlamak için bileşen. Bu yöntemler test çerçevesi tarafından çağrılır.  
  
## <a name="code-generation-customization-methods"></a>Kod üretimi özelleştirme yöntemleri  
 Bu uzantı için bu yöntem uygulanmadı. Bu nedenle, ya da döndürmeleri `null` veya <xref:System.NotImplementedException>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard>   
 [Kodlanmış UI testleri ve Eylem kayıtlarını Microsoft Excel'i desteklemek için genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
