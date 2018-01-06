---
title: "Örnek Excel uzantısı: ExtensionPackage sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e45410a-1819-4d54-ac21-7280152f7e3a
caps.latest.revision: "9"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: e216205ef2e7dfb22524ca3fb83a40958d31fd6d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sample-excel-extension-extensionpackage-class"></a>Örnek Excel Uzantısı: ExtensionPackage Sınıfı
Bu sınıfını genişleten <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> sınıfı ve sınayan kodlanmış UI testi için giriş noktası sağlayan bir [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] çalışma sayfası.  
  
## <a name="assembly-attribute"></a>Derleme özniteliği  
 Dosyanın derleme bir UI testi uzantısı olarak tanımlayan bir derleme özniteliği ile başlar.  
  
```  
[assembly: Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage(  
    "ExcelExtensionPackage",  
    typeof(  
     Microsoft.VisualStudio.Test.Sample.UI.ExtensionPackage))]  
```  
  
 Bu öznitelik, temel sınıfın adını, paket sınıfı adı ve özel uzantı paketini sınıfı için tam sınıf adını bildirir.  
  
## <a name="simple-properties"></a>Basit Özellikler  
 Bu sınıf tanımlamak ve uzantı ve derlemeleri açıklamak için kodlanmış UI test çerçevesi tarafından kullanılan değerleri sağlayan özellikleri vardır. Kod açıklamaları daha fazla bilgi için bkz.  
  
## <a name="getservice-method"></a>GetService yöntemi  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A> Yöntemi her nesne için temel sınıfı tarafından tanımlandığı gibi teknoloji Yöneticisi, özellik sağlayıcısı ve eylem filtresi erişmek için kodlanmış UI test çerçevesi tarafından kullanılan tek giriş noktasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>   
 [Kodlanmış Kullanıcı Arabirimi Testlerini ve Eylem Kayıtlarını Microsoft Excel'i Desteklemek için Genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
