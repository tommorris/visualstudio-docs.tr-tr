---
title: ShowWebBrowser Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- view.showwebbrowser
helpviewer_keywords:
- ShowWebBrowser command
- View.ShowWebBrowser command
ms.assetid: c6a4fbd6-8e9d-45cc-8b2f-93990d065e78
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4beed25b1cdbc9f298df32743b9fec2e59fcdd8b
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704882"
---
# <a name="showwebbrowser-command"></a>ShowWebBrowser Komutu
Bir Web tarayıcı penceresinde da tümleşik geliştirme ortamı (IDE) ya da dış IDE içinde belirttiğiniz URL'yi görüntüler.

## <a name="syntax"></a>Sözdizimi

```cmd
View.ShowWebBrowser URL [/new][/ext]
```

## <a name="arguments"></a>Arguments
 `URL`

 Gerekli. Web sitesi için URL (Tekdüzen Kaynak Konum Belirleyicisi).

## <a name="switches"></a>Anahtarlar
 / Yeni

 İsteğe bağlı. Sayfaya yeni bir Web tarayıcısı örneğini görüntüleneceğini belirtir.

 /ext

 İsteğe bağlı. Sayfa IDE dışında varsayılan Web tarayıcısında görüntüleneceğini belirtir.

## <a name="remarks"></a>Açıklamalar
 Diğer **ShowWebBrowser** komutu **gidin** veya **nav**.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir Web tarayıcısında IDE dışında MSDN çevrimiçi giriş sayfasını görüntüler. Web tarayıcısı örneği zaten açıksa kullanılır; Aksi halde yeni bir örneğini başlatılır.

```cmd
>View.ShowWebBrowser http://msdn.microsoft.com /ext
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Komut Penceresi](../../ide/reference/command-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)