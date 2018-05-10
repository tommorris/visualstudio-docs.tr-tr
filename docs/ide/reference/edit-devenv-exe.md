---
title: -Düzenleme (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv swtich
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22c5aeffae35a4202577cf8065b76b1968616355
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
Mevcut bir örneğini belirtilen dosyayı açar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="syntax"></a>Sözdizimi

```cmd
Devenv /edit [file1[ file2]]
```

## <a name="arguments"></a>Arguments
 `file1`

 İsteğe bağlı. Mevcut bir örneği açmak için dosyaya [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Hiçbir örneği varsa [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yoksa, yeni bir örneğini bir Basitleştirilmiş pencere düzenini ile oluşturulur ve `file1` yeni örneğinde açılır.

 `file2`

 İsteğe bağlı. Mevcut örneğinde açmak için bir veya daha fazla ek dosyalar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="remarks"></a>Açıklamalar
 Hiçbir dosya belirtilir ve mevcut bir örneği var. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], var olan örneğinin [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] odağı alır. Hiçbir dosya belirtilir ve hiçbir mevcut örneği [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], yeni bir örneğini [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Basitleştirilmiş pencere düzenini ile oluşturulur.

 Varsa mevcut örneği [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kalıcı, örneğin durumunda, [Seçenekler iletişim kutusu](../../ide/reference/options-dialog-box-visual-studio.md) açık, dosya mevcut açık örnek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kalıcı durumdan çıkar.

## <a name="example"></a>Örnek
 Bu örnek dosyayı açar `MyFile.cs` varolan örneğindeki [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] veya yeni bir örneğini içinde dosya açılır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bir zaten mevcut değilse.

```cmd
devenv /edit MyFile.cs
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)