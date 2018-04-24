---
title: Düzenle ve devam et (Visual Basic) | Microsoft Docs
ms.custom: ''
ms.date: 10/11/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue, 64-bit
- Edit and Continue [Visual Basic]
- debugging [Visual Basic], Edit and Continue
- Visual Basic, Edit and Continue
- 64-bit Edit and Continue
ms.assetid: 7e90f34f-e699-45ab-a4c9-a4b527c498c8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aa3b8c287129c164d8c6984ac52375d6012fbd68
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="edit-and-continue-visual-basic"></a>Düzenle ve Devam Et (Visual Basic)
Düzenle ve devam et için bir özelliktir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] , hata ayıklama kesme modunda yürütülürken kodunuzu değiştirmek olanak sağlar. Kod düzenlemeleri uygulandıktan sonra yerinde yeni düzenlemelerle kodu yürütme devam ve etkisi görebilirsiniz.  
  
 Düzenle ve kesme modu girişinizde özellik devam kullanabilirsiniz. Kesme modu, yönerge işaretçisi, sarı bir ok ucunu kaynak penceresinde, yürütülebilir bir deyim gövdesindeki olacak bir yöntemi veya özelliği içeren satırı noktalarına sonraki yürütüldü.

 Düzenle ve devam et hata ayıklama oturumu sırasında yapmak isteyebilirsiniz çoğu değişiklikleri destekler, ancak bazı özel durumlar vardır. Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri (C# ve Visual Basic)](../debugger/supported-code-changes-csharp.md).   
  
 Yetkisiz bir düzenleme yaptığınızda, değişiklik mor dalgalı alt çizgi ile işaretlenir ve bir görev görev listesinde görüntülenir. Düzenle ve devam et kullanmaya devam etmek istiyorsanız, yetkisiz bir düzen geri almanız gerekir. Belirli yetkisiz düzenlemeleri dış Düzenle ve devam et yapıldığında izin verilir. Yetkisiz bir düzen sonuçlarını korumak istiyorsanız, hata ayıklamayı durdurun ve uygulamanızı yeniden başlatmanız gerekir.  
  
 Düzenle ve devam et UWP uygulamaları Windows 10 ve .NET Framework 4.6 hedef x86 hem x64 uygulamalar desteklenir (yalnızca masaüstü sürümü .NET Framework'dur) masaüstü veya sonraki sürümleri.

 > [!NOTE]
 > Desteklenmeyen uygulamalar ve platformlar ASP.NET 5, Silverlight 5 ve Windows 8.1 içerir.
  
 Düzenle ve devam et desteklenmiyor kullanarak hata ayıklama başlattığınızda **ekleme işlemi için**. Düzenle ve devam et iyileştirilmiş kodda veya karma için desteklenmeyen yönetilen ve yerel kodu. Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri (C# ve Visual Basic](../debugger/supported-code-changes-csharp.md).
  
 Bu bölümdeki konular, bu özelliği kullanmak nasıl ve ne tür değişiklikler hakkında daha ayrıntılı bilgi verilmez sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: Düzenle ile kesme modunda düzenlemeler uygulama ve devam et](../debugger/how-to-apply-edits-in-break-mode-with-edit-and-continue.md)  
 Kesme modunda düzenlemeler kodu uygulamak açıklanmaktadır.  
  
 [Desteklenen kod değişiklikleri (C# ve Visual Basic](../debugger/supported-code-changes-csharp.md)   
 Ne düzenlemeleri türleri olamaz açıklar başlığında gerçekleştirilen [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)] Düzenle ve devam et.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Düzenle ve devam et](../debugger/edit-and-continue.md)  
 Düzenle ve devam et konuların listesini sağlar.