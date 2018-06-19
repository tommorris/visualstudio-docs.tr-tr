---
title: Aç komutunu kullanarak dosyaları görüntüleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project types, supporting Open With command
- Open With command
- persistence, supporting Open With command
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9c708bb5a510748b08cac5b46b6829b908e74e0a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128626"
---
# <a name="displaying-files-by-using-the-open-with-command"></a>Aç komutunu kullanarak dosyaları görüntüleme
Bir proje görüntülenecek IDE sorabilirsiniz **birlikte Aç** iletişim kutusu. Bu istek standart düzenleyicileri seçimine sahip bir dosyayı açmak için kullanıcıya sorar. Aşağıdaki adımlar, bu işlem açıklamaktadır.  
  
1.  Proje çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, OSE_UseOpenWithDialog için değerini belirten `OSEOpenDocEditor` parametresi.  
  
2.  Belgenin dosya adı uzantısına göre IDE kayıt defteri can listelenen hangi düzenleyicileri belirtilen belgeyi açın belirler ve bu bilgiyi görüntüler **birlikte Aç** iletişim kutusu.  
  
    > [!NOTE]
    >  Bulunması gereken bir iç Düzenleyicisi projeleri **birlikte Aç** iletişim kutusu için bu tür bir düzenleyici her bir düzenleyici üreteci kaydetmeniz gerekir. İç düzenleyicileri yalnızca işlev belirli bir uygulamasında zorlanan proje türü ile birlikte <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> yöntemi. IDE çekirdek metin Düzenleyicisi'ni ve İkili Düzenleyicisi için bir yerleşik Düzenleyici üreteci vardır. IDE ayrıca her kayıtlı bir Windows Dosya ilişkilendirme adına bir düzenleyici üreteci örneği oluşturur. Microsoft Word gibi bir dosya örnektir.  
  
3.  Kullanıcının seçtiği bir öğeden hemen sonra **birlikte Aç** iletişim kutusu, IDE sonra çağırarak belge açılır <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> yöntemi. Daha fazla bilgi için bkz: [nasıl yapılır: açık standart düzenleyicileri](../../extensibility/how-to-open-standard-editors.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açıp kaydederek proje öğeleri](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Dosya Aç komutu kullanarak dosyaları görüntüleme](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)   
 [Nasıl Yapılır: Standart Düzenleyicileri Açma](../../extensibility/how-to-open-standard-editors.md)