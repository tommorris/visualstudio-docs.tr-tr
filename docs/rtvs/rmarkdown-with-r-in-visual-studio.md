---
title: "Visual Studio için R araçları ile R Markdown | Microsoft Docs"
description: "Yüksek kaliteli raporları, sunuları ve panoları oluşturmak için Visual Studio'da R Markdown belgeleri oluşturma"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 982dc9a2fbcb8e6cb790ec64c07d83f02017c803
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="creating-r-markdown-documents"></a>R Markdown belgeleri oluşturma

[R Markdown](https://rmarkdown.rstudio.com/) yüksek kaliteli belgeleri, raporları, sunuları ve panolar analiz R etkinleştiren bir belge biçimidir.

R araçları için Visual Studio (RTVS) bir R Markdown öğesi şablonu sağlar, Düzenleyici (IntelliSense de dahil olmak üzere R kodu Düzenleyicisi içinde), dosya oluşturma yeteneklerini desteklemek ve Canlı Önizleme.

## <a name="using-r-markdown"></a>R Markdown kullanma

1. Visual Studio’yu kapatın.
1. (Yalnızca bir kez) Yükleme `pandoc` gelen [pandoc.org](http://pandoc.org/installing.html).
1. Pandoc yüklemesini seçmeniz gerekir Visual Studio'yu yeniden başlatın.
1. Yükleme `knitr` ve `rmarkdown` yapmak için paketler [etkileşimli pencere](interactive-repl-for-r-in-visual-studio.md):

    ```R
    install.packages("knitr")
    install.packages("rmarkdown")

    ```
1. Yeni bir R Markdown dosyası kullanarak oluşturmak **Dosya > Yeni > Dosya** menü komutu ve seçerek **R > R Markdown** listeden. Bir proje bağlamında, Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **eklemek R Markdown** (veya **Ekle > Yeni öğe...**  ve seçerek **R Markdown** listeden).

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

## <a name="previews"></a>Önizlemeler

Visual Studio 2017 15,5 ve sonraki sürümleri, Canlı Önizleme R Markdown için otomatik olarak sağlayın. Düzenleyici ve önizleme arasında otomatik eşitlemeyi etkinleştirmek için seçin **R Araçlar > Markdown > otomatik eşitleme** (Ctrl + Shift + Y). Otomatik eşitleme kullanmıyorsanız, Önizleme kullanarak yenileyebilirsiniz **R Araçlar > Markdown > yeniden R Markdown önizlemesini**.

Microsoft Word biçimleri Düzenleyicisi'nde sağ tıklayıp aşağıdakilerden birini seçerek ve HTML, PDF, dosyasında da önizleyebilirsiniz **Önizleme** komutları. Aynı komutları da kullanılabilir **R Araçlar > Markdown** menüsü. (Visual Studio'nun önceki sürümleri, bu komutları üzerinde bulunan **R Araçlar > Yayımla** menü.)

![RMarkdown Canlı Önizleme ve diğer Önizleme menü komutları](media/rmarkdown-live-preview.png)
