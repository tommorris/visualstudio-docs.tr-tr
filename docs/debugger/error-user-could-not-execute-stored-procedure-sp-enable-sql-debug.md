---
title: 'Hata: Kullanıcı verebilir değil yürütme sp_enable_sql_debug saklı yordamını yürütemedi | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.sqlde_accessdenied
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e36c56f594b9858334f3b67042183278afa218df
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31472429"
---
# <a name="error-user-could-not-execute-stored-procedure-spenablesqldebug"></a>Hata: Kullanıcı sp_enable_sql_debug Saklı Yordamını Yürütemedi
Sp_enable_sql_debug saklı yordamını yürütemedi sunucuda yürütülemedi. Bunun nedeni:  
  
-   Bir bağlantı sorunu. Sunucunun kararlı bağlantısı olması gerekir.  
  
-   Sunucu üzerindeki gerekli izinleri eksiği. SQL Server 2005'te hata ayıklamak için Visual Studio çalıştıran hesabı ve SQL Server'a bağlanmak için kullanılan hesabın sysadmin rolünün üyesi olması gerekir. (SQL kimlik doğrulaması kullanıyorsanız) SQL Server'a bağlanmak için kullanılan hesabın (Windows kimlik doğrulaması kullanıyorsanız), Windows kullanıcı hesabı veya kullanıcı kimliği ve parolası olan bir hesap yok.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: hata ayıklama için SQL Server izinleri ayarlama](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: hata ayıklama için SQL Server izinleri ayarla](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [SQL hata ayıklama Kurulumu ayarlama](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)