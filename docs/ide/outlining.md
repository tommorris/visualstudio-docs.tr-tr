---
title: "Anahat oluşturma | Microsoft Docs"
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
ms.assetid: d1476758-9d35-4d74-b63c-310661932ecd
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cc1b41f0b1095876129a9be451e5a1ff774c8dc5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="outlining"></a>Anahat Oluşturma
Böylece bir artı işareti (+) altında görünür bir bölge kodu daraltarak biraz kod görünümünden gizlemek seçebilirsiniz. Daraltılmış bölge artı işaretine tıklayarak genişletin. (Veya basabilirsiniz CTRL + M + M bir bölge daraltmak ve CTRL + M + M yeniden genişletmek için.) Anahat bölge satırıyla kodunun sol yalnızca görünür anahat Kenar çubuğunda bölgede çift tıklayarak da daraltabilirsiniz. Daraltılmış bölgesini üzerine geldiğinizde, araç ipucu olarak daraltılmış bir bölge içeriğini görebilirsiniz.  
  
 Kenar boşluğu fareyle üzerine geldiğinizde anahat kenar boşluğu bölgelerde da vurgulanmıştır. Renk vurgulama varsayılan bazı renk yapılandırmalarda yerine soluk görünebilir. İçinde değiştirebileceğiniz **Araçlar/Seçenekler/ortamı/yazı tipleri ve renkler/Collapsible bölge**.  
  
 Anahatları belirlenmiş kodda çalışırken, istediğiniz çalışma yapılır ve diğer bölümleri taşıma bunları Daralt bölümleri genişletebilirsiniz. Sahip olmasını istiyor musunuz anahat oluşturma görüntülenen, kullanabileceğiniz **durdurmak anahat oluşturma** temel kodunuzu etkilemeden anahat bilgileri kaldırmak için komutu.  
  
 **Geri** ve **Yinele** komutlarını **Düzenle** menü bu eylemleri etkiler. **Kopya**, **Kes**, **Yapıştır**, ve sürükle ve bırak işlemleri anahat bilgi ancak durumunda daraltılabilir bölgenin korur. Örneğin, daraltılıp, bölge kopyaladığınızda **Yapıştır** işlemi genişletilmiş bir bölge olarak kopyalanan metni yapıştırmak.  
  
> [!CAUTION]
>  Anahatları belirlenmiş bir bölgeyi değiştirdiğinizde, anahat oluşturma kaybolmuş olabilir. Örneğin, silme veya bulma ve değiştirme işlemleri bölge sonuna silebilir.  
  
 Aşağıdaki komutları bulunabilir **Düzenle/anahat** alt.  
  
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