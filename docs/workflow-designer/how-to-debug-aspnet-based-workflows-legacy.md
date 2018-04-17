---
title: 'Nasıl yapılır: hata ayıklama ASP.NET tabanlı iş akışları (eski) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ASP.NET, debugging workflows
- debugging workflows, ASP.NET workflows
- ASP.NET workflows, debugging
- debugging, ASP.NET workflows
ms.assetid: 79b21edc-9e7d-410d-af68-09c1598b9c30
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: ed3f4f23ff02291df33b2676bdb980de191b281b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-aspnet-based-workflows-legacy"></a>Nasıl yapılır: hata ayıklama ASP.NET tabanlı iş akışları (eski)
Bu konu, hata ayıklamak açıklar [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]-tabanlı [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] ya da hedefleyen uygulamalar [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] eski Windows iş akışı Tasarımcısı'nda.

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

## <a name="see-also"></a>Ayrıca bkz.

- [Windows Workflow Foundation için Visual Studio Hata Ayıklayıcısını Çağırma (Eski)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)
- [Nasıl Yapılır: İş Akışlarında Kesme Noktası Ayarlama (Eski)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)
- [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)