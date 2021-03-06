---
title: Kullanarak yalıtılmış Kabuğu değiştirme. Pkgundef dosya | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, isolated mode%2C .pkgundef file
ms.assetid: 9cee2a20-f8ac-4d9d-aef9-068fcd9f27a4
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3741fc9abdae6693670538c80288dfdefcefd84e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630548"
---
# <a name="modifying-the-isolated-shell-by-using-the-pkgundef-file"></a>Kullanarak yalıtılmış Kabuğu değiştirme. Pkgundef dosyası
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yalıtılmış Kabuğu kullanarak değiştirme. Pkgundef dosya](https://docs.microsoft.com/visualstudio/extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file).  
  
Yalıtılmış Kabuk uygulaması belirtilen kayıt defteri girişlerini dışarıda bırakmak için .pkgundef dosyası değiştirebilirsiniz. Genellikle, bir bilgisayarda, bir uygulama başlatıldığında ilk kez uygulamanın kök kayıt defteri anahtarı için Visual Studio kayıt defteri girdilerinin Visual Studio Kabuğu kopyalar. Bu, şu anda yüklü VSPackages yönelik başvuruları içerir.  
  
 Bir yalıtılmış Kabuk uygulamasından bir özel kayıt defteri girişi dışlamak için paket anahtarı giriş tarafından izlenen uygulama .pkgundef dosyası ekleyin. Yalnızca .pkgdef dosyası olduğu gibi anahtarları ve girişleri temsil edilir. diğer bir deyişle [$RootKey $] veya [$RootKey$\\*alt*] ve "*giriş*" =*değer*burada *alt* etkilemek için alt *giriş* kaldırmak için giriş ve *değer* ya da `""` veya `dword:00000000`.  
  
 Dışlanacak yalnızca kayıt defteri anahtarından birden çok girişi hariç tutmak her giriş için bir satır tarafından izlenen anahtarı bir kez listeler.  
  
 Yalıtılmış Kabuk uygulaması tüm kayıt defteri anahtarı tutmak için anahtar için uygulama .pkgundef dosyası ekleyin, ancak bu anahtar için kayıt defteri girdilerini belirtmeyin.  
  
 .Pkgundef dosyaya açıklama ekleyebilirsiniz. Tek satırlı açıklama iki eğik çizgi ilk iki karakter olmalıdır.  
  
 Örneğin, kaldırmak için **veritabanına bağlan** ve **hizmet vermemesini r Bağlan** komutlarını **Araçları** menüsünde, satırın açıklamasını kaldırın:  
  
```  
[$RootKey$\Packages\{8D8529D3-625D-4496-8354-3DAD630ECC1B}]  
```  
  
 ve satır ekleyin:  
  
```  
[$RootKey$\Packages\{198E76C1-34C0-424D-9957-B3EBD80265FB}]  
```  
  
 uygulamanın .pkgundef dosyası için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio özelliklerinin paket GUID'leri](../extensibility/package-guids-of-visual-studio-features.md)   
 [Yalıtılmış Kabuğu Özelleştirme](../extensibility/customizing-the-isolated-shell.md)

