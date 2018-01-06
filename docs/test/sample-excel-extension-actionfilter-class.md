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
ms.workload: multiple
ms.openlocfilehash: 6a76f89db120f8655d63a064cb3d851abb9eac64
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
 [Kodlanmış Kullanıcı Arabirimi Testlerini ve Eylem Kayıtlarını Microsoft Excel'i Desteklemek için Genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
