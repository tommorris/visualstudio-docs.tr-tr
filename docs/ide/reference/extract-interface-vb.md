---
title: "Visual Basic'te bir arabirim ayıklamak | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.extractinterface
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 98a3a96357eb6e7391eb92bd0ac3a53dd00f09f5
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="extract-an-interface-in-visual-basic"></a>Visual Basic'te bir arabirim Ayıkla

**Ne:** üyelerin bir sınıf, yapı ya da arabirimi kullanarak bir arabirim oluşturmanızı sağlar.

**Ne zaman:** çeşitli sınıflar, yapılar veya arabirimler ortak ve diğer sınıflar, yapılar veya arabirimler tarafından kullanılan yapılamadı yöntemleriyle sahip.

**Neden:** nesne odaklı tasarımları için harika yapılar arabirimlerdir.  Tüm Eat, içki, uyku gibi yaygın yöntemleri olabilir çeşitli hayvanlar (köpek, kat, kuş) için sınıflar sahip düşünün.  IAnimal gibi bir arabirim kullanarak köpek, kat ve kuş ortak bir "imza" Bu yöntemlere ait olmasını olanak tanır.  

**Nasıl:**

1. Yalnızca metin imleci sınıf adında bir yerde put veya eylemi gerçekleştirmek için sınıfı adı vurgulayın.

   ![Vurgulanmış kodu](media/extractinterface-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + ı**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **arayüz** gelen önizleme penceresi açılır.
   * **Fare**
     * Seçin **Düzenle > yeniden düzenlemeniz > ayıklamak arabirimi**.
     * Select sınıfın adını sağ tıklatın **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **arayüz** gelen önizleme penceresi açılır.

1. İçinde **arayüz** , POP iletişim kutusunun sorulan bilgileri girin: ![Arabirimi Ayıkla](media/extractinterface-dialog-vb.png)
   | Alan | Açıklama |
   | --- | --- |
   | **Yeni Arabirim adı** | Oluşturulacak arabirimi adı. Bu t varsayılan*ClassName*, burada *ClassName* Yukarıda seçilen sınıf adı. |
   | **Yeni dosya adı** | Arabirimi içerecek oluşturulacak olan dosya adı. Arabirim adı ile bu t varsayılan olarak*ClassName*, burada *ClassName* Yukarıda seçilen sınıf adı. |
   | **Form arabirimi ortak üyeleri seçin** | Ayıklama arabirimi öğeler.  İstediğiniz gibi birçok seçebilirsiniz. |

1. **Tamam**'ı tıklatın.

   Arabirim, belirtilen adı dosyasında hemen oluşturulur.  Ayrıca, seçtiğiniz sınıfı şimdi bu arabirimi uygular.

   ![Sonuçta elde edilen sınıf](media/extractinterface-class-vb.png)
   ![elde edilen arabirimi](media/extractinterface-interface-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)