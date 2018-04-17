---
title: 'Nasıl yapılır: standart metin işaretçileri ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - standard text markers
ms.assetid: a39fca69-0014-474c-933f-51f0e9b9617e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2fc5bf34c9b4200d8d7fef2d9f4a878ca604f886
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-standard-text-markers"></a>Nasıl yapılır: standart metin işaretleyicileri ekleyin
İle sağlanan varsayılan metin işaretçisi türleri oluşturmak için aşağıdaki yordamı kullanın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çekirdek Düzenleyici.  
  
### <a name="to-create-a-text-marker"></a>Bir metin işaretçisi oluşturmak için  
  
1.  Kullanmanıza bağlı olarak, bir veya iki boyutlu koordinat sistemi, çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> yöntemi veya <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> yeni bir metin işaretçisi oluşturmak için yöntem.  
  
     Metin üzerinde işaretçisi oluşturmak için bir aralığı bir işaret türü bu yöntem çağrısında belirtin ve bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> arabirimi. Bu yöntem, sonra yeni oluşturulan metin işaretçisi bir işaretçi döndürür. İşaretçi türleri gelen alınır <xref:Microsoft.VisualStudio.TextManager.Interop.MARKERTYPE> numaralandırması. Belirtin bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> işaret olayları bilgilendirilmek istiyorsanız arabirim.  
  
    > [!NOTE]
    >  Metin işaretçileri ana kullanıcı Arabirimi iş parçacığı üzerinde yalnızca oluşturun. Çekirdek düzenleyici metin işaretçileri oluşturmak için metin arabelleğini içeriğine güvenir ve metin arabelleği iş parçacığı içinde korumalı değil.  
  
## <a name="adding-a-custom-command"></a>Özel bir komut ekleme  
 Uygulama `IVsTextMarkerClient` arabirimi ve bir işaretçi için bir işaret sağlama işaret davranışı çeşitli şekillerde geliştirir. İlk olarak, bu işaret için ipuçları sağlamak için ve komutlarını çalıştırmaya izin verir. Bu ayrıca, tek tek işaretlerin olay bildirimleri alması ve özel bağlam menüsü işaretçisi oluşturmak için sağlar. Özel bir komut işaret bağlam menüsüne eklemek için aşağıdaki yordamı kullanın.  
  
#### <a name="to-add-a-custom-command-to-the-context-menu"></a>Bağlam menüsüne bir özel komut eklemek için  
  
1.  Bağlam menüsü görüntülenmeden önce ortamı çağırır <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetMarkerCommandInfo%2A> yöntemi ve metin işaretçisi gösteren bir işaretçi sorundan geçişleri ve bağlam menüsünden komutu öğe sayısı.  
  
     Örneğin, bağlam menüsünde kesme noktası özgü komutlar şunlardır **kaldırmak kesme noktası** aracılığıyla **yeni kesme noktası**, aşağıdaki ekran görüntüsünde gösterildiği.  
  
     ![İşaretçi bağlam menüsü](../extensibility/media/vsmarkercontextmenu.gif "vsMarkercontextmenu")  
  
2.  Geri özel komut adını tanımlayan bir metin geçirin. Örneğin, **kaldırmak kesme noktası** bu ortam zaten sağlamadı özel bir komut olabilir. Ayrıca geri geçirdiğiniz komutu desteklenen, kullanılabilir ve etkin olup ve/veya şirket dışı iki durumlu. Ortam özel komut bağlam menüsünde doğru şekilde görüntülemek için bu bilgileri kullanır.  
  
3.  Ortam çağrıları komutu çalıştırmak için <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A> yöntemi, metin işaretçisi ve bağlam menüsünden Seçili komut sayısı için bir işaretçi geçirme.  
  
     Metin işaretçisi hangi eylemleri belirler, özel bir komut yürütmek için bu çağrı bu bilgileri kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin işaretçileri eski API ile kullanma](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Nasıl yapılır: uygulama hata işaretçileri](../extensibility/how-to-implement-error-markers.md)   
 [Nasıl yapılır: özel metin işaretçileri oluşturma](../extensibility/how-to-create-custom-text-markers.md)   
 [Nasıl yapılır: metin işaretçileri kullanın](../extensibility/how-to-use-text-markers.md)