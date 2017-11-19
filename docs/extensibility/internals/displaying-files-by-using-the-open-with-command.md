---
title: "Aç komutunu kullanarak dosyaları görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, supporting Open With command
- Open With command
- persistence, supporting Open With command
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ed8a19ce0cfb6a7936d61ff7a5855498d2010359
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Nasıl yapılır: standart düzenleyicileri açın](../../extensibility/how-to-open-standard-editors.md)