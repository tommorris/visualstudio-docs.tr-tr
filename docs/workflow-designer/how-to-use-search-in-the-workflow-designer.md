---
title: "Nasıl yapılır: İş Akışı Tasarımcısı'nda Ara'yı kullanın"
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: f42d3115-2ed2-4941-8f1e-92dac41c30fa
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 3e8e44586f6b0f2f8aea5ab13eb27886d7b3a6e8
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757974"
---
# <a name="how-to-use-search-in-the-workflow-designer"></a>Nasıl yapılır: İş Akışı Tasarımcısı'nda Ara'yı kullanın

Daha büyük ve daha karmaşık iş akışları oluşturma kolaylaştırmak için anahtar sözcüğüyle öğeleri bulmak için iş akışı Tasarımcısı'nda arama yapabilirsiniz. Tasarımcı Değiştir desteklemiyor unutmayın.

## <a name="quick-find"></a>Hızlı Bul

Hızlı Bul Tasarımcısı'nda aşağıdaki bulur:

-   Özelliklerini <xref:System.Activities.Activity> nesneleri <xref:System.Activities.Statements.FlowNode> nesneleri <xref:System.Activities.Statements.State> nesneleri, geçişleri ve diğer özel akış denetimi öğeleri.

-   Değişkenler

-   Arguments

-   İfadeler

### <a name="use-quick-find"></a>Hızlı Bul'u kullanma

1.  İş Akışı Tasarımcısı açık basın **Ctrl + F**, ya da seçin **Düzenle** > **bulma ve değiştirme** > **Hızlı Bul'u**.

2.  Arama terimini girin **Aranan** textbox tıklatıp **Sonrakini Bul**.

3.  Arama terimi geçerli iş akışında yer alır. Aşağıdaki resimde Tasarımcısı'nda bulunuyor bir etkinlik görünen adı gösterilmektedir:

   ![İş Akışı Tasarımcısı'nda arama sonucu](../workflow-designer/media/designersearch.png)

## <a name="find-in-files"></a>Dosyalarda Bul

Dosyalarda Bul XAML dosyaları dahil olmak üzere iş akışı dosyalarında dizeleri bulur.

### <a name="use-find-in-files"></a>Dosyalarda Bul kullanın

1.  Visual Studio'da basın **Ctrl**+**Shift**+**F**, ya da seçin **Düzenle**  >   **Bulma ve değiştirme** > **dosyalarda Bul**.

2.  Arama öğesine girin **Aranan** textbox tıklatıp **Tümünü Bul**.

3.  Bulma sonucu gösterilen **Bul sonuç** görünümü. Sonuç öğeyi çift iş akışı Tasarımcısı'nda eşleşme içeren aktiviteyi gider.