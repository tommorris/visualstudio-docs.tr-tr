---
title: "Örnek Excel uzantısı: ActionFilter sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c69fe3c7-f797-4e90-b21c-f2cc4dddf152
caps.latest.revision: "11"
ms.author: douge
manager: douge
ms.openlocfilehash: 346cb9faddf2bd155c91d9fc72176020ba43197b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="sample-excel-extension-actionfilter-class"></a>Örnek Excel Uzantısı: ActionFilter Sınıfı
Bu dahili sınıfını genişleten <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> sınıfı ve üzerinde test eylemleri için bir filtre temsil eden bir [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] öğesi.  
  
## <a name="simple-properties"></a>Basit Özellikler  
 Bu salt okunur özellikler bu test eylem filtresinin nasıl kodlanmış UI test çerçevesi tarafından yürütülecek belirtmek Geliştirici etkinleştirin. Örneğin, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> özelliği, eylem filtresinin adını sağlar. Diğer özellikler get <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A> eylem filtresinin <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> bu test eylem filtresi tarafından filtrelenen test eylemler için ad. Başkalarının belirtmek kullanılıp kullanılmayacağını <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> ve ayrıca test eylem olup <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>.  
  
## <a name="processrule-method"></a>ProcessRule yöntemi  
 Bu yöntem kodlanmış UI test çerçevesi tarafından çağrılır ve sağlanan karşı filtresini yürütür <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>. Fare bu geçersiz kılma kaldırır yığındaki bir sonraki eylem hücreye tuş vuruşları gönderdiğinde eylemi bir hücre seçin. Daha sonra döndürür `false`.  
  
## <a name="private-methods"></a>Özel yöntemler  
 `IsLeftClick` Yöntemi, sağlanan eyleme ayarını fare temsil edip etmediğini belirler. `AreActionsOnSameExcelCell` Yöntemi, iki Eylemler aynı hücrenin Excel'de gerçekleştirildi sağlanan olup olmadığını belirler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>   
 [Kodlanmış UI testleri ve Eylem kayıtlarını Microsoft Excel'i desteklemek için genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
