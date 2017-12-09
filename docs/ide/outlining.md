---
title: "Visual Studio'da kodu bölgelerinin genişletme ve daraltma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- outlining
- Visual Studio, expand/collapse code
- Visual Studio, outlining
- expand/collapse code
- code [Visual Studio], outlining
- code [Visual Studio], hiding
- outlining code
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a3c6d848821495b5db069b4343ca5c596a064422
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="outlining"></a>Anahat Oluşturma

Böylece bir artı işareti (+) altında görünür bir bölge kodu daraltarak biraz kod görünümünden gizlemek seçebilirsiniz. Daraltılmış bölge artı işaretine tıklayarak genişletin. Klavye kullanıcısıysanız seçebileceğiniz **Ctrl** + **M** + **M** daraltın ve genişletin. Anahat bölge satırıyla kodunun sol yalnızca görünür anahat Kenar çubuğunda bölgede çift tıklayarak da daraltabilirsiniz. Daraltılmış bölgesini üzerine geldiğinizde, araç ipucu olarak daraltılmış bir bölge içeriğini görebilirsiniz.

Kenar boşluğu fareyle üzerine geldiğinizde anahat kenar boşluğu bölgelerde da vurgulanmıştır. Renk vurgulama varsayılan bazı renk yapılandırmalarda yerine soluk görünebilir. İçinde değiştirebileceğiniz **aracı**, **seçenekleri**, **ortam**, **yazı tiplerini ve renkleri**, **daraltılabilir bölge**.

Anahatları belirlenmiş kodda çalışırken, istediğiniz çalışma yapılır ve diğer bölümleri taşıma bunları Daralt bölümleri genişletebilirsiniz. Sahip olmasını istiyor musunuz anahat oluşturma görüntülenen, kullanabileceğiniz **durdurmak anahat oluşturma** temel kodunuzu etkilemeden anahat bilgileri kaldırmak için komutu.

**Geri** ve **Yinele** komutlarını **Düzenle** menü bu eylemleri etkiler. **Kopya**, **Kes**, **Yapıştır**, ve sürükle ve bırak işlemleri anahat bilgi ancak durumunda daraltılabilir bölgenin korur. Örneğin, daraltılıp, bölge kopyaladığınızda **Yapıştır** işlemi genişletilmiş bir bölge olarak kopyalanan metni yapıştırmak.

> [!CAUTION]
> Anahatları belirlenmiş bir bölgeyi değiştirdiğinizde, anahat oluşturma kaybolmuş olabilir. Örneğin, silme veya bulma ve değiştirme işlemleri bölge sonuna silebilir.

Aşağıdaki komutları bulunabilir **Düzenle**, **anahat** alt.

|||
|-|-|
|Seçimi Gizle|(CTRL + M, CTRL + H) - seçili bir normalde örneğin anahat oluşturma için kullanılabilir olmayacaktır kod bloğunu daraltır bir `if` bloğu. Özel bölge kaldırmak için kullanın **gizleme geçerli Durdur** (veya CTRL + M, CTRL + U). Visual Basic'te kullanılamaz.|  
|İki durumlu genişletme anahat oluşturma|-İç içe geçmiş bir daraltılmış bölümü imleci gerektiği zaman bölüm anahat oluşturma en içteki geçerli gizli veya genişletilmiş durumunu tersine çevirir.|  
|Tüm anahat oluşturma Değiştir|(CTRL + M, CTRL + L) - aynı tüm bölgelere daraltılmış veya genişletilmiş durumuna ayarlar. Bazı bölgelerde genişletilir ve bazı daraltılmış, ardından daraltılmış bölgeler genişletilmiş.|  
|Anahat oluşturma Durdur|(CTRL + M, CTRL + P) - tüm belgeyi tüm anahat bilgilerini kaldırır.|  
|Geçerli gizleme Durdur|(CTRL + M, CTRL + U) - şu anda seçili kullanıcı tanımlı bölgede anahat bilgilerini kaldırır. Visual Basic'te kullanılamaz.|  
|Tanımları Daralt|(CTRL + M, CTRL + O) - tüm türleri üyeleri daraltır.|  
|Daraltma engelle:\<mantıksal sınır >|(Visual C++) Ekleme noktasını içeren işlevi bir bölgede daraltır. Örneğin, ekleme noktasını bir döngü içinde yer alıyorsa, döngü gizlenir.|  
|Tümünü Daralt: \<mantıksal yapıları >|(Visual C++) İşlevin içindeki tüm yapıları daraltır.|  

Visual Studio SDK'sı, genişletmek veya daraltmak için istediğiniz metin bölgeleri tanımlamak için de kullanabilirsiniz. Bkz: [izlenecek yol: anahat oluşturma](../extensibility/walkthrough-outlining.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kod Düzenleyicisi'nde yazma](../ide/writing-code-in-the-code-and-text-editor.md)