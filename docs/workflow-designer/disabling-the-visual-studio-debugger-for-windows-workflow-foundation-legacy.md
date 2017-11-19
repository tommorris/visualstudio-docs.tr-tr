---
title: "Windows Workflow Foundation (eski) için Visual Studio hata ayıklayıcısı devre dışı bırakma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- workflows, disabling debugger
- debugging workflows, disabling debugger
- workflow debugger, disabling
ms.assetid: 9da96d0e-f941-4fa9-a1a5-6bab50adfec9
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 835ca509c86a9be27486ee257839c4e161221e4e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Windows Workflow Foundation (eski) için Visual Studio hata ayıklayıcısı devre dışı bırakma
Bu konu, devre dışı bırakmak açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oluştururken yapılandırma dosyası kullanarak hata ayıklayıcı [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] eski uygulamalarda [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ya da hedeflemek gerektiğinde [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Varsayılan olarak, [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] için hata ayıklayıcı [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] bir ana bilgisayar işlemi için etkinleştirilir. İş akışı hata ayıklama devre dışı bırakmak için açıkça bunu bir "DisableWorkflowDebugging" girişini ekleyerek devre dışı bırakmalısınız  **\<anahtarları >** öğesinde  **\<system.diagnostics >**ana bilgisayar yapılandırma dosyası bölümünü.  
  
 Aşağıdaki örnek iş akışı hata ayıklama devre dışı bırakmak için yapılandırma dosyası ana bilgisayarı değiştirme gösterir.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="DisableWorkflowDebugging" value="true"/>  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio hata ayıklayıcısı Windows Workflow Foundation (eski) için çağırma](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)   
 [Hata ayıklama eski iş akışları](../workflow-designer/debugging-legacy-workflows.md)