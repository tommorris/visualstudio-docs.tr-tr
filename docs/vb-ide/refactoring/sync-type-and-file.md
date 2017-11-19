---
title: "Eşitleme türü ve dosya adı - yeniden düzenleme (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff86d7bd-837b-4664-b0ea-d3ee0c52fe87
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: VB
ms.openlocfilehash: da6f39dd3573d361c1da579eb3d84c2c8ceeb517
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-in-visual-basic"></a>Bir dosya adı ya da Visual Basic'te bir tür için bir dosya türüne eşitleme

<!-- VERSIONLESS -->
**Bu, Visual Studio 2017 kullanılabilir ve sonraki özelliğidir.  Ek olarak, .NET standart projeleri henüz bu yeniden düzenleme için desteklenmez.**

**Ne:** bir türü filename eşleşecek şekilde yeniden adlandırın ya da bir dosya adı içerdiği türüyle eşleşecek şekilde yeniden adlandırın imkan tanır.

**Ne zaman:** bir dosya veya türü adlandırdınız ve karşılık gelen dosya ya da türü eşleşecek şekilde güncelleştirildi henüz yapmadıysanız. 

**Neden:** farklı bir ad ya da tam tersini, onu aradığınızı bulmak zor sahip bir dosya türü yerleştirmekten.  Türü ya da dosya yeniden adlandırmadan kodunu daha okunabilir ve gitmek daha kolay olur.

**Nasıl:**

1. Vurgula veya metin imleci eşitlemek için türünün adı içinde:

   ![Vurgulanmış kodu](media/synctype_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **dosyayı yeniden adlandır *TypeName*.vb** önizleme penceresi açılan, gelen nerede *TypeName* seçtiğiniz türünün adı.
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **yeniden adlandırmak için türü _Filename_**  önizleme penceresi açılan, gelen nerede *Filename* geçerli dosyanın adıdır.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **dosyayı yeniden adlandır *TypeName*.vb** önizleme penceresi açılan, gelen nerede *TypeName* seçtiğiniz türünün adı.
     * Kodu sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsünde ' nı seçip **yeniden adlandırmak için türü _Filename_**  önizleme penceresi açılan, gelen nerede  *Dosya adı* geçerli dosyanın adıdır.

   Tür veya dosya anında adlandırılacak.  Dosya aşağıdaki örnekte **Employee.vb** yeniden adlandırıldı **Person.vb** türü adı ile eşleşmesi için.

   ![Satır içi sonucu](media/synctype_result.png)

## <a name="see-also"></a>Ayrıca Bkz.  
[Yeniden düzenleme (Visual Basic)](../refactoring-vb.md)
