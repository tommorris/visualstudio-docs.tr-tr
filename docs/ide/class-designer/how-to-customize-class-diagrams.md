---
title: 'Nasıl Yapılır: Sınıf Diyagramlarını Özelleştirme (Sınıf Tasarımcısı)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- class diagrams, customizing
- shapes, removing type from class diagrams
- type shapes, removing from class diagrams
- class diagrams, removing type shapes
ms.assetid: e9030aea-c77d-4cc1-b8f6-b6ca469b692d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8ed2a6112d59e5d433201a417d8d85fd6683b36d
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
# <a name="how-to-customize-class-diagrams"></a>Nasıl yapılır: sınıf diyagramlarını özelleştirme

Sınıf diyagramlarının bilgileri görüntüleme biçimini değiştirebilirsiniz. Tüm diyagramı veya tasarım yüzeyinde tek tek türleri özelleştirebilirsiniz.

Örneğin, tüm bir sınıf diyagramının yakınlaştırma seviyesini ayarlayabilir, tek tek üyelerin gruplandırılma ve sıralanma şeklini değiştirebilir, ilişkileri gizleyebilir ya da gösterebilir ve tek tek türleri ya da tür kümelerini diyagram üzerinde istediğiniz yere taşıyabilirsiniz.

> [!NOTE]
> Şekillerin diyagram üzerinde görünme biçimi özelleştirildiğinde, diyagramda temsil edilen türlerin temelini oluşturan kod değişmez.

Üyeleri içeren bölümleri gibi yazın **özellikleri** bölümünde bir sınıfta, bölmeler denir. Tek tek bölmeleri ve tür üyelerini gizleyebilir veya gösterebilirsiniz.

## <a name="zoom-in-and-out-of-the-class-diagram"></a>Sınıf diyagramını yakınlaştırma ve uzaklaştırma

1. Açın ve bir sınıf diyagramı dosyasında seçin **Sınıf Tasarımcısı**.

2. Üzerinde **Sınıf Tasarımcısı** araç tıklatın **Yakınlaştır** veya **Uzaklaştır** Tasarımcı yüzeyine yakınlaştırma düzeyini değiştirmek için düğmesi.

     veya

     Belirli bir yakınlaştırma değeri belirtin. Kullanabileceğiniz **yakınlaştırma** açılan liste veya geçerli yakınlaştırma düzeyini yazın (geçerli aralık: % %10 400 arasında).

    > [!NOTE]
    > Yakınlaştırma seviyesinin değiştirilmesi sınıf diyagramı çıktınızın ölçeğini etkilemez.

## <a name="customize-grouping-and-sorting-of-type-members"></a>Tür üyelerinin gruplandırmasını ve sıralamasını özelleştirme

1. Açın ve bir sınıf diyagramı dosyasında seçin **Sınıf Tasarımcısı**.

2. Tasarım yüzeyine boş bir alana sağ tıklayın ve fareyle **Grup üyeleri**.

3. Kullanılabilir seçeneklerden birini belirtin:

    - **Grup türü tarafından** tek tek tür üyeleri özellikleri, yöntemleri, olayları ve alanları gruplandırılmış liste halinde ayırır. Tek tek gruplar varlıklar tanımına göre değişir: Örneğin, bir sınıf için henüz hiç tanımlı olay yoksa, bu sınıf olaylar grubunu görüntülemez.

    - **Erişim grupla** tek tek tür üyeleri gruplandırılmış listesine göre üyenin üzerinde ayırır erişim değiştiricileri. Örneğin, Genel ve Özel.

    - **Alfabetik olarak sıralamak** öğeleri, bir varlığın tek alfabetik listesi olarak oluşturan gösterir. Liste artan düzende sıralanır.

## <a name="hide-compartments-on-a-type"></a>Türe göre bölmeleri gizleme

1. Açın ve bir sınıf diyagramı dosyasında seçin **Sınıf Tasarımcısı**.

2. Özelleştirmek istediğiniz türündeki üye kategori sağ tıklayın (örneğin, seçin **yöntemleri** bir sınıf düğümünde.

3. Tıklatın **Gizle bölme**.

     Seçili bölme tür kapsayıcısından kaybolur.

## <a name="hide-individual-members-on-a-type"></a>Türe göre tek tek üyeleri gizleme

1. Açın ve bir sınıf diyagramı dosyasında seçin **Sınıf Tasarımcısı**.

2. Gizlemek istediğiniz türde üyeye sağ tıklayın.

3. Tıklatın **Gizle**.

     Seçili üye tür kapsayıcısından kaybolur.

## <a name="show-hidden-compartments-and-members-on-a-type"></a>Türe göre gizli bölmeleri ve üyeleri gösterme

1. Açın ve bir sınıf diyagramı dosyasında seçin **Sınıf Tasarımcısı**.

2. Gizli bölmeyi içeren türün adına sağ tıklayın.

3. Tıklatın **tüm üyeleri Göster**.

     Tüm gizli bölmeler ve üyeler tür kapsayıcısında görünür.

## <a name="hide-relationships"></a>İlişkileri gizleme

1. Açın ve bir sınıf diyagramı dosyasında seçin **Sınıf Tasarımcısı**.

2. Gizlemek istediğiniz ilişkilendirme veya devralma çizgisine sağ tıklayın.

3. Tıklatın **Gizle** ilişkilendirme satırları ve tıklatın **devralma satırı gizlemek** devralma satırlar için.

4. Tıklatın **tüm üyeleri Göster**.

     Tüm gizli bölmeler ve üyeler tür kapsayıcısında görünür.

## <a name="show-hidden-relationships"></a>Gizli ilişkileri gösterme

1. Açın ve bir sınıf diyagramı dosyasında seçin **Sınıf Tasarımcısı**.

2. Gizli ilişkilendirmeyi veya devralmayı içeren türün adına sağ tıklayın.

 Tıklatın **tüm üyeleri Göster** ilişkilendirme satırları ve tıklatın **Göster temel sınıf** veya **türetilmiş sınıfları Göster** devralma satırlar için.

## <a name="remove-a-shape-from-a-class-diagram"></a>Sınıf diyagramından şekil kaldırma
Türün temelini oluşturan koda etkisi olmaksızın, bir tür şeklini sınıf diyagramından kaldırabilirsiniz. Tür şekillerinin bir sınıf diyagramından kaldırılması yalnızca o diyagramı etkiler: Türü tanımlayan temel kod ve türü görüntüleyen diğer diyagramlar bundan etkilenmez.

1. Sınıf diyagramında, diyagramdan kaldırmak istediğiniz tür şeklini seçin.

2. Üzerinde **Düzenle** menüsünde seçin **diyagramdan Kaldır**.

     Tür şekli ve varsa bu şekle bağlı ilişkilendirme ya da devralma çizgileri bundan böyle diyagramda görünmez.

## <a name="delete-a-type-shape-and-its-underlying-code"></a>Bir tür şeklini ve temelini oluşturan kodu silme

1. Tasarım yüzeyinde şekle sağ tıklayın.

2. Seçin **Sil kod** ve bağlam menüsünden.

     Şekil diyagramdan kaldırılır ve temelini oluşturan kod projeden silinir.

## <a name="see-also"></a>Ayrıca bkz.

- [Sınıf Diyagramları ile Çalışma](working-with-class-diagrams.md)
- [Nasıl yapılır: üye gösterimi ile ilişkilendirme gösterimi arasında değişiklik](how-to-change-between-member-notation-and-association-notation.md)
- [Nasıl yapılır: Varolan türleri görüntüleme](how-to-view-existing-types.md)
- [Türleri ve İlişkileri Görüntüleme](viewing-types-and-relationships.md)