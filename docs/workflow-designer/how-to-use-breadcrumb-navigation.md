---
title: "Nasıl yapılır: içerik haritası Gezinti kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4a688056-37dc-406a-9071-be2141e192fe
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 95e79ab384c6311aa17f2592b514d62b899b8b6f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-breadcrumb-navigation"></a>Nasıl yapılır: içerik haritası Gezinti kullanın
Görüntülenen etkinlikler kümesini değiştirmek için üç ana yolu [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]:  
  
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
    >  Tüm etkinlikleri yerinde genişletilebilir. Bir etkinlik yerinde genişletildiğinde iki durumda olan: üst etkinliğin yerinde genişletilecek alt izin vermez, (örneğin, bir akış etkinlikleri yerinde genişletilemiyor), veya etkinlik Tasarımcısı kendisine izin verme yerinde genişletilmesi. Dahil etkinlik tasarımcıları hiçbiri rağmen [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ikinci davranışa sahiptir, bazı özel etkinlikleri bu davranışı sergiler.  
  
### <a name="expanding-all-or-collapsing-all-activities"></a>Tüm genişleterek veya daraltarak tüm etkinlikler  
  
1.  Kullanım **Tümünü Genişlet** ve **Daralt tüm** genişletmek veya geçerli içerik haritası kökü altındaki etkinliklerin tümünü daraltmak için kullanıcı arabiriminde düğmeler. Tümünü Genişlet ve Tümünü Daralt Not genel durumlarını aynıdır. Tıklattığınız kadar zaman içerik haritası gezinme, tüm genişletme kullanarak Kök etkinlik değiştirmek veya tüm durum Daralt devam yani **geri**.  
  
2.  Tüm genişletme uygulamış olan veya tüm durum Daralt sonra tıklayabilirsiniz **geri** her etkinlik için daha önce uygulanan durumu bakarak için geri dönmek için görünür düğmesi.  
  
    > [!WARNING]
    >  Bir etkinlik, gibi <xref:System.Activities.Statements.Flowchart>, ettikten dışında bir yerde genişletin, işlevselliği ilişkili **Tümünü Genişlet** ve **Tümünü Daralt** düğmeleri devre dışı bırakılmış **akış çizelgesi**  Tasarımcısı. [!INCLUDE[crabout](../test/includes/crabout_md.md)]**akış çizelgesi** Tasarımcı, bkz: [akış çizelgesi](../workflow-designer/flowchart-activity-designer.md) konu.  
  
    > [!WARNING]
    >  Tümünü Genişlet de bir özel bir etkisi **anahtar** ve **TryCatch** etkinlik tasarımcıları. Tıkladığınızda **Tümünü Genişlet**, tüm anahtar durumlarda ve tüm try/catch/finally blokları görüntülenir. Tıklatarak **geri** veya **Tümünü Daralt** bu tasarımcıları içinden tıklayabilirsiniz varsayılan durumlarına için bir bireysel çalışması/içindekileri görüntülemek için bloğu döndüren.