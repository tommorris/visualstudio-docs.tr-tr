---
title: "Unity Azure izlenecek güvenlik için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: F4FD6E1C-EA64-4613-BDDE-6E4E5CCF983E
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 1ffb0c57329a8453208978cee69daa771d8ee0e9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="update-unity-mono-security-certificate-store"></a>Güncelleştirme Unity Mono güvenlik sertifika deposu

Unity'nın Mono boş sertifika deposu ile birlikte gönderilir ve bu nedenle herhangi bir siteye güvenmezse. Daha fazla bilgiyi bu hakkında [Mono güvenlik sık sorulan sorular](http://www.mono-project.com/docs/faq/security/).

TLS yoksayılıyor olmadan Azure'a bağlanmak için / SSL, Unity Mono sertifika deposu olmalıdır güncelleştirildi.

## <a name="using-mozroots-to-install-certificates"></a>Sertifikaları yüklemek için mozroots kullanma

Mozroots aracı Mono olarak dahil edilir. İndirir ve Mozilla'nin kök sertifikalar listesini yükler.

1. Terminal komut istemi açın.

2. Terminale gezinme **C:\Program Files\Unity\Editor\Data\MonoBleedingEdge\bin >** dizin. Tam konumu, Unity yerel makinenizde yüklediğiniz bağlı olarak değişebilir.

3. Aşağıdaki komutu yazın ve isabet **Enter** çalıştırmak için:

  `mono ..\lib\mono\4.5\mozroots.exe --sync --import`

4. Şu (sayı veya eklenen sertifikaları değişebilir rağmen) çıktıyı almanız gerekir:

  ```
  Downloading from 'https://hg.mozilla.org/releases/mozilla-release/raw-file/default/security/nss/lib/ckfw/builtins/certdata.txt'...
  Importing certificates into user store...
  1 new root certificates were added to your trust store.
  Import process completed.
  ```

5. Çalıştırılabilmesi için artık TLS alma olmadan örnek proje ilgili hatalarla ilgili.

## <a name="next-step"></a>Sonraki adım

* [İstemci bağlantılarını test etme](visual-studio-tools-for-unity-azure-connection.md)
