---
title: "CreateExpInstance yardımcı programı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- experimental builds
- experimental hive
- experimental instance
- createexpinstance
- createexpinst
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c1104ebfbd066ad438262fcca0186acfb3854dbd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="createexpinstance-utility"></a>CreateExpInstance yardımcı programı
Sıfırlamak oluşturmak için CreateExpInstance yardımcı programını kullanın veya Visual Studio deneysel örneği silin. Hata ayıklama ve temel alınan ürün değiştirmeden Visual Studio uzantılarını test etmek için deneysel örneği kullanabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix  
```  
  
#### <a name="parameters"></a>Parametreler  
 / Oluşturma  
 Deneysel örneği oluşturur.  
  
 / Sıfırla  
 Deneysel örneği siler ve sonra yeni bir tane oluşturur.  
  
 /Clean  
 Deneysel örneği siler.  
  
 / VSInstance  
 Kopyalamak için temel Visual Studio örneği içeren dizinin adı.  
  
 / RootSuffix  
 Deneysel örneği dizin adının sonuna eklenecek soneki.  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio uzantısı üzerinde çalışırken, varsayılan Deneysel örneğini açın ve geçerli uzantısı yüklemek için F5 tuşuna basabilirsiniz. Hiçbir deneysel örneği varsa, Visual Studio varsayılan ayarlara sahip bir tane oluşturur.  
  
 Deneysel örneği varsayılan konumunu Visual Studio sürüm sayısına bağlıdır. Örneğin, Visual Studio 2015 için %localappdata%\Microsoft\VisualStudio\14.0Exp\ konumdur dizinini konumdaki tüm dosyaları bu örnek bir parçası olarak kabul edilir. Dizin adı varsayılan konuma değiştirilmediği sürece herhangi bir ek Deneysel örnekler Visual Studio tarafından yüklü değil.  
  
 Deneysel örneği açıldığında visual Studio sistem kayıt defteri erişmez. Bu, kullanılan kayıt defteri kovanını Deneysel bir sürümü Visual Studio'nun önceki sürümlerden farklıdır.  
  
 CreateExpInstance yardımcı programı VsRegEx yardımcı programının yerine geçer.  
  
 Aşağıdaki örnek Visual Studio varsayılan Deneysel örneğini sıfırlar.  
  
 **CreateExpInstance.exe/Reset /VSInstance 14.0 = /RootSuffix Exp =**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackage’lar](../../extensibility/internals/vspackages.md)