---
title: R kodu için IntelliSense
description: R kodu yazarken visual Studio IntelliSense işlevleri, nesne üyeleri, kod parçacıkları ve tamamlamalar hakkındaki bilgileri görüntüler.
ms.custom: ''
ms.date: 01/24/2018
ms.technology:
- devlang-r
dev_langs:
- R
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: a5ba810cc1dc988a72de1e9e596578bca1ae85e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="intellisense"></a>IntelliSense

Visual Studio IntelliSense çağırabilirsiniz, işlevleri üyeleri nesnelerin işlev bağımsız değişkenleri hakkında daha fazla bilgi görüntüler ve [kod parçacıkları](code-snippets-for-r.md) doğrudan görünümünüzde yazarken kodu yazın. Ayrıca tamamlanabilir yazarken görüntüler ve sekme veya Enter tuşlarına sırada tamamlar (bkz [Düzenleyici Seçenekleri](editing-r-code-in-visual-studio.md#editor-options) için **Gelişmiş** sekmesi). IntelliSense Düzenleyicisi'nde kullanılabilir ve [etkileşimli pencere](interactive-repl-for-r-in-visual-studio.md).

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
