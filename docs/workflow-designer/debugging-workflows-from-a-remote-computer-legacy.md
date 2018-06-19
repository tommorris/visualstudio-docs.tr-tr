---
title: İş Akışı Tasarımcısı - uzak bir bilgisayardan (eski) iş akışları hata ayıklama
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 391180cd76fe5e0cccca802ba1cbfb78277dabc1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31967914"
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>Hata ayıklama iş akışları uzak bir bilgisayardan (eski)

Bu konu, eski Windows iş akışı Tasarımcısı'yla oluşturulan uzak eski Windows Workflow Foundation (WF) uygulamalarının hatalarını açıklar. Uygulamanız .NET Framework sürüm 3.5 veya WinFX hedef gerektiğinde eski iş akışı Tasarımcısı kullanın.

 Visual Studio yüklediğinizde bileşeni yükleme seçeneklerinden birini Visual Studio hata ayıklayıcısı için Windows Workflow Foundation (WF) yüklemektir. Uzaktan hata ayıklama bileşenleri yükler. Bu uzaktan hata ayıklama bileşenleri uzak iş akışı hata ayıklama için hedeflediğiniz bilgisayara yüklenmesi gerekir.

 Ayrıca, uzak bir bilgisayarda hata ayıklama eski iş akışının iş akışı tanımını içeren derlemenin genel derleme önbelleğinde (GAC) hata ayıklama yaptığınız yerel bilgisayarın yüklenmesi gerekir. Örneğin, bir uzak bilgisayarda bir eski bir iş akışını çalıştıran ve yerel bilgisayardan B ayıkladığınız, iş akışı tanımı b bilgisayarı GAC içinde bulunması gerekir Bu seri durumdan ve B bilgisayarında uzaktan A. bilgisayarda çalışan bir iş akışı iş akışı biçimlendirmesi görüntülemek tasarımcı sağlar Genel Derleme Önbelleği hakkında daha fazla bilgi için MSDN Kitaplığı bakın.

 Windows Workflow Foundation uzaktan hata ayıklama için Visual Studio bileşenlerle uzaktan hata ayıklama ile aynı işlevleri. Daha fazla bilgi için Visual Studio uzaktan hata ayıklama MSDN Kitaplığı'nda bkz.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)