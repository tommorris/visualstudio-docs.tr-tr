---
title: "Nasıl yapılır: Office Çok Dilde Kullanıcı arabirimini hedefleme | Microsoft Docs"
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
- globalization [Office development in Visual Studio], user interface targeting
- MUI [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], localization
- Multilingual User Interface [Office development in Visual Studio]
- localization [Office development in Visual Studio], user interface targeting
- Office applications [Office development in Visual Studio], globalization
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 39ee8b6bdcb4ad647164ec555cfa37ee9cfe8f50
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-target-the-office-multilingual-user-interface"></a>Nasıl Yapılır. Office Çok Dilde Kullanıcı Arabirimini Hedefleme
  Çok Dilde Kullanıcı Arabirimi (MUI) son kullanıcı kullanıcı arabirimi (UI) dilini değiştirme olanağı sağlayan bir Microsoft Office özelliğidir. Örneğin, İngilizce bir kullanıcı Arabirimi ile çalışan bir son kullanıcı için İspanyolca dil UI değiştirebilirsiniz.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Uygulamanız birden çok dil Office sürümlerini kullanan kişiler tarafından kullanılacaksa, otomatik olarak (kullanıcı yüklü doğru kaynakları varsa) kullanıcının bilgisayarında Office tarafından kullanılan dil ile eşleşen UI dizelerinizi dilini değiştirmek için kod ekleyebilirsiniz.  
  
### <a name="to-check-the-current-office-ui-setting"></a>Geçerli Office UI ayarını denetlemek için  
  
1.  Kullanım <xref:System.Threading.Thread.CurrentUICulture%2A> geçerli iş parçacığının özelliği. Şu anda kullanıcının bilgisayar üzerinde çalışan Office sürümü tarafından kullanılan dil ile eşleşen UI dizelerinizi dilinin ayarlayın.  
  
     [!code-vb[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#10)]
     [!code-csharp[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#10)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: birincil birlikte çalışma derlemeleriyle Office uygulamalarını](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Office Çözümlerinde Geç Bağlama](../vsto/late-binding-in-office-solutions.md)  
  
  