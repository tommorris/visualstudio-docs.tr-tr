---
title: Bu projeyi oluşturmak için kullanılan çalışma kitabı tasarımcının yükleyemeyeceği ActiveX denetimleri içeriyor | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.SelectDocWizard.ContainsActiveXControls
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8d31674f54ce454db50a63572c24f92031e7d886
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
  
  