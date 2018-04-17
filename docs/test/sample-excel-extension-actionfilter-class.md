---
title: 'Örnek Excel uzantısı: ActionFilter sınıfı | Microsoft Docs'
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 6f98afa819fceb4f8b8b34d5aa268f11f7b16993
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sample-excel-extension-actionfilter-class"></a>Örnek Excel Uzantısı: ActionFilter Sınıfı

Bu dahili sınıfını genişleten <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> sınıfı ve üzerinde test eylemleri için bir filtre temsil eden bir [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] öğesi.

## <a name="simple-properties"></a>Basit Özellikler

Bu salt okunur özellikler test eylem filtresinin kodlanmış UI test çerçevesi tarafından nasıl yürütülmesi gereken belirtin. Örneğin, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> özelliği, eylem filtresinin adını sağlar. Diğer özellikler get <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A> eylem filtresinin <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> bu test eylem filtresi tarafından filtrelenen test eylemler için ad. Başkalarının belirtmek kullanılıp kullanılmayacağını <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> ve ayrıca test eylem olup <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>.

## <a name="processrule-method"></a>ProcessRule yöntemi

Bu yöntem kodlanmış UI test çerçevesi tarafından çağrılır ve sağlanan karşı filtresini yürütür <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>. Fare bu geçersiz kılma kaldırır yığındaki bir sonraki eylem hücreye tuş vuruşları gönderdiğinde eylemi bir hücre seçin. Daha sonra döndürür `false`.

## <a name="private-methods"></a>Özel yöntemler

`IsLeftClick` Yöntemi, sağlanan eyleme ayarını fare temsil edip etmediğini belirler. `AreActionsOnSameExcelCell` Yöntemi, iki Eylemler aynı hücrenin Excel'de gerçekleştirildi sağlanan olup olmadığını belirler.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>
- [Kodlanmış Kullanıcı Arabirimi Testlerini ve Eylem Kayıtlarını Microsoft Excel'i Desteklemek için Genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
