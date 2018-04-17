---
title: 'Nasıl yapılır: içerik haritası Gezinti kullanın | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4a688056-37dc-406a-9071-be2141e192fe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 97c88a8c47bfaa2e1ccd135baec95f19a49c4e5a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-breadcrumb-navigation"></a>Nasıl yapılır: içerik haritası Gezinti kullanın

Windows iş akışı Tasarımcısı'nda görüntülenen etkinlikler kümesini değiştirmek için üç ana yolu vardır:

1.  Bir alt etkinlik incelemek için çift tıklayın.

2.  Bir üst etkinliğe gitmek için içerik haritası çubuğunda bir düğmeyi tıklatın.

3.  Genişlet veya daralt yerinde etkinlikler.

### <a name="using-breadcrumb-navigation"></a>İçerik haritası Gezinti kullanma

1.  Bir etkinliğin çift [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Kök etkinlik değişiklik için tıklatılan etkinliği. Tıklatılan etkinlik sonra tam olarak-kök dizininde genişletilir ve alt öğelerinden içerik haritası çubuğunda gösterilir. Buna bazen içinde veya dışında bir etkinlik ayrıntılara denir.

2.  Geçerli Kök etkinlik üst için gitmek için içerik haritası çubuğunu etkinliğinde'ı tıklatın.

### <a name="expanding-or-collapsing-an-activity-in-place"></a>Genişleterek veya daraltarak yerinde bir etkinlik

1.  Bir etkinlikte köşeli çift tıklatarak genişletir veya etkinlik yerinde daraltır.

2.  Genişletme durumu durumunu düğmesine tıklayarak değiştirildiğinde, genişletme yeni durumu XAML'de kaydedilir.

    > [!WARNING]
    > Tüm etkinlikleri yerinde genişletilebilir. Bir etkinlik yerinde genişletildiğinde iki durumda olan: üst etkinliğin yerinde genişletilecek alt izin vermez, (örneğin, bir akış etkinlikleri yerinde genişletilemiyor), veya etkinlik Tasarımcısı kendisine izin verme yerinde genişletilmesi. Dahil etkinlik tasarımcıları hiçbiri rağmen [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ikinci davranışa sahiptir, bazı özel etkinlikleri bu davranışı sergiler.

### <a name="expanding-all-or-collapsing-all-activities"></a>Tüm genişleterek veya daraltarak tüm etkinlikler

1.  Kullanım **Tümünü Genişlet** ve **Daralt tüm** genişletmek veya geçerli içerik haritası kökü altındaki etkinliklerin tümünü daraltmak için kullanıcı arabiriminde düğmeler. Tümünü Genişlet ve Tümünü Daralt Not genel durumlarını aynıdır. Tıklattığınız kadar zaman içerik haritası gezinme, tüm genişletme kullanarak Kök etkinlik değiştirmek veya tüm durum Daralt devam yani **geri**.

2.  Tüm genişletme uygulamış olan veya tüm durum Daralt sonra tıklayabilirsiniz **geri** her etkinlik için daha önce uygulanan durumu bakarak için geri dönmek için görünür düğmesi.

    > [!WARNING]
    > Bir etkinlik, gibi <xref:System.Activities.Statements.Flowchart>, ettikten dışında bir yerde genişletin, işlevselliği ilişkili **Tümünü Genişlet** ve **Tümünü Daralt** düğmeleri devre dışı bırakılmış **akış çizelgesi**  Tasarımcısı. Hakkında daha fazla bilgi için **akış çizelgesi** Tasarımcı, bkz: [akış çizelgesi](../workflow-designer/flowchart-activity-designer.md) konu.

    > [!WARNING]
    > Tümünü Genişlet de bir özel bir etkisi **anahtar** ve **TryCatch** etkinlik tasarımcıları. Tıkladığınızda **Tümünü Genişlet**, tüm anahtar durumlarda ve tüm try/catch/finally blokları görüntülenir. Tıklatarak **geri** veya **Tümünü Daralt** bu tasarımcıları içinden tıklayabilirsiniz varsayılan durumlarına için bir bireysel çalışması/içindekileri görüntülemek için bloğu döndüren.