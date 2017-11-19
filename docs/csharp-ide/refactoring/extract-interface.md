---
title: "Ayıklama arabirimi yeniden düzenlemesi (C#) - | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: 55e17f0a-eacb-41ec-b8ca-74f5c6bbd6de
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.extractinterface
dev_langs: csharp
ms.openlocfilehash: 854e341a5c02b3bb4b0a596720a4899410550689
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="extract-an-interface-in-c"></a>C# bir arabirim Ayıkla #
**Ne:** üyelerin bir sınıf, yapı ya da arabirimi kullanarak bir arabirim oluşturmanızı sağlar.

**Ne zaman:** çeşitli sınıflar, yapılar veya arabirimler ortak ve diğer sınıflar, yapılar veya arabirimler tarafından kullanılan yapılamadı yöntemleriyle sahip.

**Neden:** nesne odaklı tasarımları için harika yapılar arabirimlerdir.  Tüm Eat, içki, uyku gibi yaygın yöntemleri olabilir çeşitli hayvanlar (köpek, kat, kuş) için sınıflar sahip düşünün.  IAnimal gibi bir arabirim kullanarak köpek, kat ve kuş ortak bir "imza" Bu yöntemlere ait olmasını olanak tanır.  

**Nasıl:**

1. Yalnızca metin imleci sınıf adında bir yerde put veya eylemi gerçekleştirmek için sınıfı adı vurgulayın.

   ![Vurgulanmış kodu](media/extractinterface_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + ı**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **arayüz** gelen önizleme penceresi açılır.
   * **Fare**
     * Seçin **Düzenle > yeniden düzenlemeniz > ayıklamak arabirimi**.
     * Select sınıfın adını sağ tıklatın **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **arayüz** gelen önizleme penceresi açılır.

1. İçinde **arayüz** , POP iletişim kutusunun sorulan bilgileri girin: ![Arabirimi Ayıkla](media/extractinterface_dialog.png)
   | Alan | Açıklama |
   | --- | --- |
   | **Yeni Arabirim adı** | Oluşturulacak arabirimi adı. Bu t varsayılan*ClassName*, burada *ClassName* Yukarıda seçilen sınıf adı. |
   | **Yeni dosya adı** | Arabirimi içerecek oluşturulacak olan dosya adı. Arabirim adı ile bu t varsayılan olarak*ClassName*, burada *ClassName* Yukarıda seçilen sınıf adı. |
   | **Form arabirimi ortak üyeleri seçin** | Ayıklama arabirimi öğeler.  İstediğiniz gibi birçok seçebilirsiniz. |

1. **Tamam**'ı tıklatın.

   Arabirim, belirtilen adı dosyasında hemen oluşturulur.  Ayrıca, seçtiğiniz sınıfı şimdi bu arabirimi uygular.

   ![Sonuçta elde edilen sınıf](media/extractinterface_class.png)
   ![elde edilen arabirimi](media/extractinterface_interface.png)

## <a name="see-also"></a>Ayrıca Bkz.  
[Yeniden düzenlemesi (C#)](../refactoring-csharp.md)