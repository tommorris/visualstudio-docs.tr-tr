---
title: 'Nasıl yapılır: Düzenle ile kesme modunda düzenlemeler uygulama ve devam et | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [Visual Basic], applying edits in break mode
- break mode, applying code changes
- Edit and Continue, applying edits in break mode
- editing, break mode
- coding, editing in break mode
- code, editing in break mode
ms.assetid: 1eef7498-6a1f-4fba-8146-510adc6375c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f031598e0c8f290907e759bcfceac85c1b063f5f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474199"
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>Nasıl Yapılır: Düzenle ve Devam Et ile Kesme Modunda Düzenlemeleri Uygulama
Düzenle ve devam et, kodunuzu kesme modunda düzenleme ve ardından yürütme durdurup olmadan devam etmek için kullanabilirsiniz.  
  
Düzenle ve devam et hata ayıklama sırasında kullanma ile ilgili sınırlamalar için bkz: [desteklenen kod değişiklikleri (C# ve Visual Basic](../debugger/supported-code-changes-csharp.md)]
  
### <a name="to-edit-code-in-break-mode"></a>Kesme modunda kod düzenlemek için  
  
1.  Kesme modu, aşağıdakilerden birini yaparak girin:  
  
    -   Kodunuzda bir kesme noktası ayarlayın ve ardından **hata ayıklamayı Başlat** gelen **hata ayıklama** menü ve uygulamanın kesme noktası isabet bekleyin.  
  
         -veya-  
  
    -   Hata Ayıklamayı Başlat ve ardından **bölün tüm** gelen **hata ayıklama** menüsü.  
  
         -veya-  
  
    -   Özel durum oluştuğunda seçin **düzenlemeyi etkinleştir** üzerinde**özel durum Yardımcısı**.  
  
2.  İstenen ve desteklenen kod değişiklikleri yapın.  
  
     Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri (C# ve Visual Basic](../debugger/supported-code-changes-csharp.md).  
  
    > [!NOTE]
    >  Bir kod, değişikliği yapmak için Düzenle ve devam et tarafından izin verilmiyor dener düzenlemeniz mor dalgalı bir çizgi altı çizili olacaktır ve görev görev listesinde görünür. Geçersiz kod değişikliği geri sürece kod yürütmeye devam etmek mümkün olmaz.  
  
3.  Üzerinde **hata ayıklama** menüsünde tıklatın **devam** yürütme devam etmek için.  
  
     Kodunuzu projeye dahil uygulanan düzenlemeleriniz ile artık yürütür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Desteklenen kod değişiklikleri (C# ve Visual Basic](../debugger/supported-code-changes-csharp.md)   
 [Düzenle ve Devam Et (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)