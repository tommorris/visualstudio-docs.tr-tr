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
ms.assetid: c81736dd-7a26-4e11-95c8-c2a2e56d7a41
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c8bf4de0ff0dfb240f668ba3f6915268ee89e594
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="findcommand-box"></a>Bul/Komut Kutusu
Aramak için metin ve Visual Studio komutları çalıştırmak **Bul/komut** kutusu. **Bul/komut** kutusu araç çubuğu denetimi olarak hala kullanılabilir, ancak artık varsayılan olarak görünür. Görüntüleyebileceğiniz **Bul/komut** seçerek kutusunu **Düğme Ekle veya Kaldır** üzerinde **standart** araç çubuğu ve ardından seçme **Bul**.  
  
 Çalıştırmak için bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komutu, büyüktür (>) işaretiyle yazdığınızdan.  
  
 **Bul/komut** kutusuna girilen son 20 öğeleri korur ve bir aşağı açılan listede görüntüler. Ok tuşları seçerek listeyi gidebilirsiniz.  
  
 ![&#47;Bul; Komut kutusu](../ide/media/findcommandbox.png "FindCommandBox")  
Bul/Komut Kutusu  
  
## <a name="searching-for-text"></a>Metin arama  
 Varsayılan olarak metinde belirttiğinizde, **Bul/komut** kutusuna ve ardından ENTER anahtar, Visual Studio içinde belirtilen seçeneklerini kullanarak geçerli belge veya aracı penceresi arar **dosyalardaBul**iletişim kutusu. Daha fazla bilgi için bkz: [bulma ve değiştirme metnini](../ide/finding-and-replacing-text.md).  
  
## <a name="entering-commands"></a>Komutları girme  
 Kullanılacak **Bul/komut** tek bir sorun için kutusunu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komutunu veya metin arama yerine, diğer adını girin [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] büyüktür (>) simgesiyle başında komutu. Örneğin:  
  
```  
>File.NewFile c:\temp\MyFile /t:"General\Text File"  
```  
  
 Alternatif olarak, girin ve tek veya birden çok komutları çalıştırmak için komut penceresini kullanabilirsiniz. Bazı komutlar veya diğer adlar girilen ve tek başına yürütülebilir; Başkalarının kendi sözdizimi değişkenlerinde gerekli sahip. Bağımsız değişkenleri sahip komutları bir listesi için bkz: [Visual Studio komutları](../ide/reference/visual-studio-commands.md).  
  
## <a name="escape-characters"></a>Çıkış karakterleri  
 Aşağıdaki tam anlamıyla yerine bir denetim karakteri olarak yorumlanır hemen bir komut satırında bir şapka (^) karakteri karakter anlamına gelir. Bu anahtar adları dışında bir parametre veya anahtar değer düz tırnak işaretleri ("), boşluk, başında bir eğik çizgi, belirliyorsanız düzeltme işaretleri veya başka bir değişmez değer karakterler katıştırmak için kullanılabilir. Örneğin,  
  
```  
>Edit.Find ^^t /regex  
```  
  
 İç veya dış tırnak işaretleri olup bir şapka aynı çalışır. Bir şapka satırında son karakter ise, yoksayılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut penceresi](../ide/reference/command-window.md)   
 [Metin bulma ve değiştirme](../ide/finding-and-replacing-text.md)