---
title: .Ofs dosyasındaki bir veya daha fazla özellik seçilen ileti sınıfı için geçerli değildir | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.OFSPropertyError
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7ac9f5ab05ba6ed858946b5f665d850eea51c230
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="one-or-more-properties-in-the-ofs-file-are-not-valid-for-the-message-class-selected"></a>.ofs dosyasındaki bir veya daha fazla özellik seçilen ileti sınıfı için geçerli değil
  Outlook'ta tasarlanan form bölgesini içeri aktardığınızda, bu hata görünür, ancak bir veya daha fazla alan form bölgesi üzerindeki son sayfasında, seçtiğiniz ileti sınıfları ile uyumlu olmadığında **Yeni Form bölgesi** Sihirbazı.  
  
 Örneğin, seçebilirsiniz **görev (IPM. Görev)** son sayfasında **Yeni Form bölgesi** Sihirbazı. Form bölgesini içeriyorsa bir **iş adresi** alan, bir görev iş adresi olmadığından bu hatayı alırsınız. Bu nedenle, **iş adresi** alan IPM ile uyumlu değil. Görev ileti sınıfı.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Sihirbazın son sayfasında **Yeni Form bölgesi** Sihirbazı, form bölgesini alanları ile uyumlu bir ileti sınıfı seçin.  
  
-   Outlook Form tasarımcısında son sayfasında, seçmek için planlama ileti sınıfları ile uyumlu olmayan alanlarını kaldırın **Yeni Form bölgesi** Sihirbazı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Outlook'ta Tasarlanan Form Bölgesini İçeri Aktarma](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  