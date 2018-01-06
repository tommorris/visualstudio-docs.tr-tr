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
ms.workload: office
ms.openlocfilehash: 2227af08d42b6cf47f7db4ba68e568b9e315bae6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
 [Office Belgelerine Çalışma Zamanında Denetim Ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  