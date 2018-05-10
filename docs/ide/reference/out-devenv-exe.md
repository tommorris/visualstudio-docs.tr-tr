---
title: -(Out devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- errors [Visual Studio], builds
- Devenv, /out switch
- builds [Visual Studio], logs
- error logs [Visual Studio], command-line build errors
- error logs [Visual Studio]
- /out Devenv switch
- out Devenv switch
- builds [Visual Studio], errors
- output files, build errors
ms.assetid: 9002d8c2-36d4-451c-b489-8f01932f31f7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 623f4e8a8a2f6e275c42507aa3839106f3a1dd2f
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="out-devenvexe"></a>/Out (devenv.exe)
Depolamak ve çalıştırırken, yapı, yeniden, veya bir çözüm dağıtma hataları görüntülemek için bir dosyayı belirtir.

## <a name="syntax"></a>Sözdizimi

```cmd
devenv /out FileName
```

## <a name="arguments"></a>Arguments
 `FileName`

 Gerekli. Yürütülebilir bir dosya derlerken hataları almak için dosyanın adını ve yolunu.

## <a name="remarks"></a>Açıklamalar
 Dosya var olmayan bir dosya adı belirtilirse, otomatik olarak oluşturulur. Dosya zaten mevcutsa, sonuçları dosyasının mevcut içerikleri eklenir.

 Komut satırı derleme hataları görüntülenir **komutu** penceresini açın ve çözüm Oluşturucusu'nu görüntülemek **çıkış** penceresi. Katılımsız derlemeleri çalıştırıyorsanız ve sonuçları görmek gereken bu kullanışlı bir seçenektir.

## <a name="example"></a>Örnek
 Bu örnekte çalışan `MySolution` ve hataları dosyaya yazar `MyErrorLog.txt`.

```cmd
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /out "C:\MyErrorLog.txt"
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)
- [/ Çalıştır (devenv.exe)](../../ide/reference/run-devenv-exe.md)
- [/ Yapı (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ (Devenv.exe) dağıtma](../../ide/reference/deploy-devenv-exe.md)