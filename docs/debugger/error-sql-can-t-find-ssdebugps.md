---
title: "Hata: SQL Can &#39;/; bulamadığınız SSDEBUGPS'yi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0e45c70d8186a178bafe6544bf83dcec1ed35d9d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-sql-can39t-find-ssdebugps"></a>Hata: SQL Can &#39;/; bulamadığınız SSDEBUGPS'yi
SSDEBUGPS.dll SQL Server hata ayıklama konağı bileşendir.  
  
 Bu hata, hata ayıklama başlatmaya çalışırken oluşur ve belirtilen dosya mevcut olmadığı anlamına [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] makine. Olası nedenler şunlardır: ya da uzaktan hata ayıklama Kurulumu hiçbir zaman çalıştırıldığı ya da şekilde bu dosyayı sildiğini.  
  
 Bu hatayı gidermek için iki yolu vardır: uzaktan hata ayıklama kurulumu yeniden çalıştırmadan ve dosyanın üzerine kopyalama [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] makine.  
  
 Uzaktan hata ayıklama Kur'u yeniden çalıştırmak için yönergeleri izleyin [uzaktan hata ayıklama](../debugger/remote-debugging.md).  
  
 Ssdebugps.dll bir kopyasını bulabiliyorsa sürüklediğinizde kopyalayabilirsiniz [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] makine. Varsa, dosyayı dizin \Program Files\ içinde ortak Files\Microsoft Shared\SQL Debugging olacaktır. Bunu başka bir bulabilirsiniz [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] makine, veya farklı olan bir makinede [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)] yüklü.  
  
### <a name="to-copy-ssdebugpsdll-onto-the-sql-server-2005-machine"></a>SQL Server 2005 makineye yüklenmesi SSDEBUGPS.dll kopyalamak için  
  
1.  Dosyayı aynı ad ve yol dizine kopyalayın [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] makine.  
  
2.  Açarak kaydetmek bir **komut istemi**ve aşağıdaki komutu çalıştırın:  
  
    ```  
    regsrv32 ssdebugps.dll  
    ```