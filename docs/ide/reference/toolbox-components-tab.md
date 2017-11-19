---
title: "Araç kutusu, bileşenler sekmesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Toolbox, Components tab
ms.assetid: 332fafab-a763-4244-b388-15d1b5b5cc04
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bb474e832f815453fd84ba35bc3680b961e17954
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="toolbox-components-tab"></a>Araç Kutusu, Bileşenler Sekmesi
Görüntüler için ekleme bileşenleri [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] ve [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] tasarımcıları. Ek olarak [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)] dahil edilen bileşenleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], gibi <xref:System.Messaging.MessageQueue> ve <xref:System.Diagnostics.EventLog> bileşenleri ekleyebilirsiniz, bu sekmeye kendi veya üçüncü taraf bileşenleri. Daha fazla bilgi için bkz: [nasıl yapılır: araç kutusu sekmeleri işlemek](http://msdn.microsoft.com/en-us/21285050-cadd-455a-b1f5-a2289a89c4db).  
  
 Bu sekme görüntülenecek **Görünüm** menüsünde, select **araç**. İçinde **araç**seçin **bileşenleri** sekmesi.  
  
 **BackgroundWorker**  
 Oluşturur bir `System.ComponentModel.BackgroundWorker` ayrı, özel bir iş parçacığı üzerinde bir işlemi çalıştırabilirsiniz bileşen örneği.  
  
 **DirectoryEntry**  
 Oluşturur bir <xref:System.DirectoryServices.DirectoryEntry> bir düğüm veya nesne Active Directory hiyerarşisinde yalıtır ve Active Directory hizmet sağlayıcıları ile etkileşim kurmak için kullanılan bileşen örneği.  
  
 **DirectorySearcher**  
 Oluşturur bir <xref:System.DirectoryServices.DirectorySearcher> gerçekleştirmek için kullanabileceğiniz bileşen örneği karşı Active Directory sorgular.  
  
 **ErrorProvider**  
 Oluşturur bir `System.Windows.Forms.ErrorProvider` son kullanıcı için bir form üzerinde denetim kendisiyle ilişkili bir hata olduğunu gösterir bileşen örneği.  
  
 **Olay günlüğü**  
 Oluşturur bir <xref:System.Diagnostics.EventLog> bileşen örneği sistem ve özel olay günlükleri, olayları günlüğe yazma ve günlük verileri okuma gibi etkileşim için kullanabilirsiniz. Daha fazla bilgi için bkz: [EventLog bileşen giriş](http://msdn.microsoft.com/en-us/a2ba4f28-4b1a-435e-99ef-51b28e21f805).  
  
 **FileSystemWatcher**  
 Oluşturur bir <xref:System.IO.FileSystemWatcher> herhangi bir dizin veya dosya olan erişimi izlemek için kullanabileceğiniz bileşen örneği değiştirir. Daha fazla bilgi için bkz: [nasıl yapılır: yapılandırma FileSystemWatcher bileşen örnekleri](http://msdn.microsoft.com/en-us/2e628234-4951-4135-8a86-28b924070d50).  
  
 **HelpProvider**  
 Oluşturur bir `System.Windows.Forms.HelpProvider` denetimleri açılır veya çevrimiçi Yardım sağlar bileşen örneği.  
  
 **ImageList**  
 Oluşturur bir `System.Windows.Forms.ImageList` koleksiyonu yönetmek için yöntemler sağlar bileşen örneği `System.Drawing.Image` nesneleri.  
  
 **MessageQueue**  
 Oluşturur bir <xref:System.Messaging.MessageQueue> gelen iletileri okumak ve kuyruklara iletileri yazma, işlemleri ve sıra yönetim görevleri gerçekleştirme de dahil olmak üzere, ileti kuyrukları ile etkileşim kurmak için kullanabileceğiniz bileşen örneği. Daha fazla bilgi için bkz: [ileti sistemi bileşenleri kullanarak](http://msdn.microsoft.com/en-us/922dbac7-26f0-4e39-b666-ccfc184793d7).  
  
 **PerformanceCounter**  
 Oluşturur bir <xref:System.Diagnostics.PerformanceCounter> Windows performans sayaçları, yeni kategori ve örnekleri oluşturma, değerleri sayaçlarını okuma ve sayaç verileri hesaplamaları gibi etkileşim için kullanabileceğiniz bileşen örneği. Daha fazla bilgi için bkz: [izleme performans eşiklerini](http://msdn.microsoft.com/en-us/b8b44a55-31d0-4b45-9517-8c1b1e4fdc91).  
  
 **İşlem**  
 Oluşturur bir <xref:System.Diagnostics.Process> bileşen örneği durdurun, başlatın ve sisteminizdeki işlemlerle ilişkili verileri işlemek için kullanabilirsiniz. Daha fazla bilgi için bkz: [izleme ve yönetme Windows işlemlerinin](http://msdn.microsoft.com/en-us/a86bd4c1-b92c-49a0-8f32-61d67837b45e).  
  
 **Seri bağlantı noktası**  
 Oluşturur bir `System.IO.Ports.SerialPort` zaman uyumlu ve olay denetimli g/ç, PIN ve sonu durumları için erişim ve seri sürücü özelliklerine erişimi sağlayan bileşen örneği.  
  
 **ServiceController**  
 Oluşturur bir <xref:System.ServiceProcess.ServiceController> bileşen örneği başlatma hizmetleri durdurma ve komutlar göndererek dahil olmak üzere var olan hizmetleri yönetmek için kullanabilirsiniz. Daha fazla bilgi için bkz: [Windows hizmetlerini izleme](http://msdn.microsoft.com/en-us/4542ee3f-e052-4cb9-8726-58e9420de222).  
  
 **Zamanlayıcı**  
 Oluşturur bir <xref:System.Windows.Forms.Timer> bileşen örneği, Windows tabanlı uygulamalar için zamana dayalı işlevsellik eklemek için kullanabilirsiniz. Daha fazla bilgi için bkz: [süreölçer bileşeni](/dotnet/framework/winforms/controls/timer-component-windows-forms).  
  
> [!NOTE]
>  Ayrıca vardır sistemi tabanlı <xref:System.Timers.Timer> için ekleyebileceğiniz **araç** bu <xref:System.Timers.Timer> sunucu uygulamaları ve Windows Forms için optimize edilmiştir <xref:System.Windows.Forms.Timer> Windows formlarında kullanmak için uygundur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bileşenleri ile programlama](http://msdn.microsoft.com/Library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)   
 [Bileşen programlama izlenecek yollar](http://msdn.microsoft.com/Library/373cacf7-479e-4b05-991c-5cb18824e913)   
 [Araç kutusu](../../ide/reference/toolbox.md)   
 [Araç kutusu öğelerini Seç iletişim kutusu (Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)