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
ms.assetid: b1f03164-f0cf-42e3-942b-8cf90c242ffb
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3ee88cbcde2a25a13b4c4432afe5a5b1397ab727
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Office çözümlerinde geç bağlama](../vsto/late-binding-in-office-solutions.md)  
  
  