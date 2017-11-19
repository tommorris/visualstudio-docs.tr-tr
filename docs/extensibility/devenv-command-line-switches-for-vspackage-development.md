---
title: "Devenv komut satırı anahtarları VSPackage geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /setup command line switch
- /resetskippkgs command line switch
- /noVSIP command line switch
- /rootsuffix command line switch
- command-line switches
- registry, Visual Studio SDK
- command line, switches
- Visual Studio SDK, command-line switches
ms.assetid: d65d2c04-dd84-42b0-b956-555b11f5a645
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ca93d63236eb1b50663eff4c86a6ae3603600802
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="devenv-command-line-switches-for-vspackage-development"></a>Devenv komut satırı anahtarları VSPackage geliştirme
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]geliştiricilerin devenv.exe, Visual Studio tümleşik geliştirme ortamı (IDE) başlatan dosyanın yürütülürken komut satırından görevleri otomatikleştirmenizi sağlar.  
  
 Görevler aşağıdakileri içerir:  
  
-   IDE dışında tasarlanmış yapılandırmalardan uygulamalarda dağıtma.  
  
-   Otomatik olarak hazır kullanarak yapı projeleri derleme ayarları veya hata ayıklama yapılandırmaları.  
  
-   IDE belirli yapılandırmalar'daki tüm gelen IDE dışında yükleniyor. Ayrıca, başlatma sırasında IDE özelleştirebilirsiniz.  
  
## <a name="guidelines-for-switches"></a>Anahtarlar için yönergeler  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Belge kullanıcı düzeyinde devenv komut satırı anahtarları açıklanır. Daha fazla bilgi için bkz: [Devenv komut satırı anahtarları](../ide/reference/devenv-command-line-switches.md). Devenv VSPackage geliştirme, dağıtım ve hata ayıklama ile yararlı ek komut satırı anahtarlarını da destekler.  
  
|Komut satırı anahtarı|Açıklama|  
|--------------------------|-----------------|  
|/ safemode|Başlatır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] güvenli modda, yalnızca varsayılan IDE ve Hizmetleri Yükleniyor. / Safemode anahtarı tüm üçüncü taraf VSPackages ne zaman yüklenmesini engeller [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] başlar, bu nedenle kararlı yürütme sağlama.<br /><br /> Bu anahtar hiçbir bağımsız değişkenleri alır.|  
|/resetskippkgs|Tüm Atla sorunlu VSPackages yüklenmesini önlemek amacıyla isteyen kullanıcılar tarafından eklenen yükleme seçenekleri temizler ardından başlatır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. SkipLoading etiketi varlığını bir VSPackage yüklenmesini devre dışı bırakır. Etiket temizleme VSPackage yüklenmesini yeniden etkinleştirir.<br /><br /> Bu anahtar hiçbir bağımsız değişkenleri alır.|  
|/rootsuffix|Başlatır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] farklı bir konuma kullanarak. Aşağıdaki komutu tarafından oluşturulan kısayol tarafından çalıştırılan [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] yükleyici:<br /><br /> Devenv /RootSuffix exp<br /><br /> Bu durumda, exp 10.0 yerine belirli bir soneki, örneğin 10.0Exp konumuyla tanımlar. Deneysel örneği ayrı olarak örneğinden VSPackage hata ayıklama sayesinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kod yazmak için kullanmakta olduğunuz.<br /><br /> Bu anahtar VSRegEx.exe kullanarak oluşturduğunuz bir konum tanımlayan herhangi bir dize alabilir. Daha fazla bilgi için bkz: [deneysel örneği](../extensibility/the-experimental-instance.md).|  
|/Splash|Gösterir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] her zamanki gibi giriş ekranı ve ardından ana IDE gösterilmeden önce bir ileti kutusu gösterir. İleti kutusu için bir VSPackage ürün simgesi, örneğin kontrol ekranı araştırmak olanak sağlar.<br /><br /> Bu anahtar hiçbir bağımsız değişkenleri alır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut satırı anahtarları ekleme](../extensibility/adding-command-line-switches.md)   
 [Devenv komut satırı anahtarları](../ide/reference/devenv-command-line-switches.md)