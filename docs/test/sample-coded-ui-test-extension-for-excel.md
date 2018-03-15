---
title: "Excel için kodlanmış UI testi uzantısı örneği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- coded UI tests, extensions for Excel
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: a446fbf087441be9e02c54314d05845ce759e47b
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="sample-coded-ui-test-extension-for-excel"></a>Excel için Kodlanmış UI Testi Uzantısı Örneği
Örnek uzantısı bileşeninin çalışan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kodlanmış UI testi işlemi ve biraz hiyerarşik `ExtensionPackage` temel sınıfı. `TechnologyManager`, `ActionFilter`, Ve `PropertyProvider` sınıfları sonraki düzeyi, en üst düzeydeki denetim öğeleri ile.

 ![Excel Test Uzantısı Mimarisi](../test/media/excel_extarch.png "Excel_ExtArch") Excel uzantısı mimarisi

## <a name="extension-points"></a>Uzantı noktaları
 Kodlanmış UI testi için etkinleştirmek için örnek uygulanan uzantı noktaları bu sınıfları temsil [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)].

### <a name="extensionpackage"></a>ExtensionPackage
 Devralınan <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> , bu sınıftır kodlanmış UI testi uzantısı için giriş noktası. Bu Özet sınıf uygulama framework iç erişimini özel kullanıcı Arabirimi test teknoloji Yöneticisi, UI test özellik sağlayıcısına ve UI test eylem filtresinin yeni UI testi için test etme kodlanmış kullanıcı Arabirimi sağlar. Daha fazla bilgi için bkz: [ExtensionPackage sınıfı](../test/sample-excel-extension-extensionpackage-class.md).

### <a name="technologymanager"></a>TechnologyManager
 Devralınan <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager> sınıfı, bu sınıfın sağladığı bir teknoloji Yöneticisi test kaydetme ve kayıttan yürütme için. Daha fazla bilgi için bkz: [TechnologyManager sınıfı](../test/sample-excel-extension-technologymanager-class.md).

### <a name="actionfilter"></a>ActionFilter
 Devralınan <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> sınıfı, bu sınıfın sağladığı bir taban sınıf bir tek test sonucu benzer test eylem sonuçlarını toplamak için. Daha fazla bilgi için bkz: [ActionFilter sınıfı](../test/sample-excel-extension-actionfilter-class.md).

### <a name="technology-elements"></a>Teknoloji öğeleri
 Bir taban sınıf devralınan <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> sınıfı kaydedilen ve çalınma UI testleri teknoloji öğeleri için temel sağlar. Daha fazla bilgi için bkz: [öğe sınıfları](../test/sample-excel-extension-element-classes.md).

### <a name="propertyprovider"></a>PropertyProvider
 Devralınan <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> sınıfı, bu sınıfın sağladığı bir taban sınıf test kaydetme ve kayıttan yürütme için kullanıcı Arabirimi öğelerinin özelliklerini desteklemek için. Daha fazla bilgi için bkz: [PropertyProvider sınıfı](../test/sample-excel-extension-propertyprovider-class.md).

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [ExtensionPackage sınıfı](../test/sample-excel-extension-extensionpackage-class.md)
- [TechnologyManager Sınıfı](../test/sample-excel-extension-technologymanager-class.md)
- [ActionFilter sınıfı](../test/sample-excel-extension-actionfilter-class.md)
- [Öğe sınıfları](../test/sample-excel-extension-element-classes.md)
- [PropertyProvider Sınıfı](../test/sample-excel-extension-propertyprovider-class.md)
