---
title: Visual Studio yavaşsa performansı
ms.date: 04/11/2018
ms.topic: conceptual
helpviewer_keywords:
- performance [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.performancecenter
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 0ce1f0e8b7ab522cf9272918a794d61e09cd243d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="optimize-visual-studio-performance"></a>Visual Studio performansı en iyi duruma getirme

Bu makalede, Visual Studio yavaş çalışıyorsa bulursanız denemek için bazı öneriler sağlar. Bir göz atalım [Visual Studio performans ipuçları ve püf noktaları](../ide/visual-studio-performance-tips-and-tricks.md) performansı konusunda daha fazla öneri için.

## <a name="upgrade-to-visual-studio-2017-version-156-or-later"></a>15,6 Visual Studio 2017 sürümüne yükseltme veya üzeri

Visual Studio 2015 kullanıyorsanız, indirme [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) ücretsiz geliştirilmiş performansını denetlemek için. Çözümleri iki ila üç kat daha hızlı Visual Studio 2017 ' diğer alanlarda performans geliştirmeleri ile çok yükleyin. Herhangi bir şey çalışırken tarafından kaybetmemek için visual Studio 2017 yan yana Visual Studio 2015 ile uyumludur.

Visual Studio 2017 kullanıyorsanız, 15.6 veya sonraki sürümü çalıştırdığınızdan emin olun. Veri çözümleri iki veya üç kez sürüm 15,6 daha hızlı yük olduğunu gösterir. Karşıdan [burada](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).

## <a name="extensions-and-tool-windows"></a>Uzantılar ve araç pencereleri

Visual Studio yavaşlamadan yüklü uzantıları olabilir. Performansı artırmak için uzantılarını yönetme hakkında daha fazla yardım için bkz: [performansını artırmak için uzantı ayarları değiştir](../ide/optimize-visual-studio-startup-time.md#extensions).

Benzer şekilde, Visual Studio yavaşlamadan aracı windows olabilir. Araç pencereleri yönetme hakkında daha fazla yardım için bkz: [performansını artırmak için araç penceresi ayarlarını değiştir](../ide/optimize-visual-studio-startup-time.md#tool-windows).

## <a name="hardware"></a>Donanım

Donanımınızın yükseltme hakkında düşünüyorsanız, katı hal sürücüsü (SSD) daha fazla performans ek RAM veya daha hızlı bir CPU'ya daha etkisi.

Bir SSD eklerseniz, en iyi performans için bir sabit disk sürücüsü (HDD) aksine bu sürücüyü Windows yükleyin. Visual Studio çözümünüzü sürücü konumunu kadar önemli görünmüyor.

Ayrıca, çözümünüzün bir USB sürücüsünden çalıştırmayın. HDD ya da SSD kopyalayın.

## <a name="help-us-improve"></a>İyileştirmemize yardımcı olun

Görüşleriniz hizmetlerimizi geliştirmemize yardımcı olur. Kullanım **bir sorun bildirmek** "izleme kaydı" ve bize göndermek için özellik. Geri bildirim simgesini seçin **Hızlı Başlat**, ya da seçin **yardımcı** > **geri bildirim gönder** > **ilgilibirsorunraporu** menü çubuğundan. Daha fazla bilgi için bkz: [Visual Studio 2017 ile ilgili bir sorun bildirme](../ide/how-to-report-a-problem-with-visual-studio-2017.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Performans İpuçları ve püf noktaları](../ide/visual-studio-performance-tips-and-tricks.md)
- [Visual Studio günlüğü - Visual Studio 2017 sürüm 15,6 daha hızlı yük çözümleri](https://blogs.msdn.microsoft.com/visualstudio/2018/04/04/load-solutions-faster-with-visual-studio-2017-version-15-6/)
