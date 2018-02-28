---
title: "Bu projeyi oluşturmak için kullanılan çalışma kitabı tasarımcının yükleyemeyeceği ActiveX denetimleri içeriyor | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.SelectDocWizard.ContainsActiveXControls
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 0f50342fd82826aec8cf0d9694454afdc2db4080
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
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
  
  