---
title: Derleme olayları iletişim kutusu (Visual Basic) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vb.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- build events, specifying
- pre-build events
- Build Events dialog box
- post-build events
ms.assetid: 3a81a7c7-39f9-47a8-ba5a-b351227f380e
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 23f1d883468c34d042da3501f4fc88004ebdf44e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690636"
---
# <a name="build-events-dialog-box-visual-basic"></a>Derleme Olayları İletişim Kutusu (Visual Basic)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [derleme olayları iletişim kutusu (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/build-events-dialog-box-visual-basic).  
  
  
Kullanım **Build Events** yapı yapılandırma yönergeleri belirtmek için iletişim kutusu. Altında herhangi bir ön derleme veya derleme sonrası olayı çalıştığı koşulları belirtebilirsiniz. Daha fazla bilgi için [nasıl yapılır: Specify Build Events (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).  
  
 **Derleme öncesi olay komut satırı**  
 Oluşturma başlamadan önce yürütülecek herhangi bir komut belirtir. Uzun komutları yazmak için tıklatın **Düzenle derleme öncesi** görüntülenecek [derleme öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
> [!NOTE]
>  Derleme öncesi olayları, projenin güncel olduğundan ve hiçbir derlemenin tetiklenmesinin çalıştırmayın.  
  
 **Derleme sonrası olay komut satırı**  
 Oluşturma bittikten sonra yürütülecek herhangi bir komut belirtir. Uzun komutları yazmak için tıklatın **Düzenle derleme sonrası** görüntülenecek **derleme öncesi olay/derleme sonrası olay komut satırı d**ialog kutusu.  
  
> [!NOTE]
>  Ekleme bir `call` .bat dosyaları çalıştıran tüm derleme sonrası komutları önce deyimi. Örneğin, `call C:\MyFile.bat` veya `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Derleme sonrası olayı Çalıştır**  
 Aşağıdaki tabloda gösterildiği gibi çalıştırmak derleme sonrası olay koşulları belirtir.  
  
|Seçenek|Sonuç|  
|------------|------------|  
|**Her zaman**|Derleme sonrası olay oluşturma işlemi başarılı olup olmadığını bağımsız olarak çalışır.|  
|**Başarıyla derlendiğinde**|Derleme başarılı olursa, derleme sonrası olay çalıştırılır. Olay oluşturma işlemi başarılı olduğu sürece, güncel, hatta bir proje için çalışır. Varsayılan ayar budur.|  
|**Derleme proje çıktısı zaman güncelleştirir**|Derleme sonrası olay, yalnızca önceki Derleyici çıkış dosyasından derleyicinin çıktı dosyası (.exe veya .dll) farklı olduğu durumlarda çalıştırılır. Bir projenin güncel olması halinde bir derleme sonrası olay çalıştırılmaz.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme sayfası, Proje Tasarımcısı (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Nasıl yapılır: derleme olayları belirtme (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Derleme öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)



