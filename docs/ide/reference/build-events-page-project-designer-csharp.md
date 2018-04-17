---
title: Derleme olayları sayfası, Proje Tasarımcısı (C#) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- cs.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- Project Designer, Build Events page
- pre-build events
- post-build events
ms.assetid: 3fff9ae5-213c-46ea-a660-1d70acb6c922
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: ec7aa70db8ca2f4fc4ea8f0a4a06fc35857be27b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="build-events-page-project-designer-c"></a>Derleme Olayları Sayfası, Proje Tasarımcısı (C#)
Kullanım **yapı olayları** sayfasında **Proje Tasarımcısı** yapı yapılandırma yönergeleri belirtmek için. Ayrıca altında oluşturma sonrası olay çalıştığı koşulları belirtebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: derleme olayları belirtme (C#)](../../ide/how-to-specify-build-events-csharp.md)ve [nasıl yapılır: belirtin Build Events (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Yapılandırma**  
 Bu denetim, bu sayfada düzenlenebilir değil. Bu denetim açıklaması için bkz: [derleme sayfası, Proje Tasarımcısı (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Platform**  
 Bu denetim, bu sayfada düzenlenebilir değil. Bu denetim açıklaması için bkz: [derleme sayfası, Proje Tasarımcısı (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Derleme öncesi olay komut satırı**  
 Yapı başlamadan önce yürütülecek herhangi bir komut belirtir. Uzun komutları yazmak için tıklatın **düzen oluşturma öncesi** görüntülemek için [oluşturma öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
> [!NOTE]
>  Oluşturma öncesi olaylar proje güncel olduğundan ve hiçbir derleme tetiklenir çalıştırmayın.  
  
 **Derleme sonrası olay komut satırı**  
 Derleme sona erdikten sonra yürütmek için herhangi bir komut belirtir. Uzun komutları yazmak için tıklatın **düzen oluşturma sonrası** görüntülemek için **oluşturma öncesi olay/derleme sonrası olay komut satırı iletişim kutusu**.  
  
> [!NOTE]
>  Ekleme bir `call` .bat dosyaları çalıştıran tüm sonrası derleme komutları önce deyim. Örneğin, `call C:\MyFile.bat` veya `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Oluşturma sonrası olay çalıştırın**  
 Aşağıdaki tabloda gösterildiği gibi çalıştırmak, oluşturma sonrası olay için aşağıdaki koşulları belirtir.  
  
|Seçenek|Sonuç|  
|------------|------------|  
|**Her zaman**|Oluşturma sonrası olay oluşturma işlemi başarılı olup olmadığını bağımsız olarak çalışır.|  
|**Üzerinde başarılı derleme**|Oluşturma işlemi başarılı olursa oluşturma sonrası olay çalıştırın. Bu nedenle, olay oluşturma işlemi başarılı olduğu sürece, güncel bile bir proje için çalışır.|  
|**Yapı proje çıktı zaman güncelleştirir**|Derleyicinin çıktı dosyası (.exe veya .dll) daha önceki derleyici çıktı dosyasını farklı olduğunda oluşturma sonrası olay yalnızca çalıştırılır. Bu nedenle, bir proje güncel ise oluşturma sonrası olay çalıştırılmaz.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: derleme olayları belirtme (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Nasıl yapılır: derleme olayları belirtme (C#)](../../ide/how-to-specify-build-events-csharp.md)   
 [Proje Özellikleri başvurusu](../../ide/reference/project-properties-reference.md)   
 [Derleme ve Oluşturma](../../ide/compiling-and-building-in-visual-studio.md)