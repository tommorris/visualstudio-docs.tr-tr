---
title: Visual Studio'da otomatik özelliği askıya alma
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- full solution analysis
- performance
- low-memory
ms.assetid: 572c15aa-1fd0-468c-b6be-9fa50e170914
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.workload:
- multiple
ms.openlocfilehash: d75c02bf6b817d03492a15b1f827f94eaaf3e306
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31893933"
---
# <a name="automatic-feature-suspension"></a>Otomatik özelliği askıya alma

Kullanılabilir sistem belleğini 200 MB veya daha az kalırsa, Visual Studio Kod Düzenleyicisi'nde aşağıdaki iletiyi görüntüler:

![Uyarı metni tam çözüm analizini askıya alma](../code-quality/media/fsa_alert.png)

Otomatik olarak Visual Studio bellek yetersizliği algıladığında, kararlı kalmasını sağlayacak bazı gelişmiş özellikleri askıya alır. Visual Studio'nun önceki gibi çalışmaya devam eder, ancak kendi performans düşer.

Yetersiz bellek durumu aşağıdaki eylemler gerçekleşir:

- Visual C# ve Visual Basic için tam çözüm analizini devre dışı bırakılır.

- [Çöp toplama](/dotnet/standard/garbage-collection/index) (GC) düşük gecikme süreli modu Visual C# ve Visual Basic için devre dışıdır.

- Visual Studio önbellekleri temizlenir.

## <a name="improve-visual-studio-performance"></a>Visual Studio performansı

İpuçları ve püf noktaları büyük çözümlerde veya düşük bellek koşullarla ilgilenirken Visual Studio performansını artırmak nasıl için bkz: [büyük çözümler için başarım düşünceleri](https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions).

## <a name="full-solution-analysis-suspended"></a>Tam çözüm analizini askıya alındı

Varsayılan olarak, tam çözüm analizini etkin için Visual Basic ve Visual C# için devre dışı. Ancak, bir yetersiz bellek durumu tam çözüm analizini otomatik olarak hem Visual Basic ve Visual C# için Seçenekler iletişim kutusu ayarlarına bakılmaksızın devre dışıdır. Ancak, tam çözüm analizini seçerek yeniden etkinleştirebilirsiniz **yeniden etkinleştirmek** zaman, seçerek göründüğü çubuğu bilgisi düğmesini **tam çözüm analizini etkinleştir** onay kutusunu Seçenekleri iletişim kutusunda veya Visual Studio'yu yeniden başlatmayı. Seçenekler iletişim kutusu, her zaman geçerli tam çözümü çözümleme ayarlarını gösterir. Daha fazla bilgi için bkz: [nasıl yapılır: devre dışı tam çözüm analizini etkinleştirme ve](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md).

## <a name="gc-low-latency-disabled"></a>GC düşük devre dışı Gecikmeli

GC düşük gecikme süreli modunu yeniden etkinleştirmek için Visual Studio'yu yeniden başlatın. Yazdıklarınızı GC işlemleri engellemediğinden emin olun yazmakta olduğunuz zaman varsayılan olarak, Visual Studio GC düşük gecikme süreli modu sağlar. Ancak, otomatik askıya uyarı görüntüleyecek şekilde Visual Studio bellek yetersizliği neden olursa, GC düşük gecikme süreli modu bu oturum için devre dışı bırakılır. Visual Studio'yu yeniden başlatmayı varsayılan GC davranışı yeniden etkinleştirir. Daha fazla bilgi için bkz. <xref:System.Runtime.GCLatencyMode>.

## <a name="visual-studio-caches-flushed"></a>Visual Studio önbellekleri temizlendi

Geçerli geliştirme oturumunuz devam veya Visual Studio'yu yeniden başlatın, tüm Visual Studio önbellekleri hemen boşaltılıp, ancak yeniden başlar. Temizlenen önbellekleri önbellekler için aşağıdaki özellikleri içerir:

- Tüm başvuruları Bul

- Gidin

- Using ekleme

Ayrıca, iç Visual Studio işlemleri için kullanılan önbellekleri de temizlenir.

> [!NOTE]
> Otomatik özelliği askıya uyarı çözüm başına temelinde, bir oturum başına temelinde yalnızca bir kez gerçekleşir. Bu, Visual Basic'ten Visual C# (veya tersi) geçin ve başka bir bellek yetersizliği çalıştırırsanız, başka bir otomatik özelliği askıya uyarı büyük olasılıkla alabilirsiniz anlamına gelir.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: etkinleştirme ve devre dışı tam çözüm analizini](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)
- [Atık Toplamanın Temelleri](/dotnet/standard/garbage-collection/fundamentals)
- [Büyük çözümlerde için başarım düşünceleri](https://github.com/dotnet/roslyn/wiki/Performance-considerations-for-large-solutions)