---
title: "Sistem gereksinimleri algılama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup, VSPackages
- launch conditions
ms.assetid: 0ba94acf-bf0b-4bb3-8cca-aaac1b5d6737
caps.latest.revision: "50"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 92c4d51d575ffd6e5723bf80b8adc700b83f6afd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="detecting-system-requirements"></a>Sistem gereksinimleri algılama
Visual Studio yüklenmiş bir VSPackage çalışamaz. VSPackage yüklemesini yönetmek için Microsoft Windows Installer kullandığınızda, Visual Studio yüklü olup olmadığını algılamak için yükleyici yapılandırabilirsiniz. Diğer gereksinimler sistem örneğin denetlemek üzere, belirli bir Windows sürümü veya belirli bir RAM tutarına da yapılandırabilirsiniz.  
  
## <a name="detecting-visual-studio-editions"></a>Visual Studio sürümlerini algılama  
 Visual Studio sürümü yüklü olup olmadığını belirlemek için yükleme kayıt defteri anahtarının değerini (REG_DWORD) 1 uygun klasöründe olduğunu aşağıdaki tabloda listelendiği gibi doğrulayın. Visual Studio sürümlerini hiyerarşisini olduğuna dikkat edin:  
  
1.  Enterprise  
  
2.  Professional  
  
3.  Topluluk  
  
 "Daha yüksek" sürümü yüklendiğinde, bu sürüm de olduğu gibi "daha düşük" sürümleri için kayıt defteri anahtarları eklenir. Diğer bir deyişle, Enterprise edition yüklediyseniz, yükleme anahtar 1 Professional ve topluluk sürümleri yanı sıra, kuruluş için ayarlanır. Bu nedenle ihtiyacınız yalnızca "Yüksek" sürümü için denetlemeniz gerekir.  
  
> [!NOTE]
>  Kayıt Defteri Düzenleyicisi'ni 64 bit sürümünde 32-bit anahtarları HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node altında görüntülenen\\. Visual Studio anahtarları HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\DevDiv\vs\Servicing altında olan\\.  
  
|Ürün|Anahtar|  
|-------------|---------|  
|Visual Studio Enterprise 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\enterprise|  
|Visual Studio Professional 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\professional|  
|Visual Studio Community 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\community|  
|Visual Studio 2015 (tümleşik ve yalıtılmış) Kabuğu|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\isoshell|  
  
## <a name="detecting-when-visual-studio-is-running"></a>Visual Studio çalıştırırken algılama  
 VSPackage yüklendikten sonra Visual Studio çalışıyorsa, VSPackage doğru kaydedilemedi. Yükleyici, Visual Studio çalıştırırken algılamak ve programı yüklemek reddeder. Windows Installer böyle algılamayı etkinleştirmek için tablo girişleri kullanmanıza izin vermez. Bunun yerine, bir özel eylem şu şekilde oluşturmanız gerekir: kullanım `EnumProcesses` devenv.exe işlem algılamak ve ya da bir başlatma koşulu veya koşullu olarak kullanılan bir yükleyici özelliği ayarlamak için işlevi görüntülemek kapatmak için kullanıcıdan bir iletişim kutusu Visual Studio.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Installer ile VSPackages yükleme](../../extensibility/internals/installing-vspackages-with-windows-installer.md)