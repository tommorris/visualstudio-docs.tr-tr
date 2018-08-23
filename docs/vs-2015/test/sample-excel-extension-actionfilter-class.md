---
title: 'Örnek Excel uzantısı: ActionFilter sınıfı | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c69fe3c7-f797-4e90-b21c-f2cc4dddf152
caps.latest.revision: 13
ms.author: gewarren
manager: douge
ms.openlocfilehash: 5e6aff4a57dfb84760ceb4513e06d063c01a5af0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690975"
---
# <a name="sample-excel-extension-actionfilter-class"></a>Örnek Excel Uzantısı: ActionFilter Sınıfı
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [örnek Excel uzantısı: ActionFilter sınıfı](https://docs.microsoft.com/visualstudio/test/sample-excel-extension-actionfilter-class).  
  
Bu iç sınıfını genişleten <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> sınıfı ve test işlemleri için bir filtre üzerinde temsil eder bir [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] öğesi.  
  
## <a name="simple-properties"></a>Basit Özellikler  
 Bu salt okunur özellikler geliştirici bu test eylem filtresinin nasıl kodlanmış UI test çerçevesi tarafından yürütülecek belirtmek etkinleştirin. Örneğin, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> özelliği eylem filtresinin adını sağlar. Diğer özellikler get <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A> eylem filtresinin <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> bu test eylem filtresi tarafından filtrelenen test eylemlerini adı. Diğerleri belirtmek kullanılıp kullanılmayacağını <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> ve ayrıca test eylemi olup <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>.  
  
## <a name="processrule-method"></a>ProcessRule yöntemi  
 Bu yöntem kodlanmış UI test çerçevesi tarafından çağrılır ve sağlanan karşı filtresini yürütür <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>. Fare bu geçersiz kılma kaldırır sonraki eylem yığınında hücreye tuş vuruşları gönderir eylemi bir hücreyi seçin. Ardından döndürür `false`.  
  
## <a name="private-methods"></a>Özel yöntemler  
 `IsLeftClick` Yöntemi, belirtilen eylemi bir sol tıklatma fare temsil edip etmediğini belirler. `AreActionsOnSameExcelCell` Yöntemi iki Eylemler aynı hücreyi Excel'de yürütülen sağlanıp sağlanmadığını belirler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>   
 [Kodlanmış Kullanıcı Arabirimi Testlerini ve Eylem Kayıtlarını Microsoft Excel'i Desteklemek için Genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)



