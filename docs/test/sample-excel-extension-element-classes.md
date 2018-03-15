---
title: "Örnek Excel Eklentisi: Öğe sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: bd97702aec611a3818d478513a07ce03895729f3
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="sample-excel-extension-element-classes"></a>Örnek Excel Eklentisi: Öğe Sınıfları
Türetilmiş sınıflar uzantısını kullanır <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> ve çalışma sayfası ve hücre denetimi temsil [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)].

 Bu uzantı için temel öğesidir `ExcelElement`. `ExcelWorksheetElement` Sınıfı ve `ExcelCellElement` sınıfı bu öğeden devralır

## <a name="element-and-elementinformation-classes"></a>Öğe ve ElementInformation sınıfları
 `Element` Excel uzantısı için tüm kullanıcı arabirimi öğeleri için temel sınıftır ve öğesinden devralınan <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> sınıfı. `ElementInformation` Örnek bilgileri sınıflarda öğesi için temel sınıfı olan ve hiç üye içermiyor.

#### <a name="simple-properties-and-methods"></a>Basit özellikler ve yöntemler
 Bu üyeler dönüş değeri gibi basit değerleri `Name` özelliği veya değerinin `ClassName` özelliği ve kod NET ve kolay okunur. Bazı değerler kullanılarak döndürülür `Utility` daha sonra açıklanan sınıfı. Başkalarının dönmek `null` Bu örnek uzantıyla ilgili olmadıklarından. İki üye diğerlerinden daha ilginç: <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A> özelliği ve <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.CacheProperties%2A> yöntemi.

#### <a name="queryid-property"></a>QueryId özelliği
 Bu özellik denetimi kayıttan yürütme sırasında benzersizce özelliği ad-değer çiftleri yapılan bir koşul döndürür. Her türetilmiş denetim sınıfı için geliştirici döndürmek için bu özelliği geçersiz kılmanız gerekir bir <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IQueryElement> framework denetimi kullanıcı Arabiriminde bulmak için kullanabileceğiniz nesne.

#### <a name="cacheproperties-method"></a>CacheProperties Method
 Bu yöntem, bir anlık görüntü önemli özellikleri kaydetmek için öğeye söylemek için kayıt işlemi sırasında test çerçevesi tarafından çağrılır. Gerçek UI denetimi artık ekranda olsa bile bu özellikleri kullanılabilir durumda tutar.

## <a name="worksheetelement-and-worksheetinformation-classes"></a>WorksheetElement ve WorksheetInformation sınıfları
 `WorksheetElement` Sınıfı bir Excel çalışma sayfası test Framework temsil eder ve devraldığı `Element` temel sınıfı. Excel çalışma sayfası nesnesi hakkında belirli bilgiler sağlamak için üç özellik kılınır: <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.ClassName%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.ControlTypeName%2A>, ve <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.Name%2A>.

 <xref:System.Runtime.InteropServices.ComVisibleAttribute> COM görünür yapmak için bu sınıf ayrıca uygulanır

 `WorksheetInformation` Sınıfı, bir Excel çalışma hakkında bilgi gösterir. Tek bir üyeye sahip `SheetName` Bu örnek için yeterliyse özelliği.

## <a name="cellelement-and-cellinformation-classes"></a>CellElement ve CellInformation sınıfları
 `CellElement` Sınıfı bir Excel hücresini temsil eder ve devraldığı `Element` temel sınıfı. Geçersiz kılınan tek üye <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A> döndürür özelliği bir <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IQueryElement> kullanan `RowIndex` ve `ColumnIndex` hücre tanımlamak için özellikleri.

## <a name="utilities-and-excelutilities-classes"></a>Yardımcı programlar ve ExcelUtilities sınıfları
 İç `ExcelUtilities` sınıfı teknoloji adı ve sağlanan bir pencere tanıtıcının Excel çalışma temsil edip etmediğini belirleyen bir yöntem gibi bazı sabit değerler sağlar.

 `Utilities` Sınıfı, kullanıcı Arabirimi hakkında bilgi çeşitli dönüş yardımcı yöntemler vardır. Dış sistem DLL'leri doğrudan çağrılar gibi bazı yöntemler kullandığınız **USER32. DLL** ve **OLEACC. DLL**, kullanıcı Arabiriminden pencere işleyicileri almak için**.**

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IQueryElement>
- [Kodlanmış Kullanıcı Arabirimi Testlerini ve Eylem Kayıtlarını Microsoft Excel'i Desteklemek için Genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
