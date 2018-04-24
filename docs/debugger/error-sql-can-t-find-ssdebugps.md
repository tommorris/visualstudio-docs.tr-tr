---
title: "Hata: SQL yapabilirsiniz&#39;bulamıyorsanız SSDEBUGPS'yi | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f263d76667eb197d85a99ba06a45fc08e2f4d0d6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="error-sql-can39t-find-ssdebugps"></a>Hata: SQL yapabilirsiniz&#39;t SSDEBUGPS'yi Bul

SSDEBUGPS.dll SQL Server hata ayıklama konağı bileşendir.

Bu hata, hata ayıklama başlatmaya çalışırken oluşur ve belirtilen dosya mevcut olmadığı anlamına [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] makine. Olası nedenler şunlardır: ya da uzaktan hata ayıklama Kurulumu hiçbir zaman çalıştırıldığı ya da şekilde bu dosyayı sildiğini.

Bu hatayı gidermek için iki yolu vardır: uzaktan hata ayıklama kurulumu yeniden çalıştırmadan ve dosyanın üzerine kopyalama [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] makine.

Uzaktan hata ayıklama Kur'u yeniden çalıştırmak için yönergeleri izleyin [uzaktan hata ayıklama](../debugger/remote-debugging.md).

Ssdebugps.dll bir kopyasını bulabiliyorsa sürüklediğinizde kopyalayabilirsiniz [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] makine. Varsa, dosyayı dizin \Program Files\ içinde ortak Files\Microsoft Shared\SQL Debugging olacaktır. Bunu başka bir bulabilirsiniz [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] makine, veya Visual Studio 2005 yüklü olduğu bir makineye.

SQL Server 2005 makineye yüklenmesi SSDEBUGPS.dll kopyalamak için:

1. Dosyayı aynı ad ve yol dizine kopyalayın [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] makine.

2. Açarak kaydetmek bir **komut istemi**ve aşağıdaki komutu çalıştırın:

    ```
    regsrv32 ssdebugps.dll
    ```