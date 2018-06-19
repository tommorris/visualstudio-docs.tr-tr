---
title: -ResetSettings (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3c3d3a6ef558b510cfde716716daf97a549fbba4
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33703993"
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)

Visual Studio varsayılan ayarlarına geri yükler ve Visual Studio IDE otomatik olarak başlatır. Ayarları isteğe bağlı olarak belirtilen bir sıfırlar *vssettings* dosya.

Varsayılan ayarlar, Visual Studio ilk kez başlatıldığında seçtiğiniz profili tarafından belirlenir.

## <a name="syntax"></a>Sözdizimi

```cmd
Devenv /ResetSettings SettingsFile
```

## <a name="arguments"></a>Arguments

`SettingsFile`

Dosyanın tam yolunu ve adını *vssettings* Visual Studio'ya uygulamak için dosya.

Genel Geliştirme Ayarları profili geri yüklemek için kullanmak `General`.

## <a name="remarks"></a>Açıklamalar

Öyle değilse `SettingsFile` belirtilmemişse, varsayılan ayarlar koleksiyonu seçmek için istenir sonraki başlatışınızda Visual Studio.

## <a name="example"></a>Örnek

Aşağıdaki komut satırını dosyasında depolanan ayarları uygular `MySettings.vssettings`.

```cmd
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md)
- [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)