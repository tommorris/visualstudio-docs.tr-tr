---
title: "Örnek Excel için kodlanmış UI testi eklentisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: coded UI tests, Excel Add-in sample
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: d6033b10ec7b8be4e44ad00c6f550d7237806234
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="sample-excel-add-in-for-coded-ui-testing"></a>Kodlanmış UI Testi için Excel Eklenti Örneği
Bu örnek eklenti [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] özellikle kaydedilmiş ve Visual Studio kuruluş içinde çalıştırılan kodlanmış UI testleri Excel, çalışma sayfaları destekleyecek şekilde tasarlanmıştır. Eklenti Office için Visual Studio Araçları kullanılarak oluşturulur.  
  
 Bir Excel eklentisi oluşturma hakkında daha fazla bilgi için bkz: [izlenecek yol: Excel için oluşturma bilgisayarınızı ilk VSTO eklentisi](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f) veya MSDN "Excel eklentisi için" araması yapın.  
  
 Excel eklentisi Excel için kodlanmış UI testi uzantısı belgelerinin birincil konu olmamasına karşın, birkaç açıklama yararlı olabilir.  
  
 Bu eklenti, önemli bölümleri:  
  
-   `ThisAddIn`Sınıf - arasında .NET uzaktan iletişim kanalı yönetir `ExcelUICommunicator` ve [örnek kodlanmış UI testi uzantısı Excel için](../test/sample-coded-ui-test-extension-for-excel.md).  
  
-   `ExcelCodedUIAddinHelper_TemporaryKey.pfx`-Eklenti test etme bir güvenlik sertifikası.  
  
-   `ExcelUICommunicator`Bu sınıf sınıfı - uygulayan `IExcelUICommunication` arabirimi.  
  
## <a name="thisaddin-class"></a>ThisAddIn sınıfı  
 Bu sınıf çoğu Office için Visual Studio Araçları tarafından oluşturulan gerçekten `ThisAddIn.Designer.cs` dosya Excel Eklentisi projenizi oluşturduğunuzda.  
  
 Uygulamanız gereken olay işleyicileri üyeleridir: `ThisAddIn_Startup()` ve `ThisAddIn_Shutdown()`. Başlatmak veya tarafından kullanılan .NET uzaktan iletişim kanalı kapatmak için kullanım amaçları olduğu `ExcelUICommunicator`.  
  
## <a name="excelcodeduiaddinhelpertemporarykeypfx"></a>ExcelCodedUIAddinHelper_TemporaryKey.pfx  
 Bu dosya, Office için Visual Studio Araçları tarafından oluşturulan ve eklenti ve uzantı testi için Excel işleminde çalışır eklenti derlemesi izin veren bir geçici güvenlik sertifikası içerir. Bu sertifikayı silmeniz gerekir ve ya da yeni bir tane oluşturun **imzalama** Proje sekmesinde **özellikleri** penceresinde veya kendi test sertifika eklemek.  
  
## <a name="exceluicommunicator-class"></a>ExcelUICommunicator sınıfı  
 Bu sınıf uygulayan `IExcelUITestCommunication` arabirim ve istenen UI bilgisini Excel nesne modeli alır. Daha fazla bilgi için bkz: [Excel Communicator arabirimi örnekleme](../test/sample-excel-communicator-interface.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodlanmış UI testleri ve Eylem kayıtlarını Microsoft Excel'i desteklemek için genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)   
 [İzlenecek yol: Excel için ilk VSTO eklentinizi oluşturma](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)   
 [Office ve SharePoint geliştirme](/office-dev/office-dev/office-and-sharepoint-development-in-visual-studio)
