---
title: Bul komutu kutusunu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.findcommandbox
helpviewer_keywords: Find/Command box
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8fa54e65ed581d547d7e4a0c6c5d1c1e0908c0ca
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="findcommand-box"></a>Bul/Komut kutusu

Aramak için metin ve Visual Studio komutları çalıştırmak **Bul/komut** kutusu. **Bul/komut** kutusu araç çubuğu denetimi olarak hala kullanılabilir, ancak artık varsayılan olarak görünür. Görüntüleyebileceğiniz **Bul/komut** seçerek kutusunu **Düğme Ekle veya Kaldır** üzerinde **standart** araç çubuğu ve ardından seçme **Bul**.

Çalıştırmak için bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komutu, büyüktür (>) işaretiyle yazdığınızdan.

**Bul/komut** kutusuna girilen son 20 öğeleri korur ve bir aşağı açılan listede görüntüler. Ok tuşları seçerek listeyi gidebilirsiniz.

![&#47;Bul; Komut kutusu](../ide/media/findcommandbox.png "FindCommandBox")

## <a name="searching-for-text"></a>Metin arama

Varsayılan olarak metinde belirttiğinizde, **Bul/komut** kutusuna ve ardından **Enter** anahtar, Visual Studio belirtilenseçeneklerinikullanarakgeçerlibelgeveyaaraçpenceresiarar**Dosyalarda Bul** iletişim kutusu. Daha fazla bilgi için bkz: [bulma ve değiştirme metnini](../ide/finding-and-replacing-text.md).

## <a name="entering-commands"></a>Komutları girme

Kullanılacak **Bul/komut** tek bir sorun için kutusunu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komutunu veya metin arama yerine, diğer ad komutu büyüktür (>) bir simge ile yazdığınızdan. Örneğin:

```
>File.NewFile c:\temp\MyFile /t:"General\Text File"
```

Alternatif olarak, girin ve tek veya birden çok komutları çalıştırmak için komut penceresini kullanabilirsiniz. Bazı komutlar veya diğer adlar girilen ve tek başına yürütülebilir; Başkalarının kendi sözdizimi değişkenlerinde gerekli sahip. Bağımsız değişkenleri sahip komutları bir listesi için bkz: [Visual Studio komutları](../ide/reference/visual-studio-commands.md).

## <a name="escape-characters"></a>Çıkış karakterleri

Aşağıdaki tam anlamıyla yerine bir denetim karakteri olarak yorumlanır hemen bir şapka (^) karakteri komutunda karakter anlamına gelir. Bu anahtar adları dışında bir parametre veya anahtar değer düz tırnak işaretleri ("), boşluk, başında bir eğik çizgi, belirliyorsanız düzeltme işaretleri veya başka bir değişmez değer karakterler katıştırmak için kullanılabilir. Örneğin:

```
>Edit.Find ^^t /regex
```

İç veya dış tırnak işaretleri olup bir şapka aynı çalışır. Bir şapka satırında son karakter ise, yoksayılır.

## <a name="see-also"></a>Ayrıca bkz.

[Komut Penceresi](../ide/reference/command-window.md)  
[Metin Bulma ve Değiştirme](../ide/finding-and-replacing-text.md)