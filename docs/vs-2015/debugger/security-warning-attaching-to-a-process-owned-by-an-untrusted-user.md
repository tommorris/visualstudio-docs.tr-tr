---
title: 'Güvenlik Uyarısı: Güvenilmeyen bir kullanıcının sahip olduğu işleme ekleme tehlikeli olabilir. Aşağıdaki bilgiler kuşkulu görünüyorsa ya da emin değilseniz, bu işleme eklemeyin. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.attachsecuritywarning
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 52246c1e-a371-40a0-b756-a435cc51876f
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b856ac3a61d8af72d78546948bbe4ab780e9512e
ms.sourcegitcommit: d705e015cb525bfa87a0b93e93376c3956ec2707
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43231173"
---
# <a name="security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process"></a>Güvenlik Uyarısı: Güvenilmeyen bir kullanıcının sahip olduğu işleme ekleme tehlikeli olabilir. Aşağıdaki bilgiler kuşkulu görünüyorsa ya da emin değilseniz, bu işleme eklemeyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [güvenlik uyarısı: güvenilmeyen bir kullanıcının sahip olduğu işleme ekleme tehlikeli olabilir. Aşağıdaki bilgiler kuşkulu görünüyorsa ya da emin değilseniz, bu işleme eklemeyin](https://docs.microsoft.com/visualstudio/debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process).  
  
Kısmen güvenilen kodu içerir veya hemen bağlama gerçekleşmeden önce güvenilmeyen bir kullanıcının sahip olduğu bir işleme eklediğinizde, bu uyarı iletişim kutusu görüntülenir. Kötü amaçlı kod içeren bir güvenilmeyen işlemi hata ayıklamada bilgisayar zarar verme olasılığı vardır. İşlem güvenmeyecekleri nedeniniz sonra tıklatmanız gerekir **iptal** hata ayıklama önlemek için.  
  
 Yasal bir senaryo hata ayıklama sırasında bu uyarının gösterilmemesi için Visual Studio'yu kapatın ve bu kayıt defteri anahtarı değerini 1 olarak ayarlayın: `HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\<version>\Debugger\DisableAttachSecurityWarning`ve sonra Visual Studio'yu yeniden başlatın. Hata ayıklama senaryoyu tamamladıktan sonra değerini 0 olarak ayarlamak ve Visual Studio'yu yeniden başlatın.  
  
 "Kullanıcıların güvenilen" dahil kendiniz artı genellikle .NET Framework gibi yüklü olan bilgisayarlarda tanımlanan standart kullanıcı kümesini `aspnet`, `localsystem`, `networkservice`, ve `localservice`.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 Ad  
 Hata ayıklamak için istenen derlemenin adı  
  
 Kullanıcı  
 Geçerli kullanıcı  
  
 İliştir  
 Ekleyerek hatalarını ayıklamaya devam etmek için basın  
  
 İliştirme  
 İşleme eklemeyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalıştırma işlemleri iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Hata Ayıklayıcısı Güvenliği](../debugger/debugger-security.md)



