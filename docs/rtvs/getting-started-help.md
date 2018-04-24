---
title: R için Yardım penceresini
description: Yardım R etkileşimli Visual Studio'daki doğrudan tümleşik? Komutu.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 6153a59e1875bf7b1dd81e794e0d15a37d47c2f4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="help-in-r-tools-for-visual-studio"></a>R araçları Visual Studio için Yardım

Yardım R etkileşimli Visual Studio'daki doğrudan tümleşik için. Kullandığınız her `?` gibi komutu `?mtcars`, R belgelerindeki Yardım Visual Studio penceresinde görüntülenir:

![Visual Studio'daki Yardım](media/help-window.png)

> [!Tip]
> Visual Studio'da, diğerleri gibi Yardım penceresini düzenlenmiş ve ancak istediğiniz yerleştirildi. Bkz: [Visual Studio'da pencere düzenlerini özelleştirme](../ide/customizing-window-layouts-in-visual-studio.md).
>
> Yardım sonuçları bir tarayıcıda açmak için seçin **R Araçlar > Seçenekler** menü ve kümesi **R Yardım tarayıcı** özelliğine `External`. Bkz: [seçenekleri](options-for-r-tools-in-visual-studio.md).

Yardım aramak için kullanın `??` arama terimi tarafından izlenen komutu. Arama terimi boşluk içeriyorsa tırnak işareti kullanın:

```R
??"Motor Trend"
```

![Yardım arama sonuçları](media/help-search1.png)

Yardım penceresini ayrıca üzerinden, daha fazla R belgelerinde aramaları doğrudan gerçekleştirebilirsiniz arama giriş alanı vardır:

![Giriş alanını kullanarak Yardım arama sonuçları](media/help-search2.png)

## <a name="integrated-help-lookup"></a>Tümleşik Yardım arama

Geliştiriciler genellikle R belgelerine işlev adları, veri kümeleri ve diğer öğeler hakkında Yardım için arama yapın. R araçları için Visual Studio (RTVS) düzenleyici ve etkileşimli windows Yardım aramaları tümleştirerek işlemini kolaylaştırır.

- Otomatik tamamlama işlemi sırasında F1'e basarak alt dizeyi eşleştirmek Yardım sonuçlarının bir listesini oluşturur.
- Bir arama terimi (örneğin, bir işlev) sağ tıklayıp seçerek **Yardım** komutu bu işlev için Yardım açar. Ayrıca çağırabileceği **Yardım** herhangi bir seçimi için.

    ![Sağ tıklatma bağlam menüsü üzerinden bildirilecekse Yardım](media/help-right-click.png)

> [!Tip]
> Tümleşik Yardım bir tarayıcıda açmak için seçin **R Araçlar > Seçenekler** ve **F1 Web tarayıcısı** için `External`. Bkz: [seçenekleri](options-for-r-tools-in-visual-studio.md).

## <a name="integrated-stackoverflow-search"></a>Tümleşik StackOverflow arama

R belgelerde arama yanı sıra, geliştiriciler genellikle StackOverflow kodu yazarken arama yapın. RTVS de bu işlemi kolaylaştırır. Bir terim ya da seçimi, select sağ **için arama web** komutu (Ctrl + F1) ve Visual Studio Arama sonuçlarıyla StackOverflow için kapsamlı bir pencere açılır:

![Visual Studio'da Web arama sonuçları](media/help-web-search-results.png)

Eklenen ölçüm dize değiştirebilirsiniz `R site:stackoverflow`, ile **R Araçlar > Seçenekler > F1 Web arama dizesi** seçeneği:

![F1 Web arama dizesi seçeneği değiştirme](media/options-dialog.png)

Sonuçları bir tarayıcıda görüntülemek isterseniz, değiştirmek **F1 Web tarayıcısı** seçeneği açıklandığı gibi [seçenekleri](options-for-r-tools-in-visual-studio.md).