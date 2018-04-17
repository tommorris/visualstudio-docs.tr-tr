---
title: SetThreadCount | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- SetThreadCount
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SetThreadCount
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 12861a869121daedf59f39a4c0e516abce6a7b70
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="setthreadcount"></a>SetThreadCount
Genel iş parçacığı sayısını ayarlar ve bu sayının geçerli iş parçacığına atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT WINAPI SetThreadCount(int threadCount);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `threadCount`  
 Kullanılacak iş parçacıklarının sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir **HRESULT** ile **başarılı** iş parçacığı sayısı güncelleştirildiyse biti ayarlanmamış.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** FileTracker.h