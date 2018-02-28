---
title: "Nasıl yapılır: uygulama geri alma yönetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 1942245d-7a1d-4a11-b5e7-a3fe29f11c0b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: cf57b24d81e193294f5ab90f71af07b229ec5839
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-undo-management"></a>Nasıl yapılır: uygulama geri alma yönetimi
Geri alma yönetimi için kullanılan birincil arabirimdir <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager>, ortamı tarafından gerçekleştirilir. Geri alma yönetimini desteklemek için ayrı geri birimleri uygulamak (diğer bir deyişle, <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit>, birden çok tek tek adımları içerebilir.  
  
 Geri alma Yönetimi uygulamak nasıl düzenleyicinizi birden çok görünüm veya destekleyip desteklemediğini bağlı olarak değişir. Her uygulama için yordamlar aşağıdaki bölümlerde ayrıntılı olarak belirtilir.  
  
## <a name="cases-where-an-editor-supports-a-single-view"></a>Burada bir düzenleyici tek bir görünüm destekler durumları  
 Bu senaryoda, birden çok görünüm Düzenleyicisi desteklemez. Yalnızca bir düzenleyici ve bir belge yoktur ve geri alma desteği. Geri alma Yönetimi uygulamak için aşağıdaki yordamı kullanın.  
  
#### <a name="to-support-undo-management-for-a-single-view-editor"></a>Tek görünüm Düzenleyicisi için geri alma yönetimini desteklemek için  
  
1.  Çağrı `QueryInterface` üzerinde `IServiceProvider` pencere çerçevesi için arabirimde `IOleUndoManager`, geri alma yöneticisi erişmek için belge görünümü nesnesinden (`IID_IOLEUndoManager`).  
  
2.  Bir Görünüm penceresi çerçeveye tarihli zaman çağırmak için kullanabileceği bir site işaretçi alır `QueryInterface` için `IServiceProvider`.  
  
## <a name="cases-where-an-editor-supports-multiple-views"></a>Burada bir düzenleyici birden çok görünüm destekleyen durumları  
 Belge ve görünüm ayrımı varsa, normalde bir geri alma yöneticisi belge ile ilişkili değil. Tüm geri birimleri belge veri nesneyle ilişkili bir geri alma yöneticisi yerleştirilir.  
  
 Görünüm var olduğu her görünüm için bir geri alma yöneticisi sorgulanırken yerine belge veri nesnesi çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> geri alma yöneticisi örneği oluşturmak için bir sınıf tanımlayıcısı CLSID_OLEUndoManager belirtme. Sınıf tanımlayıcısı OCUNDOID.h dosyasında tanımlanır.  
  
 Kullanırken <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> kendi geri alma yöneticisi örneği oluşturmak için geri alma yöneticisi ortamına kanca için aşağıdaki yordamı kullanın.  
  
#### <a name="to-hook-your-undo-manager-into-the-environment"></a>Geri alma yöneticisi ortamına bağlanmanıza  
  
1.  Çağrı `QueryInterface` döndürülen nesne üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2> için `IID_IOleUndoManager`. İşaretçi depolamak <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager>.  
  
2.  Çağrı `QueryInterface` üzerinde `IOleUndoManager` için `IID_IOleCommandTarget`. İşaretçi depolamak <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
3.  Geçiş, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> saklı çağrılarını `IOleCommandTarget` arabirimi aşağıdaki StandardCommandSet97 komutları için:  
  
    -   cmdidUndo  
  
    -   cmdidMultiLevelUndo  
  
    -   cmdidRedo  
  
    -   cmdidMultiLevelRedo  
  
    -   cmdidMultiLevelUndoList  
  
    -   cmdidMultiLevelRedoList  
  
4.  Çağrı `QueryInterface` üzerinde `IOleUndoManager` için `IID_IVsChangeTrackingUndoManager`. İşaretçi depolamak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>.  
  
     İşaretçi kullanmak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager> çağırmak için <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager.MarkCleanState%2A>, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager.AdviseTrackingClient%2A>ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager.UnadviseTrackingClient%2A> yöntemleri.  
  
5.  Çağrı `QueryInterface` üzerinde `IOleUndoManager` için `IID_IVsLinkCapableUndoManager`.  
  
6.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkCapableUndoManager.AdviseLinkedUndoClient%2A> belgenizi ile hangi de uygulamanız gerekir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoClient> arabirimi. Belgenizi kapatıldığında, çağrı `IVsLinkCapableUndoManager::UnadviseLinkedUndoClient`.  
  
7.  Belgenizi kapatıldığında, çağrı `QueryInterface` için geri alma yöneticinize üzerinde `IID_IVsLifetimeControlledObject`.  
  
8.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLifetimeControlledObject.SeverReferencesToOwner%2A>.  
  
9. Belgeye değişiklik yapıldığında, çağrı <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager.Add%2A> yöneticisiyle üzerinde bir `OleUndoUnit` sınıfı. <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager.Add%2A> Yöntemi tutar nesneye bir başvurusu nedenle genellikle, yayın, sonra sağ <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager.Add%2A>.  
  
 `OleUndoManager` Sınıfı, bir tek geri yığını örneği temsil eder. Bu nedenle, geri alma veya yineleme için izlenen verileri varlığı başına bir geri alma Yöneticisi nesnesi yok.  
  
> [!NOTE]
>  Geri alma Yöneticisi nesnesi yaygın metin düzenleyicisi tarafından kullanılırken, bu metin Düzenleyicisi'ni belirli desteği olan bir genel bileşendir. Birden çok düzeyli geri alma veya yineleme desteklemek istiyorsanız, bunu yapmak için bu nesneyi kullanabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLifetimeControlledObject>   
 [Nasıl yapılır: geri alma yığını temizleyin](../extensibility/how-to-clear-the-undo-stack.md)