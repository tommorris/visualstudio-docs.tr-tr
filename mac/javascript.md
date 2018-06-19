---
title: JavaScript
description: Mac için Visual Studio'da Javascript desteği hakkında bilgi
author: asb3993
ms.author: amburns
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 61432695-5B12-4257-B250-48D37EED106D
ms.openlocfilehash: b24591053162603ed3089c0868d215a101688f7e
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33887051"
---
# <a name="javascript-support"></a>JavaScript desteği

Mac için Visual Studio, sözdizimi vurgulama, kod biçimlendirme ve IntelliSense Javascript ve Typescript için destek sağlar. 

![typescript Düzenleyicisi desteği](https://msdnshared.blob.core.windows.net/media/2018/03/TypeScript-editor.gif)

JavaScript yazma hakkında daha fazla bilgi için bkz: [Javascript kodu yazma](https://docs.microsoft.com/scripting/javascript/writing-javascript-code) kılavuzları.

## <a name="adding-a-javascript-file"></a>Bir JavaScript dosyası ekleme

JavaScript dosyaları çoğunlukla eklenir ASP.NET Core projeler **yeni dosya** iletişim. Bir javascript dosyası eklemek için projeye sağ tıklayın ve Git **Ekle > yeni dosya**: 

![Projeye yeni dosyaları ekleme](media/javascript-image1.png)

Yeni dosya iletişim kutusundan seçin **Web > boş JS dosya** veya **Web > Typescript dosya**. Bir ad verin ve ardından **yeni**:

![Şablondan Yeni bir typescript dosyası oluşturma](media/javascript-image2.png)

## <a name="intellisense"></a>IntelliSense

Mac kullanımlar için Visual Studio [Javascript dil hizmetinin](https://docs.microsoft.com/en-us/visualstudio/ide/javascript-intellisense) IntelliSense sağlamak için akıllı kod tamamlama, parametre bilgisi ve üye listelerini kodu yazarken olmasını sağlar.

Tür çıkarımı, JSDoc veya Typescript Mac için Visual Studio'da JavaScript IntelliSense temel alabilir bildirimi.

- **Tür çıkarımı** – bir nesne türünü çevresindeki kod bağlamdan dahil edilir. Daha fazla bilgi için Visual Studio'nun bölümüne bakın [IntelliSense temel tür çıkarımı](https://docs.microsoft.com/visualstudio/ide/javascript-intellisense#intellisense-based-on-type-inference).
- **JSDoc** – ne zaman tür çıkarımı sunmaz doğru türde bilgileri zamanlar. Bu durumlarda, tür bilgisi açıkça göre sağlanabilir [JSDoc](http://usejsdoc.org/about-getting-started.html) ek açıklamaları. Daha fazla bilgi için Visual Studio'nun bölümüne bakın [IntelliSense dayalı JSDoc üzerinde](https://docs.microsoft.com/visualstudio/ide/javascript-intellisense#intellisense-based-on-jsdoc)
- **TypeScript bildirimi dosyalarını** – `.d.ts` dosyaları için Javascript IntelliSense değerlerini sağlamak için kullanılır. Bu dosyada bildirilen türleri JSDoc açıklamaları türleri olarak kullanılabilir. Daha fazla bilgi için Visual Studio'nun bölümüne bakın [IntelliSense dayalı TypeScript bildirimi dosyalarda](https://docs.microsoft.com/visualstudio/ide/javascript-intellisense#intellisense-based-on-typescript-declaration-files) ![typescript tanım dosyası ekleme](media/javascript-image3.png)