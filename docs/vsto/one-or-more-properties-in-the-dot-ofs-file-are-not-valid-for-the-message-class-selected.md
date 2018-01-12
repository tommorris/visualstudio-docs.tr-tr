---
title: ".Ofs dosyasındaki bir veya daha fazla özellik seçilen ileti sınıfı için geçerli değildir | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSTO.NewFormRegionWizard.OFSPropertyError
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6ab0b36921911ac8c70501096868f47a40371f79
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="one-or-more-properties-in-the-ofs-file-are-not-valid-for-the-message-class-selected"></a>.ofs dosyasındaki bir veya daha fazla özellik seçilen ileti sınıfı için geçerli değil
  Outlook'ta tasarlanan form bölgesini içeri aktardığınızda, bu hata görünür, ancak bir veya daha fazla alan form bölgesi üzerindeki son sayfasında, seçtiğiniz ileti sınıfları ile uyumlu olmadığında **Yeni Form bölgesi** Sihirbazı.  
  
 Örneğin, seçebilirsiniz **görev (IPM. Görev)** son sayfasında **Yeni Form bölgesi** Sihirbazı. Form bölgesini içeriyorsa bir **iş adresi** alan, bir görev iş adresi olmadığından bu hatayı alırsınız. Bu nedenle, **iş adresi** alan IPM ile uyumlu değil. Görev ileti sınıfı.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Sihirbazın son sayfasında **Yeni Form bölgesi** Sihirbazı, form bölgesini alanları ile uyumlu bir ileti sınıfı seçin.  
  
-   Outlook Form tasarımcısında son sayfasında, seçmek için planlama ileti sınıfları ile uyumlu olmayan alanlarını kaldırın **Yeni Form bölgesi** Sihirbazı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Outlook'ta Tasarlanan Form Bölgesini İçeri Aktarma](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  