---
redirect_url: shell/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file
title: "Yalıtılmış Kabuk kullanarak değiştirme. Pkgundef dosya | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode, .pkgundef file
ms.assetid: 9cee2a20-f8ac-4d9d-aef9-068fcd9f27a4
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dfe0e4b39e96d98718ff98025add521a678699ac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="modifying-the-isolated-shell-by-using-the-pkgundef-file"></a>Yalıtılmış Kabuk kullanarak değiştirme. Pkgundef dosyası
Yalıtılmış Kabuk uygulamadan belirtilen kayıt defteri girişlerini dışarıda bırakmak için .pkgundef dosyasını değiştirebilirsiniz. Genellikle, uygulamanın bir bilgisayarda, ilk başlattığınızda uygulama için kök kayıt defteri anahtarına Visual Studio kayıt defteri girdilerinin Visual Studio Kabuğu'nu kopyalar. Bu, şu anda yüklü VSPackages yönelik tüm başvuruları içerir.  
  
 Yalıtılmış Kabuk uygulamadan belirli kayıt defteri girdisini dışlamak için paket anahtarı giriş tarafından izlenen uygulama .pkgundef dosyasına ekleyin. Yalnızca .pkgdef dosyasını olduğu gibi anahtarları ve girişleri gösterilir; diğer bir deyişle, [$RootKey $] veya [$RootKey$\\*alt*] ve "*girişi*" =*değeri*, burada *alt* etkilemek için alt anahtar *girişi* kaldırmak için giriş ve *değeri* ya `""` veya `dword:00000000`.  
  
 Kayıt defteri anahtarından birden çok giriş dışlamak için yalnızca anahtar bir kez dışlamak her giriş için bir satır arkasından listeleyin.  
  
 Tüm kayıt defteri anahtarı bir yalıtılmış Kabuk uygulamasından dışlamak için anahtar uygulama .pkgundef dosyasına eklemek, ancak bu anahtar için kayıt defteri girdilerini belirtmeyin.  
  
 .Pkgundef dosya yorumlar ekleyebilirsiniz. Tek satırlı yorum iki eğik çizgi ilk iki karakter olmalıdır.  
  
 Örneğin, kaldırmak için **veritabanına bağlan** ve **hizmet vermemesini r Bağlan** komutlarını **Araçları** menüsünde satırı açıklamadan çıkarın:  
  
```  
[$RootKey$\Packages\{8D8529D3-625D-4496-8354-3DAD630ECC1B}]  
```  
  
 ve satırı ekleyin:  
  
```  
[$RootKey$\Packages\{198E76C1-34C0-424D-9957-B3EBD80265FB}]  
```  
  
 uygulamanın .pkgundef dosyasına.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio özelliklerinin paketi GUID](../extensibility/package-guids-of-visual-studio-features.md)   
 [Yalıtılmış Kabuğu Özelleştirme](../extensibility/customizing-the-isolated-shell.md)