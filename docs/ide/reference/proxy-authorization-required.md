---
title: "Proxy yetkilendirme düzeltilmesi gereken hatalar | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e33e0e2896ccb3a5f7fe6d6da57f509af30d77fe
ms.sourcegitcommit: 06cdc1651aa7f45e03d260080da5a623d6258661
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2018
---
# <a name="proxy-authorization-required"></a>Proxy kimlik doğrulaması gerekli

Bu hata genellikle kullanıcılar bir proxy sunucu üzerinden Internet'e bağlı ve proxy sunucusu için bazı ağ kaynaklarına Visual Studio yapar çağrıları engeller oluşur.

## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Visual Studio'yu yeniden başlatın. Proxy kimlik doğrulaması iletişim kutusu görünür. İletişim kutusunda kimlik bilgilerinizi girin.

- Yukarıdaki adımı sorunu çözmezse http://go.microsoft.com adresleri ancak bunu yapar proxy sunucunuzun kimlik bilgileri istenmez Bunun nedeni olabilir *. visualStudio.com adresleri. Bu sunucular için Visual Studio tüm oturum açma senaryoları engellemesini kaldırmak için URL aşağıdaki listesini beyaz liste ile gerekir:

    - *.windows.net

    - *.microsoftonline.com

    - *.visualstudio.com

    - *.microsoft.com

    - *.live.com

- Böylece Visual Studio yeniden başlatıldığında proxy kimlik doğrulama iletişim http://go.microsoft.com adresi hem de sunucu uç noktaları için görüntülenir http://go.microsoft.com adres beyaz liste Aksi takdirde kaldırabilirsiniz.

    VEYA

- Varsayılan kimlik bilgilerinizi proxy ile kullanmak istiyorsanız, aşağıdakileri yapabilirsiniz:

    1. Bul **devenv.exe.config** (devenv.exe yapılandırma dosyası) içinde: **%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE** veya **% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE**.

    1. Yapılandırma dosyasında bulmak `<system.net>` engelleme ve bu kodu ekleyin:

        ```xml
        <defaultProxy enabled="true" useDefaultCredentials="true">
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>
        </defaultProxy>
        ```

        Ağınızda için doğru proxy adresi eklemelisiniz `proxyaddress="<http://<yourproxy:port#>`.

    VEYA

- ' Ndaki yönergeleri de izleyebilirsiniz [bu post](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) proxy kullanmanıza olanak sağlayacak kodu eklemek için.
