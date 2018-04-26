---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: hata ayıklama atlama seçeneği (eski) değiştirme'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31047cedd4e8772b9ebab4ef238a8fe32bc07663
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>Nasıl yapılır: hata ayıklama atlama seçeneği (eski) değiştirme

Bu konu, atlama seçeneği eş zamanlı eylemleri eski Windows iş akışı Tasarımcısı'nda Windows Workflow Foundation (WF) uygulamaları için hata ayıklama değiştirmek açıklar. .NET Framework sürüm 3.5 veya WinFX hedeflemek gerektiğinde eski iş akışı Tasarımcısı kullanın.

Ne zaman ayıkladığınız eş zamanlı yürütme sahip eski etkinlikler **ParallelActivity** veya **ConditionedActivityGroup**, kodunuzun içinde ilerleyebilir için iki seçenekten birini kullanabilirsiniz.

Hata ayıklama seçeneği eski iş akışı projenizdeki atlama değiştirmek için aşağıdaki adımları izleyin.

## <a name="procedures"></a>Yordamlar

### <a name="to-change-the-debug-stepping-option"></a>Hata ayıklama sürüm seçeneği değiştirmek için

1.  Visual Studio'yu başlatın.

2.  .NET Framework sürüm 3.5 veya WinFX eşzamanlı etkinlikler ve hedefleyen kullanan yeni bir proje oluşturun veya varolan bir eski iş akışı projesini açın.

3.  Üzerinde **iş akışı** menü eski iş akışı Tasarımcısı'nda, işaret **hata ayıklama**, üzerine gelin ve ardından **atlama seçenekleri**.

4.  Şunlardan birini seçin **örneği** veya **şube**.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)
- [Hata Ayıklama Adımlama Seçenekleri (Eski)](../workflow-designer/debug-stepping-options-legacy.md)