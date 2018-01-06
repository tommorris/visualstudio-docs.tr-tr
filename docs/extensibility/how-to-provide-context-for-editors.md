---
title: "Nasıl yapılır: içerik düzenleyicileri açısından sağlamak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - provide context
ms.assetid: 12df4d06-df6b-4eaf-a7bf-c83655a0c683
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d9b89c4e45f8268df55386d321816325fb50174c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-provide-context-for-editors"></a>Nasıl yapılır: içerik düzenleyicileri açısından sağlayın
Bir düzenleyici için bağlam Düzenleyicisi odağa sahip veya odağı bir araç penceresi hemen taşınmadan önce odağa sahip olduğunda etkindir. Aşağıdakileri yaparak içerik için bir düzenleyici sağlayabilirsiniz:  
  
1.  Bir içerik paketi oluşturun.  
  
2.  İçerik Paketi seçimi öğe tanımlayıcı (SEID) yayımlayın.  
  
3.  Paketi bağlamda korur.  
  
 Bu görevleri aşağıdaki yordamları tarafından ele alınmıştır. İçerik sağlama hakkında daha fazla bilgi için bkz: **güçlü programlama** bu konuda daha sonra.  
  
### <a name="to-create-a-context-bag-for-an-editor-or-a-designer"></a>Bir düzenleyici veya bir tasarımcı için bir içerik paketi oluşturmak için  
  
1.  Çağrı `QueryService` üzerinde <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> için arabirim <xref:Microsoft.VisualStudio.Shell.Interop.SVsMonitorUserContext> hizmet.  
  
     Bir işaretçi <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorUserContext> arabirimi döndürülür.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorUserContext.CreateEmptyContext%2A> yeni bir içerik veya üzere paketi oluşturmak için yöntemi.  
  
     Bir işaretçi <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext> arabirimi döndürülür.  
  
3.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddAttribute%2A> öznitelikler, arama anahtar sözcükleri veya F1 anahtar sözcükleri bağlamı veya üzere paketi eklemek için yöntem.  
  
4.  Bir üzere paketi oluşturuyorsanız, çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddSubcontext%2A> üzere paketi için üst içerik paketi bağlamak için yöntem.  
  
5.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AdviseUpdate%2A> bildirim almak için zaman **dinamik yardımcı** penceredir güncelleştirmek üzere.  
  
     Sahip **dinamik yardımcı** çağrı düzenleyicinizi penceresi güncelleştirmek hazır olduğunda gecikme güncelleştirme gerçekleşene kadar bağlam değiştirme olanağı sağlar. Sistem boşta kalma süresi kullanılabilir hale gelene kadar uzun süren algoritmaları çalıştıran gecikme izin verdiği için Bunun yapılması performansı geliştirebilir.  
  
### <a name="to-publish-the-context-bag-to-the-seid"></a>İçerik Paketi SEID yayımlamak için  
  
1.  Çağrı `QueryService` üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> bir işaretçi döndürmek için hizmet <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> arabirimi.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A>, bir öğe tanımlayıcı belirtme (`elementid` parametresi) için genel düzeyden bağlamı geçirme belirtmek için SEID_UserContext değeri.  
  
3.  Düzenleyici veya Tasarımcısı etkin olduğunda, değerleri kendi <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> nesne genel seçimi yayılır. Her oturum için bir kez bu işlemi tamamlayın ve ardından işaretçinin çağırdığınızda oluşturulan genel bağlam için depolamak yeterlidir <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A>.  
  
### <a name="to-maintain-the-context-bag"></a>İçerik Paketi korumak için  
  
1.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext> emin olmak için **dinamik yardımcı** penceresi, Düzenleyicisi veya Tasarımcısı güncelleştirdiği önce çağırır.  
  
     Çağırdı her içerik paketi <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AdviseUpdate%2A> içerik paketi oluşturulur ve uyguladı sonra <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate>, IDE çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A> içerik paketi güncelleştirilir bağlam sağlayıcısına bildirmek için. Bu çağrı öznitelikleri ve anahtar sözcükleri İçerik Paketi ve tüm alt bağlam paketler önce değiştirmek için kullanabileceğiniz **dinamik yardımcı** penceresi güncelleştirme gerçekleşir.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.SetDirty%2A> Düzenleyicisi veya Tasarımcısı yeni bağlam olduğunu belirtmek için içerik paketi üzerinde.  
  
     Zaman **dinamik yardımcı** penceresi çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A> Bu güncelleştirme, Düzenleyicisi veya Tasarımcısı uygun şekilde üst içerik paketi hem de herhangi üzere paketler için içerik o anda güncelleştirebilirsiniz belirtmek için.  
  
    > [!NOTE]
    >  `SetDirty` Bayrağı ayarlanmış otomatik olarak `true` her bağlamı eklenemez veya içerik paketi kaldırılamaz. **Dinamik yardımcı** penceresi yalnızca çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A> içerik paketi üzerinde varsa `SetDirty` bayrağı ayarlanmış `true`. İçin Sıfırla `false` güncelleştirmeden sonra.  
  
3.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddAttribute%2A> bağlamı etkin içeriği koleksiyona eklemek için veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.RemoveAttribute%2A> bağlamı kaldırmak için.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Kendi Düzenleyicisi yazıyorsanız üçünü Düzenleyicisi bağlamı sağlamak için bu konudaki yordamları tamamlamanız gerekir.  
  
> [!NOTE]
>  Düzgün bir düzenleyici veya Tasarımcısı penceresinde etkinleştirmek ve komut yönlendirme düzgün güncelleştirildiğinden emin olmak için çağırmalısınız <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> odak penceresi oluşturmak için bileşende.  
  
 SEID özelliklerin seçimine göre değiştiren bir koleksiyondur. SEID bilgi genel seçimi yoluyla kullanılabilir. Genel seçim tarafından tetiklenen olayları içine kablolu <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> arabirimi, ve bir liste her şeyin (geçerli Düzenleyicisi, geçerli araç penceresi, geçerli hiyerarşi ve benzeri) seçmiştir.  
  
 Düzenleyiciler ve tasarımcıları için hangi içerik her değiştiğinde değiştirebilir miyim imleci taşır bir sözcük içinde sürekli olarak içerik paketi güncelleştirmek için yetersiz olduğunu. Düzenleyicisi veya designer penceresi içinde taşınması imleci algılamak istediğiniz zaman daha verimli güncelleştirme yapmak için çağırabilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.SetDirty%2A>. Bunun yapılması bağlam değişikliklerinizi boşta kalma süresi ve IDE'nin bağlam hizmeti bildirim Düzenleyicisi veya Tasarımcısı, gönderir kadar tutun olanak tanır **dinamik yardımcı** penceresi güncelleştiriyor. Bu yaklaşım, bu konudaki "İçerik Paketi korumak için" yordamında kullanılır.  
  
 Düzenleyici veya Tasarımcısı'nda etkinlikler için bağlam sağladıktan sonra Düzenleyicisi veya Tasarımcısı kendisi için Yardım almak kullanıcıların belirli bir F1 anahtar sağlamalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AddAttribute%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.AdviseUpdate%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.RemoveAttribute%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.SetDirty%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContextUpdate.UpdateUserContext%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx>