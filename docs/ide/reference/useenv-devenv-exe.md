---
title: -UseEnv (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.UseEnvVars.ExcludePath
- VC.Project.UseEnvVars.LibraryPath
- VC.Project.UseEnvVars.SourcePath
- VC.Project.UseEnvVars.Include
- VC.Project.UseEnvVars.Path
- VC.Project.UseEnvVars.ReferencePath
helpviewer_keywords:
- UseEnv switch
- /UseEnv Devenv switch
- Devenv, /UseEnv
ms.assetid: 2dd14603-a61b-42d2-ba31-427a0ee8a799
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4c48e9f22322cd5ebebeff0d987c32d369f98d03
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="useenv-devenvexe"></a>/UseEnv (devenv.exe)

Visual Studio başlar ve ortam değişkenlerini içine yükler **VC ++ dizinleri** iletişim kutusu.

> [!NOTE]
> Bu anahtarı ile yüklenen **C++ ile masaüstü geliştirme** iş yükü.

## <a name="syntax"></a>Sözdizimi

```shell
Devenv /useenv
```

## <a name="example"></a>Örnek

Aşağıdaki örnek Visual Studio başlatır ve ortam değişkenleri içine yükler **VC ++ dizinleri** iletişim kutusu.

```shell
Devenv.exe /useenv
```

## <a name="see-also"></a>Ayrıca bkz.

* [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)