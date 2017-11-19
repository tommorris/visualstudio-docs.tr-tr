---
title: "Hata: Windows dosya paylaşımı yapılandırıldı... | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.remote_credentials_prohibited
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: c45a1b74-61ec-4c64-9e2c-13051a4f50a5
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: afda40aea2340f85d27218b5a9cd7c4f09f64201
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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