---
title: İş Akışı Tasarımcısı - Visual Studio hata ayıklayıcısı Windows Workflow Foundation (eski) için devre dışı bırakma
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, disabling debugger
- debugging workflows, disabling debugger
- workflow debugger, disabling
ms.assetid: 9da96d0e-f941-4fa9-a1a5-6bab50adfec9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 473ee507e35f5ec5df902df64ee34326dcf90a2b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31969971"
---
# <a name="disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Windows Workflow Foundation (eski) için Visual Studio hata ayıklayıcısı devre dışı bırakma

Bu konu, Visual Studio eski Windows iş akışı Tasarımcısı'nda Windows Workflow Foundation (WF) uygulamaları oluştururken yapılandırma dosyası kullanarak hata ayıklayıcısında devre dışı bırakmak açıklar. .NET Framework sürüm 3.5 veya WinFX hedeflemek gerektiğinde eski iş akışı Tasarımcısı kullanın.

 Varsayılan olarak, Visual Studio hata ayıklayıcısı için Windows Workflow Foundation (WF) bir ana bilgisayar işlemi için etkinleştirilir. İş akışı hata ayıklama devre dışı bırakmak için açıkça bunu bir "DisableWorkflowDebugging" girişini ekleyerek devre dışı bırakmalısınız  **\<anahtarları >** öğesinde  **\<system.diagnostics >** ana bilgisayar yapılandırma dosyası bölümünü.

 Aşağıdaki örnek iş akışı hata ayıklama devre dışı bırakmak için yapılandırma dosyası ana bilgisayarı değiştirme gösterir.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <system.diagnostics>
      <switches>
         <add name="DisableWorkflowDebugging" value="true"/>
      </switches>
   </system.diagnostics>
</configuration>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Windows Workflow Foundation için Visual Studio Hata Ayıklayıcısını Çağırma (Eski)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)
- [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)