---
title: Office belgelerinde parola koruması | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- passwords [Office development in Visual Studio], document protections
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5d85f1dc0aa54da22b02259aea372f2ad6dd42ac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="password-protection-on-office-documents"></a>Office Belgelerinde Parola Koruması
  Böylece bunlar parolayı bilmeyen biri tarafından açılamıyor bir parola, Microsoft Office Word belgelerine ve Microsoft Office Excel çalışma kitaplarına ayarlamak mümkündür. Bu seçenek adlandırılır **açık parola**.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Belge düzeyi projelerine mevcut belgeler ve olan çalışma kitaplarını kullanarak oluşturabileceğiniz **açık parola** etkin. Visual Studio'da sahip Word ve Excel belgeleri için farklı bir davranıştır **açık parola** etkin.  
  
 Etkinleştirme hakkında bilgi için **açık parola**, Word veya Excel Yardımı'na bakın.  
  
## <a name="behavior-of-excel-and-word"></a>Excel ve Word'ün davranışı  
 Visual Studio'da sahip her bir Excel çalışma kitabı açtığınızda **açık parola** etkinse, Excel, parolasını ister. Çözümünüzü yapılandırdığınızda belge derleme sırasında açıldığından, parolasını yeniden istenir.  
  
 İlk kez açtığınızda bir Word belgesi Visual Studio'da sahip **açık parola** etkinse, Word parolasını ister. Parolanızı başarıyla girdikten sonra **açık parola** belgeden kaldırılır ve belgeyi açmayı parola artık gerektirecektir. Belgenin çözümünüzde istiyorsanız, önce bir parola gerektirecek şekilde açılabilir, etkinleştirmelisiniz **açık parola** son yapılandırmanızdan sonra ve çözüm dağıtmadan önce.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge düzeyi çözümlerde belge koruması](../vsto/document-protection-in-document-level-solutions.md)   
 [Bilgi Hakları Yönetimine ve yönetilen kod uzantılarına genel bakış](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Nasıl yapılır: kodun kısıtlı izinle belgelerin arkasında çalışmasına izin verme](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Office Çözümleri Tasarlama ve Oluşturma](../vsto/designing-and-creating-office-solutions.md)  
  
  