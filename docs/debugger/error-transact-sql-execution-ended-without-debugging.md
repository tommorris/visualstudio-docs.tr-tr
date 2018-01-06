---
title: "Hata: Transact-SQL yürütmesi sonlandırıldı hata ayıklama olmadan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.sqlde_sql_executed_but_not_debugged
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 793e516c334d39cd7befc82a15e793df44d22f3b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-transact-sql-execution-ended-without-debugging"></a>Hata: Transact-SQL yürütmesi hata ayıklaması yapılmadan sonlandı
Bu hata, bir Transact-SQL veya SQLCLR yordamı hata ayıklama denediğiniz ve hata ayıklayıcısı hata ayıklama iletilerini SQL Server'dan almaz oluşur.  
  
 Bu ağ sorunları nedeniyle veya SQL Server üzerinde sorunları olabilir, ancak en olası nedeni izinler bir sorundur.  
  
 Söz konusu iki hesap vardır:  
  
-   Kullanıcı hesabı uygulama hesabıdır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] olarak çalışıyor.  
  
-   SQL sunucusuna bağlantı yapmak için kullanılan kimlik bağlantısı hesabıdır. Bu mutlaka bağlantı SQL kimlik doğrulaması kullanılıyorsa gibi Visual Studio çalıştıran kimliği ile aynı değildir.  
  
 SQL hata ayıklama uygulama hesabı gerekir veya bağlantı hesabı eşleşen sysadmin olmasını gerektirir.  
  
 Bir SQL oturum açma sa gibi kullanıyorsanız, uygulama hesabı kurulum SQL Server'da sysadmin olarak olmalıdır. Varsayılan olarak, yöneticiler makine SQL server üzerinde çalıştığı SQL Server sysadmins bulunur.  
  
 Bu hatayı düzeltmek için ihtiyacınız:  
  
-   İzinleri ayarlarınızı doğrulayın. Daha fazla bilgi için bkz: [nasıl yapılır: hata ayıklama için SQL Server izinleri ayarlama](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
-   SQL, hata ayıklama'ı doğru bir şekilde ayarlanan emin olun.  
  
-   Ağ veya veritabanı yöneticinize başvurun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SQL hata ayıklama Kurulumu ayarlama](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)   
 [Nasıl yapılır: hata ayıklama için SQL Server izinleri ayarla](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)