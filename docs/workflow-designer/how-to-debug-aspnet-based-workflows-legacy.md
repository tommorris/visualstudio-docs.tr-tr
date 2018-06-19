---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: hata ayıklama ASP.NET tabanlı iş akışları (eski)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
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
ms.openlocfilehash: 7bf16a6a88c5d4cd063f1c32ca846031d8b2588d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975878"
---
# <a name="how-to-debug-aspnet-based-workflows-legacy"></a>Nasıl yapılır: hata ayıklama ASP.NET tabanlı iş akışları (eski)

Bu konu, .NET Framework sürüm 3.5 hedefleyen ya da eski Windows iş akışı Tasarımcısı'nda WinFX ASP.NET tabanlı Windows Workflow Foundation (WF) uygulamalarının hatalarını açıklar.

ASP.NET başlatılan eski iş akışları veya iş akışının barındırılan işlemi ekleyerek Web hizmeti olarak yayımlanan eski iş akışları ayıklayabilirsiniz.

## <a name="to-debug-an-aspnet-based-workflow"></a>ASP.NET tabanlı bir iş akışını hata ayıklamak için

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