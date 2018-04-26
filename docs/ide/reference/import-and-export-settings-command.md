---
title: Ayarları İçeri ve Dışarı Aktar Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a95841d9b9b8e67f34883efcc1a55a2daba7e8b7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="import-and-export-settings-command"></a>Ayarları İçeri ve Dışarı Aktar Komutu
Exports veya sıfırlar alır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ayarlar.

## <a name="syntax"></a>Sözdizimi

```
Tools.ImportandExportSettings [/export:filename | /import:filename | /reset]
```

## <a name="switches"></a>Anahtarlar
 / Export:`filename`

 İsteğe bağlı. Geçerli ayarları, belirtilen dosyaya aktarır.

 / import:`filename`

 İsteğe bağlı. Belirtilen dosya ayarlarında alır.

 / Reset

 İsteğe bağlı. Geçerli ayarları sıfırlar.

## <a name="remarks"></a>Açıklamalar

Olmadan bu komutu çalıştırmak geçer açılır **içeri ve dışarı aktarma ayarları** Sihirbazı. Daha fazla bilgi için bkz: [ayarlarınızı eşitleme](../../ide/synchronized-settings-in-visual-studio.md).

## <a name="example"></a>Örnek

Aşağıdaki komutu geçerli ayarları dosyasına dışa aktarır `MyFile.vssettings`.

```shell
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"
```

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md)
- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)