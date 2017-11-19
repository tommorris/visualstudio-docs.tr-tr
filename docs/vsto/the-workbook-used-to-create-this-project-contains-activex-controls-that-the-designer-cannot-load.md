---
title: "Bu projeyi oluşturmak için kullanılan çalışma kitabı tasarımcının yükleyemeyeceği ActiveX denetimleri içeriyor | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.SelectDocWizard.ContainsActiveXControls
dev_langs:
- VB
- CSharp
ms.assetid: 91e9c6ee-7543-41e3-be0c-6c000cfd32d1
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 74f68bdea80705d1b774d9f24a5ba3b122b6f653
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="the-workbook-used-to-create-this-project-contains-activex-controls-that-the-designer-cannot-load"></a>Bu projeyi oluşturmak için kullanılan çalışma kitabı tasarımcının yükleyemeyeceği ActiveX denetimleri içeriyor
  Bu hata, bir Word belgesi için bir denetim eklediğinizde veya Excel çalışma program aracılığıyla, belge veya çalışma kitabını kaydedin ve belge veya çalışma kitabı temel alan yeni bir belge düzeyi çözümü oluşturun görüntülenir.  
  
 Denetimin yönetilen türü açıklayan bilgiler, belge veya çalışma kitabı ile birlikte kaydedilmez. Bu belge veya çalışma kitabı temel alan yeni bir çözüm oluşturduğunuzda, Visual Studio konak öğesi Tasarımcısı'nda denetimi yüklemek için yeterli bilgi yok.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Belge veya çalışma kitabı açın.  
  
2.  Çalışma zamanında eklenen denetimlerini kaldırma. Belge veya çalışma kitabında seçme ve DELETE tuşuna basarak bunu yapabilirsiniz.  
  
3.  Belge veya çalışma kitabı göre bir belge düzeyi çözümü oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  