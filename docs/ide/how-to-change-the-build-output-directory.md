---
title: 'Nasıl yapılır: yapı çıktı dizinini değiştirme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 721b8241a3278ddbf1be3b5477e8829b7aa4447b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31942253"
---
# <a name="how-to-change-the-build-output-directory"></a>Nasıl yapılır: yapı çıktı dizinini değiştirme

Çıktı konumunu projeniz tarafından oluşturulan bir başına yapılandırma temelini (hata ayıklama, yayın veya her ikisi de) belirtebilirsiniz.

> [!NOTE]
> Varsa bir **Kurulum** projesi, bu makalenin sonundaki nota bakın.

## <a name="change-the-build-output-directory"></a>Derleme çıktı dizinini değiştirme

1.  Menü çubuğunda seçin **proje** > **\<uygulamaadı > Özellikler**. Ayrıca, proje düğümüne sağ **Çözüm Gezgini** seçip **özellikleri**.

2.  Visual Basic projesinde varsa, seçin **derleme** sekmesi. Bir C# projesi varsa, seçin **yapı** sekmesi. C++ projesi ya da bir JavaScript projesini varsa, seçin **genel** sekmesi.

3.  Yapılandırmada açılan en üstte, yapılandırmayı çıktısı seçin. dosya konumu (hata ayıklama, yayın veya tümü) değiştirmek istiyor.

     Çıkış yolu girişini bulun (**yapı çıkış yolu** Visual Basic'te **çıktı dizini** Visual C++ ' ta **çıkış yolu** JavaScript ve C#). Proje dizininin göre yeni bir derleme çıktı dizinini belirtin.

> [!NOTE]
> Kurulum projesinde **çıktı dosyası adını** kutusu yalnızca konumunu değiştirir *Setup.exe* dosya, proje dosyalarının konumu değil. Daha fazla bilgi için bkz: **derleme, yapılandırma özellikleri dağıtım projesi Özellikleri iletişim kutusu**.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme sayfası, Proje Tasarımcısı (C#)](../ide/reference/build-page-project-designer-csharp.md)
- [Genel özellik sayfası (Proje)](/cpp/ide/general-property-page-project)
- [Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)