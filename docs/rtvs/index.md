---
title: "Visual Studio için R araçları | Microsoft Docs"
description: "R araçları için Visual Studio (RTVS) IntelliSense, hata ayıklama ve uzak çalışma alanları dahil olmak üzere birçok dil özellikleri sağlayan ücretsiz, açık kaynaklı bir uzantısıdır."
ms.custom: 
ms.date: 11/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
ms.tgt_pltfrm: 
ms.topic: hero-article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 762b56336fa790d57ffa38510aa319e744b5959c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="working-with-r-in-visual-studio"></a>Visual Studio'da R ile çalışma

R bir yüksek düzeyde genişletilebilir dil ve ortam istatistiksel bilgi işlem ve grafik için ' dir. GNU Genel Kamu Lisansı altında ücretsiz dağıtılmış, güçlü topluluk desteği özgürlüğüne ve kendi yeteneği matematiksel simgeler ve formül dahil olmak üzere yayın kaliteli çizimler oluşturmak bilinen. R hakkında daha fazla bilgiyi [r project.org](https://www.r-project.org/about.html) ve [R giriş](https://cran.r-project.org/doc/manuals/r-release/R-intro.html).

R araçları için Visual Studio (RTVS) olan bir ücretsiz, [açık kaynak](https://github.com/microsoft/RTVS) uzantısı için Visual Studio 2017 ve Visual Studio 2015 güncelleştirme 3 (veya üstü), yayımlanan MIT lisansı altında. (İkinci bir açık kaynak bileşenini adlı [RHost](https://github.com/microsoft/R-Host), hangi R yorumlayıcı ikili dosyaları, bağlantılar altında GNU genel lisans V2 yayımlanır.)

> [!Note]
> RTVS şu anda yalnızca Windows Visual Studio ve değil Visual Studio Mac için desteklenir

Visual Studio'da R deneyimi için:

- [R Araçları'nı yükleme](installing-r-tools-for-visual-studio.md).
- İzleyin [Başlarken](getting-started-with-r.md) Kılavuzu, yanı sıra [örnekleri](getting-started-samples.md) ve [Yardımı alma](getting-started-help.md) makaleleri.

Ardından R güvenlikle ilgili özellikler ve bunun yanı sıra, Visual Studio'nun kendisi genel özellikleri hakkında daha fazla bilgi için aşağıdaki bağlantıları izleyin.

| Özellik | Açıklama | Genel Visual Studio belgeleri | 
| --- | --- | --- |
| [Visual Studio project system](r-projects-in-visual-studio.md) | Düzenleyebilir ve kullanışlı bir yapı ilişkili dosyaları yönetmek ve R kodu, R belgeleri, R Markdown, SQL sorguları ve saklı yordamlar gibi öğeleri için yararlı şablonlar yararlanın. Ayrıca keyfini [Paket Yöneticisi](r-package-manager-in-visual-studio.md) ve [SQL Server Integration](integrating-sql-server-with-r.md).  | [Visual Studio’da Çözümler ve Projeler](../ide/solutions-and-projects-in-visual-studio.md) |
| [Çalışma alanı](r-workspaces-in-visual-studio.md) | RTVS R kodu daha küçük veri kümeleri ile yerel olarak geliştirmenize olanak tanıyan yerel ve uzak çalışma alanları için bağ sonra kolayca daha güçlü bulut tabanlı bilgisayarlarda çok daha büyük veri kümeleriyle kodu çalıştırın. | yok |
| [R Araçlar Seçenekler](options-for-r-tools-in-visual-studio.md) | RTVS çeşitli yönlerini denetler. | [Seçenekler iletişim kutusu](../ide/reference/options-dialog-box-visual-studio.md) |
| [Zengin düzenleme, IntelliSense ve kod parçacıkları](editing-r-code-in-visual-studio.md) | Söz dizimi renklendirme, içeren [IntelliSense](r-intellisense.md) tüm kodunuz ve kitaplıkları arasında kod, imza Yardım biçimlendirme Git tanımı, tüm başvuruları Bul [kod parçacıkları](code-snippets-for-r.md)ve daha fazlası. | [Kod ve Metin Düzenleyici'de Kod Yazma](../ide/writing-code-in-the-code-and-text-editor.md) |
| [R Markdown](rmarkdown-with-r-in-visual-studio.md) | R Markdown belgeler markdown kod blokları içinde tümleşik R kodu ile veri sonuçlarınızı paylaşmanıza yardımcı. | yok |
| [Etkileşimli penceresi](interactive-repl-for-r-in-visual-studio.md) | Tam REPL deneyimi için R kolayca etkileşimli penceresi kaynak dosyasında kodu çalıştırma olanağı sağlar. | yok |
| [Verileri görselleştirme](visualizing-data-with-r-in-visual-studio.md) | Çizdirmek R deneyiminin ayrılmaz bir parçası olan ve RTVS destekleyen birden çok bağımsız çizim windows, her biri kendi geçmişi ve taşıma yeteneğini çizer pencereler arasında. Çizimler bit eşlem ve PDF dosyaları için kaydedilmiş veya bir bit eşlem ya da meta dosyası olarak panoya kopyalandı.  | yok |
| [Değişken Gezgini](variable-explorer.md) | Genel veya özel paketi kapsamı değişkenlerde sıralanabilir tablolarını görüntülemek ve CSV'ye verme olanağı inceleyin. | yok |
| [Tam özellikli hata ayıklama](debugging-r-in-visual-studio.md) | Etkileşimli pencere tümleştirmesi içerir. | [Visual Studio’da hata ayıklama](../debugger/debugging-in-visual-studio.md) |

Ayrıca bkz. [sık sorulan sorular](faq.md).

Aşağıdaki videoda da R araçları özellikleri kısa (5 m 48s) Gözden sağlar:

> [!VIDEO https://www.youtube.com/embed/RcSDEfMgUvU]

## <a name="send-us-your-feedback"></a>Bize Geri bildiriminizi gönderin!

1. **Github sorunları**: RTVS takım ulaşmak için en iyi yolu [Github'da bir sorun dosyalama](https://github.com/Microsoft/RTVS/issues), veya kullanarak **R Araçlar > geri bildirim** menüsü.

1. **Bir gülümseme gönderme Gönder / Frown**: **R Araçlar > görüş** menü geri bildirim gönderin ve sorunu tanılama aşamasında yardımcı olmak için RTVS günlük dosyaları eklemek için hızlı bir şekilde kalır. (Günlükleri içine yazılır `%temp%/RTVSlogs.zip` ayrı olarak göndermek istediğiniz durumda.) Visual Studio telemetri dışında tercih varsa günlüğü devre dışı **Yardım > görüş > ayarları** menü komutunu veya yükleme sırasında.

1. **E-posta**: ekibi doğrudan geri bildirim gönderebilirsiniz *rtvsuserfeedback (,) microsoft.com*.
