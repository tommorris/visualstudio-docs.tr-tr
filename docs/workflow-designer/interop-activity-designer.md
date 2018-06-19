---
title: İş Akışı Tasarımcısı - birlikte çalışma etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Interop.UI
ms.assetid: 800a3403-ba86-41c4-8de1-c4fee9703eb1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bb9eb5e8b2dbca57d28f9d350b769b5eaa90e2b2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31979081"
---
# <a name="interop-activity-designer"></a>Birlikte çalışma etkinlik Tasarımcısı

**Birlikte çalışabilirliği** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Interop> etkinlik.

## <a name="the-interop-activity"></a>Birlikte çalışma etkinliği
 <xref:System.Activities.Statements.Interop> Etkinlik öğesinden türetilen türler yürütülmesi yönetir <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName> bir iş akışındaki.

### <a name="using-the-interop-activity-designer"></a>Birlikte çalışma etkinlik Tasarımcısı'nı kullanarak
 **Birlikte çalışabilirliği** etkinlik Tasarımcısı bulunabilir **geçiş** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesini (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 [Geçiş](../workflow-designer/migration-activity-designers.md) içeren kategori <xref:System.Activities.Statements.Interop> etkinliği yalnızca gösterir **araç** hedefliyorsa, projenizin tam .NET Framework 4.

 C# projeleri için projeye sağ tıklayarak tam .NET Framework 4 kullanmak için projeyi yeniden hedefleyebilirsiniz **Çözüm Gezgini** ve seçerek **özellikleri**. Üzerinde **uygulama** sekmesine **NET Framework 4** seçeneğini **hedef framework**. Seçin **Evet** düğmesini **hedef çerçevesini değiştirebilir** bu değişikliği onaylamanızı isteyen görüntüler iletişim.

 VB projeleri için tam .NET Framework 4 ' nde projeye sağ tıklayarak kullanmak için projeyi yeniden hedefleyebilirsiniz **Çözüm Gezgini** ve seçerek **özellikleri**. Üzerinde **derleme** sekmesini tıklatın, **Gelişmiş derleme seçenekleri** düğmesi. Seçin **.Net Framework 4** gelen **hedef framework listesi** ve ardından **Tamam**. Tıklatın **Evet** düğmesini **hedef çerçevesini değiştirebilir** bu değişikliği onaylamanızı isteyen görüntüler iletişim.

 **Birlikte çalışabilirliği** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir olduğunda, örneğin olarak içinde açın iş akışı Tasarımcısı yüzeyini bırakılan bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.Interop> varsayılan etkinlik **DisplayName** , birlikte çalışabilirlik. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **birlikte çalışabilirliği** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

 Tıklatın **göz atmak için tıklatın...**  metinde **ActivityType** kutusu, üzerinde **birlikte çalışabilirliği** etkinlik Tasarımcısı veya ortaya çıkarmak için özellik kılavuzunda **göz atma ve seçme bir .net türü** iletişim kutusu. İş akışı 3.0 veya 3.5 iş akışı etkinlikleri türleri yalnızca gösterilir (öğesinden türetilmiş yalnızca tür <xref:System.Workflow.ComponentModel.Activity>). Bir tür belirtmek için bu kutuyu kullanma hakkında daha fazla bilgi için bkz: [göz atın ve bir .NET türünü seç iletişim kutusu](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box.md) konu.

### <a name="the-interop-properties"></a>Birlikte çalışabilirlik özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.Interop> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzu veya iş akışı Tasarımcısı yüzeyinde düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.Interop> etkinlik. Birlikte çalışma varsayılandır. Görünen ad kesinlikle gerekli olmamakla birlikte, bir görünen ad kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.Interop.ActivityType%2A>|Doğru|İçinde etkinlik türünü belirtir <xref:System.Activities.Statements.Interop> etkinlik. Belirtilen bu tür öğesinden türetilmelidir <xref:System.Workflow.ComponentModel.Activity>.|

## <a name="see-also"></a>Ayrıca bkz.

- [Geçiş](../workflow-designer/migration-activity-designers.md)