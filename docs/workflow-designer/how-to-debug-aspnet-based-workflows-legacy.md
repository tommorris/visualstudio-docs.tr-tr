---
title: "Nasıl yapılır: hata ayıklama ASP.NET tabanlı iş akışları (eski) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- ASP.NET, debugging workflows
- debugging workflows, ASP.NET workflows
- ASP.NET workflows, debugging
- debugging, ASP.NET workflows
ms.assetid: 79b21edc-9e7d-410d-af68-09c1598b9c30
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: aspnet
ms.openlocfilehash: 36905d8716b2f6a0fd961f668b7b5ca7c3ef623d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-aspnet-based-workflows-legacy"></a>Nasıl yapılır: hata ayıklama ASP.NET tabanlı iş akışları (eski)
Bu konu, hata ayıklamak açıklar [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]-tabanlı [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] ya da hedefleyen uygulamalar [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] eski içinde [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)].  
  
 ASP.NET başlatılan eski iş akışları veya iş akışının barındırılan işlemi ekleyerek Web hizmeti olarak yayımlanan eski iş akışları ayıklayabilirsiniz.  
  
### <a name="to-debug-an-aspnet-based-workflow"></a>ASP.NET tabanlı bir iş akışını hata ayıklamak için  
  
1.  ASP.NET uygulaması için ayarlayarak hata ayıklamayı etkinleştir **debug = true** web.config dosyasında.  
  
2.  İş akışı kitaplığı başlangıç projesi olarak ayarlayın ve iş akışını kesme noktalarını ayarlayın.  
  
3.  İş akışı Proje Özellikleri'nde varsayılan Web sayfasının URL'sini girin **hata ayıklama** seçeneği **başlangıç tarayıcı dış URL ile** metin kutusu.  
  
4.  Seçin **ekleme işlemi için** üzerinde **hata ayıklama** menüsü.  
  
5.  Gelen ekleme işlemini seçin **kullanılabilir işlemler** listesi.  
  
     İş akışı barındırılan w3wp.exe, webdev.webserver veya aspnet_wp işleme iliştirilemiyor.  
  
6.  Tıklatın **seçin** yanına **eklemek için** metin kutusu.  
  
     **Kod türünü seç** iletişim kutusu görüntülenir.  
  
7.  Seçin **bu kodu türleri hata ayıklama** seçip **iş akışı**.  
  
8.  **Tamam**'ı tıklatın.  
  
9. Tıklatın **Attach**.  
  
10. Varsayılan Web sayfasını bir tarayıcıda açın ve iş akışı başlatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio hata ayıklayıcısı Windows Workflow Foundation (eski) için çağırma](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)   
 [Nasıl yapılır: kesme iş akışları (eski)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)   
 [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)