---
title: "Office belgelerinde parola koruması | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- passwords [Office development in Visual Studio], document protections
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
ms.assetid: 9cee99c8-73c6-4f89-9d5e-7912c876ff96
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: f24c0493a66651a5d95925fd6777ba3e1cdd1658
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
  
  