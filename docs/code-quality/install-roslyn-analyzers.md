---
title: Visual Studio'da Roslyn çözümleyiciler yükleme | Microsoft Docs
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 0d21b0ab9c5db64c9b5874480c3735bfbb365384
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="install-net-compiler-platform-analyzers"></a>.NET derleme platformu çözümleyiciler yükleyin

Visual Studio 2017 .NET derleyici platformu çekirdek kümesini içerir (*Roslyn*) Çözümleyicileri. Bu çözümleyiciler her zaman açıktır. NuGet paketleri, veya olarak Visual Studio uzantıları ek çözümleyiciler yükleyebilirsiniz *VSIX* dosyaları.

## <a name="to-install-nuget-package-analyzers"></a>NuGet paket çözümleyiciler yüklemek için

1. [Hangi Çözümleyicisi paket sürümünü](https://github.com/dotnet/roslyn-analyzers#recommended-version-of-analyzer-packages) yüklemek için Visual Studio sürümüne.

1. Visual Studio içinde kullanarak paketi yükleyin [Paket Yöneticisi Konsolu](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console) veya [Paket Yöneticisi kullanıcı Arabirimi](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console).

   > [!NOTE]
   > Her bir Çözümleyicisi paket nuget.org sayfası yapıştırmak için komutu gösterir **Paket Yöneticisi Konsolu**. Hatta metni panoya kopyalamak için kullanışlı bir düğme vardır.
   >
   > ![Paket Yöneticisi konsol komutu gösteren NuGet.org sayfası](media/nuget-package-manager-command.png)

   Çözümleyicisi derlemeleri yüklenir ve görüntülenmesini **Çözüm Gezgini** altında **başvuruları** > **çözümleyiciler**.

   ![Çözüm Gezgini'nde çözümleyiciler düğümü](media/solution-explorer-analyzers-node.png)

## <a name="to-install-vsix-analyzers"></a>VSIX çözümleyiciler yüklemek için

1. Visual Studio'da seçin **Araçları** > **Uzantılar ve güncelleştirmeler**.

   **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.

   > [!NOTE]
   > Alternatif olarak, doğrudan uzantısını [Visual Studio Market'te](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017).

1. Genişletme **çevrimiçi** sol bölmesinde ve seçip **Visual Studio Market'te**.

1. Arama kutusuna "kod çözümlemesi" yazın ve Ara **Microsoft kod çözümleme 2017** uzantısı.

   ![Microsoft Kod Analizi uzantısı](media/extensions-and-updates-code-analysis.png)

1. Seçin **karşıdan**.

   Uzantı indirilir.

1. Seçin **Tamam** iletişim kutusunu kapatın ve ardından başlatmak için Visual Studio tüm örneklerini kapatın **VSIX yükleyici**.

   **VSIX yükleyici** iletişim kutusu açılır.

   ![Microsoft Kod Analizi için VSIX yükleyicisi](media/vsix-installer-code-analysis.png)

1. Seçin **Değiştir** yüklemeyi başlatmak için.

1. Bir veya iki dakika sonra yükleme işlemini tamamlar. Seçin **Kapat**.

1. Visual Studio'yu yeniden açın.

Yüklenen, seçim olup olmadığını ' uzantısı denetlemek istiyorsanız **Araçları** > **Uzantılar ve güncelleştirmeler**. İçinde **Uzantılar ve güncelleştirmeler** iletişim kutusunda **yüklü** solda, kategori ve ada göre uzantısı için arama yapın.

## <a name="next-steps"></a>Sonraki adımlar

- [Visual Studio'da Roslyn çözümleyiciler kullanın](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da Roslyn çözümleyiciler genel bakış](../code-quality/roslyn-analyzers-overview.md)