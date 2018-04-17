---
title: Dosya Aç komutu kullanarak dosyaları görüntüleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project types, supporting Open File command
- Open File command
- persistence, supporting Open File command
ms.assetid: 4fff0576-b2f3-4f17-9769-930f926f273c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6b84992dc1803f1eee4fc36d477db1708eb90904
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="displaying-files-by-using-the-open-file-command"></a>Dosya Aç komutu kullanarak dosyaları görüntüleme
Aşağıdaki adımlar, IDE nasıl işlediğini açıklar **açık dosya** kullanılabilir komut **dosya** menüde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Adımları ayrıca nasıl projeleri Bu komuttan kaynaklanan çağrıları yanıt vermesi gerektiğini açıklar.  
  
 Bir kullanıcı tıkladığında **açık dosya** komutunu **dosya** menüsünde ve bir dosyadan seçer **Dosya Aç** iletişim kutusunda, aşağıdaki süreç gerçekleşir.  
  
1.  Çalışan belge tabloyu kullanarak, IDE dosyanın zaten bir projede açık olup olmadığını belirler.  
  
    -   Dosya açıksa IDE penceresi resurfaces.  
  
    -   Dosya açık değilse, IDE çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> her proje hangi proje dosyası açabileceğini belirlemek için sorgulanamıyor.  
  
        > [!NOTE]
        >  Proje uygulamanızda <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A>, projenizi dosyayı açar düzeyini gösteren bir öncelik değeri sağlayın. Öncelik değerleri verilmiştir <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> numaralandırması.  
  
2.  Her proje önemini gösteren bir öncelik düzeyi ile yanıt dosyasını açmak için proje olan yerleştirir.  
  
3.  IDE hangi proje dosyasını açar belirlemek için aşağıdaki ölçütleri kullanır:  
  
    -   En yüksek öncelikli (DP_Intrinsic) yanıt proje dosyasını açar. Bu önceliğine sahip birden çok proje yanıt verirse, yanıt ilk proje dosyasını açar.  
  
    -   Proje yanıtlar en yüksek öncelikli (DP_Intrinsic), ancak aynı, daha düşük önceliğe sahip tüm projeleri yanıt, etkin proje dosyasını açar. Proje etkinse yanıt ilk proje dosyasını açar.  
  
    -   Proje dosyası (DP_Unsupported) sahipliğini talep, çeşitli dosyalar proje dosyasını açar.  
  
         Çeşitli dosyalar proje örneği oluşturduysanız, projenin her zaman DP_CanAddAsExternal değeri ile yanıt verir. Bu değer, proje dosyayı açabilmesini gösterir. Bu proje başka bir projede olmayan açık dosyaları barındırmak için kullanılır. Bu projede öğe listesinin kalıcı değildir; Bu proje görünür **Çözüm Gezgini** yalnızca bir dosyayı açmaya kullanıldığında.  
  
         Çeşitli dosyalar proje dosyayı açabilmesini bildirmediği, proje örneği oluşturulmamış. Bu durumda, IDE çeşitli dosyalar proje örneği oluşturur ve dosyayı açmak için proje söyler.  
  
4.  Proje dosyası açılır IDE belirler hemen çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> bu projede yöntemi.  
  
5.  Proje sonra bir projeye özgü Düzenleyici ya da standart düzenleyicisi kullanarak dosyayı açmasını seçeneği vardır. Daha fazla bilgi için bkz: [nasıl yapılır: açık projeye özgü düzenleyicileri](../../extensibility/how-to-open-project-specific-editors.md) ve [nasıl yapılır: açık standart düzenleyicileri](../../extensibility/how-to-open-standard-editors.md)sırasıyla.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Aç komutunu kullanarak dosyaları görüntüleme](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)   
 [Açıp kaydederek proje öğeleri](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Nasıl yapılır: açık projeye özgü düzenleyiciler](../../extensibility/how-to-open-project-specific-editors.md)   
 [Nasıl Yapılır: Standart Düzenleyicileri Açma](../../extensibility/how-to-open-standard-editors.md)