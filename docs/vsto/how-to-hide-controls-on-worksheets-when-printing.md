---
title: "Nasıl yapılır: yazdırırken çalışma sayfası denetimlerini gizleme | Microsoft Docs"
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
- printing [Office development in Visual Studio], worksheets
- controls [Office development in Visual Studio], hiding while printing
- printing [Office development in Visual Studio], hiding controls
- worksheets, hiding controls when printing
ms.assetid: a637fe9a-9de1-4162-8ff6-fe28ccd62389
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 17ebd691120d1d5aba2623f8178d95c3fc142dee
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hide-controls-on-worksheets-when-printing"></a>Nasıl Yapılır: Yazdırırken Çalışma Sayfası Denetimlerini Gizleme
  Windows Forms denetimleri içeren bir Microsoft Office Excel belgeyi yazdırma sırasında denetimleri yazdırılan çalışma sayfalarında görünür değildir. Bir çalışma sayfası yazdırma sırasında denetimleri gizleyebilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  Verileri görüntüleyen denetimleri gizleme varsa bir <xref:Microsoft.Office.Tools.Excel.Controls.TextBox>, denetiminde verileri yazdırılan çalışma sayfalarında görünür olmaz.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-hide-controls-when-a-worksheet-is-printed"></a>Bir çalışma sayfası denetimlerini gizlemek için yazdırılan  
  
1.  Oluşturun veya bir Excel projesini Visual Studio'da açın ve doğrulayın **Sheet1** Tasarımcısı'nda görünür. Proje oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Gelen **ortak denetimler** sekmesinde **araç**, sürükleyin bir <xref:Microsoft.Office.Tools.Excel.Controls.Button> denetlemek için bir hücre `Sheet1`.  
  
3.  İçinde **özellikleri** penceresindeki ayarlayın <xref:Microsoft.Office.Tools.Excel.Controls.Button.PrintObject%2A> özelliğine **False**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Windows Forms denetimleri Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Nasıl yapılır: Windows Forms denetimleri Office belgelerine ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Nasıl Yapılır: Çalışma Sayfası Hücreleri İçinde Denetimleri Yeniden Boyutlandırma](../vsto/how-to-resize-controls-within-worksheet-cells.md)  
  
  