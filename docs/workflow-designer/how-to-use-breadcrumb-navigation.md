---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: içerik haritası Gezinti kullanın'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 4a688056-37dc-406a-9071-be2141e192fe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 92f3e35d4182297601741bd603aa3c5a17e54d67
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975072"
---
# <a name="how-to-use-breadcrumb-navigation"></a>Nasıl yapılır: içerik haritası Gezinti kullanın

Windows iş akışı Tasarımcısı'nda görüntülenen etkinlikler kümesini değiştirmek için üç ana yolu vardır:

1.  Bir alt etkinlik incelemek için çift tıklayın.

2.  Bir üst etkinliğe gitmek için içerik haritası çubuğunda bir düğmeyi tıklatın.

3.  Genişlet veya daralt yerinde etkinlikler.

## <a name="using-breadcrumb-navigation"></a>İçerik haritası Gezinti kullanma

1.  Kök etkinlik değişiklik için tıklatılan etkinliği iş akışı Tasarımcısı'nın bir etkinliğe çift tıklayın. Tıklatılan etkinlik sonra tam olarak-kök dizininde genişletilir ve alt öğelerinden içerik haritası çubuğunda gösterilir. Buna bazen içinde veya dışında bir etkinlik ayrıntılara denir.

2.  Geçerli Kök etkinlik üst için gitmek için içerik haritası çubuğunu etkinliğinde'ı tıklatın.

## <a name="expanding-or-collapsing-an-activity-in-place"></a>Genişleterek veya daraltarak yerinde bir etkinlik

1.  Bir etkinlikte köşeli çift tıklatarak genişletir veya etkinlik yerinde daraltır.

2.  Genişletme durumu durumunu düğmesine tıklayarak değiştirildiğinde, genişletme yeni durumu XAML'de kaydedilir.

    > [!WARNING]
    > Tüm etkinlikleri yerinde genişletilebilir. Bir etkinlik yerinde genişletildiğinde iki durumda olan: üst etkinliğin yerinde genişletilecek alt izin vermez, (örneğin, bir akış etkinlikleri yerinde genişletilemiyor), veya etkinlik Tasarımcısı kendisine izin verme yerinde genişletilmesi. İş Akışı Tasarımcısı'nda bulunan etkinlik tasarımcıları hiçbiri ikinci davranışı olmakla birlikte, bazı özel etkinlikleri bu davranışı düşebilir.

## <a name="expanding-all-or-collapsing-all-activities"></a>Tüm genişleterek veya daraltarak tüm etkinlikler

1.  Kullanım **Tümünü Genişlet** ve **Daralt tüm** genişletmek veya geçerli içerik haritası kökü altındaki etkinliklerin tümünü daraltmak için kullanıcı arabiriminde düğmeler. Tümünü Genişlet ve Tümünü Daralt Not genel durumlarını aynıdır. Tıklattığınız kadar zaman içerik haritası gezinme, tüm genişletme kullanarak Kök etkinlik değiştirmek veya tüm durum Daralt devam yani **geri**.

2.  Tüm genişletme uygulamış olan veya tüm durum Daralt sonra tıklayabilirsiniz **geri** her etkinlik için daha önce uygulanan durumu bakarak için geri dönmek için görünür düğmesi.

    > [!WARNING]
    > Bir etkinlik, gibi <xref:System.Activities.Statements.Flowchart>, ettikten dışında bir yerde genişletin, işlevselliği ilişkili **Tümünü Genişlet** ve **Tümünü Daralt** düğmeleri devre dışı bırakılmış **akış çizelgesi**  Tasarımcısı. Hakkında daha fazla bilgi için **akış çizelgesi** Tasarımcı, bkz: [akış çizelgesi](../workflow-designer/flowchart-activity-designer.md) konu.

    > [!WARNING]
    > Tümünü Genişlet de bir özel bir etkisi **anahtar** ve **TryCatch** etkinlik tasarımcıları. Tıkladığınızda **Tümünü Genişlet**, tüm anahtar durumlarda ve tüm try/catch/finally blokları görüntülenir. Tıklatarak **geri** veya **Tümünü Daralt** bu tasarımcıları içinden tıklayabilirsiniz varsayılan durumlarına için bir bireysel çalışması/içindekileri görüntülemek için bloğu döndüren.