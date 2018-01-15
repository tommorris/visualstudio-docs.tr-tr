---
title: "Visual Studio'da bir C# türüyle eşleşecek şekilde filename yeniden adlandırma | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: CSharp
ms.workload: dotnet
ms.openlocfilehash: ada7044ebb6718dc0380b387a130ea7b2334e443
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-in-c"></a>Bir dosya adı ya da C# türü için bir dosya türüne eşitleme #

<!-- VERSIONLESS -->
**Bu, Visual Studio 2017 kullanılabilir ve sonraki özelliğidir.  Ek olarak, .NET standart projeleri henüz bu yeniden düzenleme için desteklenmez.**

**Ne:** bir türü filename eşleşecek şekilde yeniden adlandırın ya da bir dosya adı içerdiği türüyle eşleşecek şekilde yeniden adlandırın imkan tanır.

**Ne zaman:** bir dosya veya türü adlandırdınız ve karşılık gelen dosya ya da türü eşleşecek şekilde güncelleştirildi henüz yapmadıysanız. 

**Neden:** farklı bir ad ya da tam tersini, onu aradığınızı bulmak zor sahip bir dosya türü yerleştirmekten.  Türü ya da dosya yeniden adlandırmadan kodunu daha okunabilir ve gitmek daha kolay olur.

**Nasıl:**

1. Vurgula veya metin imleci eşitlemek için türünün adı içinde:

   ![Vurgulanmış kodu](media/synctype-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **dosyayı yeniden adlandır *TypeName*.cs** önizleme penceresi açılan, gelen nerede *TypeName* seçtiğiniz türünün adı.
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **yeniden adlandırmak için türü _Filename_**  önizleme penceresi açılan, gelen nerede *Filename* geçerli dosyanın adıdır.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **dosyayı yeniden adlandır *TypeName*.cs** önizleme penceresi açılan, gelen nerede *TypeName* seçtiğiniz türünün adı.
     * Kodu sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsünde ' nı seçip **yeniden adlandırmak için türü _Filename_**  önizleme penceresi açılan, gelen nerede  *Dosya adı* geçerli dosyanın adıdır.

   Tür veya dosya anında adlandırılacak.  Dosya aşağıdaki örnekte **MyClass.cs** yeniden adlandırıldı **MyNewClass.cs** türü adı ile eşleşmesi için.

   ![Satır içi sonucu](media/synctype-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)
