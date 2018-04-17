---
title: ShowWebBrowser komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
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
ms.openlocfilehash: 1f699623d15a400b58b3b546a7eb93300385903a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="showwebbrowser-command"></a>ShowWebBrowser Komutu
Bir Web tarayıcı penceresinde da tümleşik geliştirme ortamı (IDE) ya da dış IDE içinde belirttiğiniz URL'yi görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
```  
>View.ShowWebBrowser http://msdn.microsoft.com /ext  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)