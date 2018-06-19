---
title: CreatePkgDef yardımcı programı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- package definition
- create pkgdef
- pkgdef
- createpkgdef
ms.assetid: c745cb76-47a6-49ff-9eed-16af0f748e35
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b8ae53766a42ac2ed218bc92f59088d27e4434e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135797"
---
# <a name="createpkgdef-utility"></a>CreatePkgDef yardımcı programı
Bir parametre olarak Visual Studio uzantısı için bir .dll dosyası alır ve .pkgdef dosyayı .dll eşlik oluşturur. .Pkgdef dosya uzantısı yüklü olduğunda, aksi halde sistem kayıt defterine yazılan tüm bilgileri içerir.  
  
> [!NOTE]
>  Visual Studio SDK'ın otomatik olarak dahil edilen proje şablonları çoğunu .pkgdef dosyaları oluşturma işleminin bir parçası olarak oluşturun. Bu belge paketleri el ile oluşturmak veya .pkgdef dağıtımını kullanmak için mevcut paketleri dönüştürmek istediğiniz olanlar için tasarlanmıştır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
CreatePkgDef /out=FileName [/codebase] [/assembly] AssemblyPath  
```  
  
## <a name="arguments"></a>Arguments  
 / out =`FileName`  
 Gerekli. .Pkgdef çıktı dosyası adını ayarlar`FileName`.  
  
 /codebase  
 İsteğe bağlı. CodeBase yardımcı programı ile kayıt zorlar.  
  
 /Assembly  
 Derleme yardımcı programı ile kayıt zorlar.  
  
 `AssemblyPath`  
 .pkgdef oluşturmak istediğiniz .dll dosyasının yolu.  
  
## <a name="remarks"></a>Açıklamalar  
 .Pkgdef dosyaları kullanarak uzantı dağıtımı, Visual Studio'nun önceki sürümleri kayıt defteri gereksinimlerini değiştirir.  
  
 Aşağıdaki konumlardan birinde .pkgdef dosyaları yüklenmelidir: %localappdata%\Microsoft\Visual Studio\14.0\Extensions\ veya %vsinstalldir%\Common7\IDE\Extensions\\. Yükleme klasörünü %localappdata%\Microsoft\Visual Studio\14.0\Extensions ise\\, uzantıyı Visual Studio tarafından tanınan, ancak varsayılan olarak devre dışı bırakılacak. Kullanıcı uzantısını kullanarak etkinleştirebilirsiniz **Uzantılar ve güncelleştirmeler**. Yükleme klasörü %vsinstalldir%\Common7\IDE\Extensions ise\\, uzantı varsayılan olarak etkindir.  
  
> [!NOTE]
>  **Uzantılar ve güncelleştirmeler** aracı, VSIX paketi bir parçası olarak yüklenmiş bir uzantı erişmek için kullanılamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CreateExpInstance Yardımcı Programı](../../extensibility/internals/createexpinstance-utility.md)