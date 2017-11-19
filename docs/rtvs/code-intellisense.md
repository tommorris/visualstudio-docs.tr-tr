---
title: "R kodu Visual Studio için IntelliSense | Microsoft Docs"
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d96e3677-e5ec-4e11-82a8-d914a93b1aa9
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 821f92f7a3cf0e5ca1d647890602ec17e580b36b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="intellisense"></a>IntelliSense

Visual Studio IntelliSense çağırabilirsiniz, işlevleri üyeleri nesnelerin işlev bağımsız değişkenleri hakkında daha fazla bilgi görüntüler ve [kod parçacıkları](code-snippets.md) doğrudan görünümünüzde yazarken kodu yazın. Ayrıca tamamlanabilir yazarken görüntüler ve sekme veya Enter tuşlarına sırada tamamlar (bkz [Düzenleyici Seçenekleri](code-editing.md#editor-options) için **Gelişmiş** sekmesi). IntelliSense Düzenleyicisi'nde kullanılabilir ve [etkileşimli pencere](interactive-repl.md).

![İşlev imzası gösteren IntelliSense](media/intellisense-function-signature.png) 

Bir işlev veya diğer deyimi yazarken IntelliSense otomatik tamamlama sağlar ne önceden girmiş olduğunuz tarafından menü (case-sensitively) filtre:

![IntelliSense otomatik tamamlama menüsü](media/intellisense-auto-complete-menu.png)

Sekme (veya Enter veya seçenekleri nasıl ayarlanacağını bağlı olarak alanı), tuşuna basarak açılır listede seçilen öğe ekler. Seçimi ok tuşlarını kullanarak değiştirebilirsiniz. 

IntelliSense de R nesneleri üyeleri için öneriler sağlar:
 
![Nesne üyeleri için IntelliSense önerileri](media/intellisense-auto-complete-r-objects.png)
 
ESC tuşuna basarak menüsünü tamamen kapatır. Bunu Ctrl + Ara çubuğu ile getirebilir yedekleyin.

Açılış yazarak `(` için bir işlev çağrısı kapatma ekler `)` ve daha önce gösterildiği gibi imza Yardım getirir:

![Bir işlev için IntelliSense imza Yardım](media/intellisense-function-signature.png)

Yeniden açılan ESC kapatır; işlevi imzalar için onu yeniden Ctrl + Shift + alanıyla getirebilir.

> [!Tip]
> Parametre Yardım altındaki metin engelliyorsa, Yardım metni saydam parametre yapmak için Ctrl tuşunu basılı tutun.

## <a name="intellisense-for-user-defined-functions-and-variables"></a>Kullanıcı tanımlı işlevler ve değişkenler için IntelliSense

Name parametresi tamamlama dahil olmak üzere aynı dosyada, kullanıcı tanımlı işlevler için IntelliSense geçerlidir:

![Kullanıcı tanımlı işlevler için IntelliSense](media/intellisense-same-file-functions.png)

![Kullanıcı tanımlı işlevler için IntelliSense parametre tamamlama](media/intellisense-parameter-completion.png)

IntelliSense de aynı dosya ve geçerli oturumun değişkenler için geçerlidir:

![IntelliSense değişken tamamlama](media/intellisense-variable-completion.png)

> [!Note]
> Etkileşimli penceresinde IntelliSense geçerli R oturumda yalnızca adlarını göz önünde bulundurur ve projenizin dosyalarında yok sayar.

## <a name="code-suggestions"></a>Kod önerileri

(Akıllı etiket olarak adlandırılır) bir ampul kenar boşluğunda göründüğünde, Visual Studio için yaygın olarak kullanılan bir eylem bir kısayol olduğunu önerme. Örneğin, içeren bir çizginin üzerine getirin bir `library` bir ampul görmek için düzenleyicisinde deyimi. Ampul seçme seçeneklerden görüntüler:

![Düzenleyicideki r akıllı etiketler](media/intellisense-smart-tags.png)
