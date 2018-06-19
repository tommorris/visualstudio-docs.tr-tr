---
title: Derleme Olayları İletişim Kutusu (Visual Basic)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- build events, specifying
- pre-build events
- Build Events dialog box
- post-build events
ms.assetid: 3a81a7c7-39f9-47a8-ba5a-b351227f380e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 38ef3b173643c7bff0e1417ffc9ecfb431b06685
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31944141"
---
# <a name="build-events-dialog-box-visual-basic"></a>Derleme Olayları İletişim Kutusu (Visual Basic)
Kullanım **yapı olayları** yapı yapılandırma yönergeleri belirtmek için iletişim kutusu. Ayrıca, tüm ön derleme veya derleme sonrası olayları çalıştığı koşulları belirtebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: belirtin Build Events (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).

 **Oluşturma öncesi olay komut satırı** yapı başlamadan önce yürütülecek herhangi bir komut belirtir. Uzun komutları yazmak için tıklatın **düzen oluşturma öncesi** görüntülemek için [oluşturma öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

> [!NOTE]
> Oluşturma öncesi olaylar proje güncel olduğundan ve hiçbir derleme tetiklenir çalıştırmayın.


 **Oluşturma sonrası olay komut satırı** yapı sona erdikten sonra yürütmek için herhangi bir komut belirtir. Uzun komutları yazmak için tıklatın **düzen oluşturma sonrası** görüntülemek için **oluşturma öncesi olay/derleme sonrası olay komut satırı d**ialog kutusu.

> [!NOTE]
> Ekleme bir `call` .bat dosyaları çalıştıran tüm sonrası derleme komutları önce deyim. Örneğin, `call C:\MyFile.bat` veya `call C:\MyFile.bat call C:\MyFile2.bat`.


 **Oluşturma sonrası olay çalıştırmak** aşağıdaki tabloda gösterildiği gibi çalıştırmak, oluşturma sonrası olay koşulları belirtir.

|Seçenek|Sonuç|
|------------|------------|
|**Her zaman**|Oluşturma sonrası olay oluşturma işlemi başarılı olup olmadığını bağımsız olarak çalışır.|
|**Üzerinde başarılı derleme**|Oluşturma işlemi başarılı olursa oluşturma sonrası olay çalıştırın. Olay oluşturma işlemi başarılı olduğu sürece, güncel bile bir proje için çalışır. Varsayılan ayar budur.|
|**Yapı proje çıktı zaman güncelleştirir**|Yalnızca önceki derleyici çıktı dosyasından derleyicinin çıktı dosyası (.exe veya .dll) farklı olduğu durumlarda oluşturma sonrası olay çalıştırın. Bir proje güncel ise oluşturma sonrası olay çalıştırılmaz.|

## <a name="see-also"></a>Ayrıca Bkz.

- [Derleme Sayfası, Proje Tasarımcısı (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)
- [Nasıl Yapılır: Derleme Olayları Belirtme (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)
- [Derleme öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)