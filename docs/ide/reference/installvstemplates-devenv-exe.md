---
title: devenv.exe InstallVSTemplates switch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /InstallVSTemplates switch
- /InstallVSTemplates Devenv switch
- InstallVSTemplates switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 529979caa801ace8dd649cf1614f2eeb27ca070b
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2018
---
# <a name="installvstemplates-devenvexe"></a>/InstallVSTemplates (devenv.exe)

/InstallVSTemplates bulunan kayıtları proje veya öğe şablonları geçiş  *\<Visual Studio yükleme yolu >*\Common7\IDE\ProjectTemplates\ veya  *\<Visual Studio yükleme yolu >*\Common7\IDE\ItemTemplates\ aracılığıyla erişilebilir böylece **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları.

> [!WARNING]
> Bu anahtar, yalnızca Visual Studio iş ortağı geliştirme için desteklenir. Kullanmak için yönetici olarak devenv çalıştırmalısınız [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) ve [/InstallVSTemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) anahtarları. Daha fazla bilgi için bkz: [kullanıcı izinleri](../../ide/user-permissions-and-visual-studio.md).

## <a name="syntax"></a>Sözdizimi

```
devenv.exe /InstallVSTemplates
```

## <a name="see-also"></a>Ayrıca bkz.

[Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)