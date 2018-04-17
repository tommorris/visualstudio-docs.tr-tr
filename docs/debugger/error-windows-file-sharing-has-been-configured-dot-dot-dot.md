---
title: 'Hata: Windows dosya paylaşımı yapılandırıldı... | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.remote_credentials_prohibited
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
ms.openlocfilehash: 95ecba6f793ddb0f4daadec67760a3e6ccdba7e0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-windows-file-sharing-has-been-configured"></a>Hata: Windows dosya paylaşımı yapılandırıldı...
Farklı bir kullanıcı adı kullanarak uzak bilgisayara bağlanır böylece Windows dosya paylaşımı yapılandırıldı. Bu uzaktan hata ayıklama ile uyumsuz.  
  
 Geçerli dosya yapılandırma paylaşımı farklı bir kullanıcı adı kullanarak uzak bilgisayara bağlanmak için ayarlanır. Uzaktan hata ayıklama, bu senaryoda mümkün değildir.  
  
 Bu hatayı düzeltmek için bir hesap adı kullanarak bilgisayara oturum veya altında hata ayıklama hesap adı kullanmak için dosya paylaşımı değiştirin.  
  
 Bu kullanıcı adı kullanarak uzak bilgisayara bağlanmak istiyorsanız, uzak bilgisayardan bağlantısını kesmeniz gerekir.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Yerel makinenizdeki, başka bir hesap adı kullanarak hata ayıklama yaptığınız makine oturum açın.  
  
     —veya—  
  
     biçimindeki telefon numarasıdır. Uzak bilgisayardan çıkarın ve ardından hesap adınızı kullanarak diğer makineye bağlanmak için dosya paylaşımını yeniden yapılandırın:  
  
    1.  Üzerinde **Başlat** menüsündeki **Donatılar**ve ardından **komut istemi**.  
  
    2.  Windows komut isteminde yazın:  
  
         `net use /delete computer_name`  
  
    3.  Windows Yardımı'nda belgelenen yöntemlerden birini kullanarak dosya paylaşım ayarlarınızı değiştirin.