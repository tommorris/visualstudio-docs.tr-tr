---
title: "Visual Studio için R araçları ile R Markdown | Microsoft Docs"
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ac955b2-b6e1-4d32-b1a4-2882c93311fc
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: e3d9ee899c9ed82cacfd9466412bacfea6b8c5e8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-r-markdown-documents"></a>R Markdown belgeleri oluşturma

[R Markdown](https://rmarkdown.rstudio.com/) yüksek kaliteli belgeleri, raporları, sunuları ve panolar analiz R etkinleştiren bir belge biçimidir.

R araçları için Visual Studio (RTVS) bir R Markdown öğe şablonu, düzenleyici desteği (R kodu Düzenleyicisi içinde için de dahil olmak üzere IntelliSense) ve dosya oluşturma özellikleri sağlar.

R Markdown kullanmak için:

1. Visual Studio’yu kapatın.
1. (Yalnızca bir kez) Yükleme `pandoc` gelen [pandoc.org](http://pandoc.org/installing.html).
1. Pandoc yüklemesini seçmeniz gerekir Visual Studio'yu yeniden başlatın.
1. Yükleme `knitr` ve `rmarkdown` yapmak için paketler [etkileşimli pencere](interactive-repl.md):

    ```R
    install.packages("knitr")
    install.packages("rmarkdown")

    ```
1. Kullanarak yeni bir R Markdown dosyası oluşturun **Dosya > Yeni** menü komutu ve seçerek **R Markdown** listeden ya da Çözüm Gezgini'nde projenize sağ ve seçerek **R ekleme Markdown** (veya **Ekle > Yeni öğe...**  ve seçerek **R Markdown** listeden).

1. Yeni dosya varsayılan içeriğini aşağıdaki gibidir:

    ~~~markdown
    ---
    title: "Untitled"
    output: html_document
    ---
    
    This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and Microsoft Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.
    
    When you click the **R Tools | Publish | Preview** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:
    
    ```{r}
    summary(cars)
    ```
    
    You can also embed plots, for example:
    
    ```{r, echo=FALSE}
    plot(cars)
    ```
    
    Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
    
    ~~~

1. Düzenleme sırasında herhangi bir zamanda Düzenleyicisi ve seçin, sağ **Önizleme**, HTML, PDF ve Microsoft Word seçeneği vardır. Bu Önizlemesi'nden dosyayı seçtiğiniz biçimi için uygun şekilde kaydedebilirsiniz.
