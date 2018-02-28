---
title: "Hata: Kullanıcı verebilir değil yürütme sp_enable_sql_debug saklı yordamını yürütemedi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.sqlde_accessdenied
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5da5a9aa6bc5f2bda382b69223b2b758f576ac29
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-user-could-not-execute-stored-procedure-spenablesqldebug"></a>Hata: Kullanıcı sp_enable_sql_debug Saklı Yordamını Yürütemedi
Sp_enable_sql_debug saklı yordamını yürütemedi sunucuda yürütülemedi. Bunun nedeni:  
  
-   Bir bağlantı sorunu. Sunucunun kararlı bağlantısı olması gerekir.  
  
-   Sunucu üzerindeki gerekli izinleri eksiği. SQL Server 2005'te hata ayıklamak için Visual Studio çalıştıran hesabı ve SQL Server'a bağlanmak için kullanılan hesabın sysadmin rolünün üyesi olması gerekir. (SQL kimlik doğrulaması kullanıyorsanız) SQL Server'a bağlanmak için kullanılan hesabın (Windows kimlik doğrulaması kullanıyorsanız), Windows kullanıcı hesabı veya kullanıcı kimliği ve parolası olan bir hesap yok.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: hata ayıklama için SQL Server izinleri ayarlama](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: hata ayıklama için SQL Server izinleri ayarla](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [SQL hata ayıklama Kurulumu ayarlama](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)