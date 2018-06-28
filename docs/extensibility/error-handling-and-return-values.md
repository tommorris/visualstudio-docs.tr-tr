---
title: Hata işleme ve dönüş değerleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- errors [Visual Studio SDK], handling
- error handling
- return values
ms.assetid: b2d9079d-39a6-438a-8010-290056694b5c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 85eee51941f6fb549c96dcc257335f9d77b6b0f2
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057138"
---
# <a name="error-handling-and-return-values"></a>Hata İşleme ve Dönüş Değerleri
VSPackages ve COM aynı mimariye hataları için kullanın. `SetErrorInfo` Ve `GetErrorInfo` işlevleri Win32 uygulama programlama arabirimi (API) bir parçasıdır. Tüm VSPackage tümleşik geliştirme ortamı (IDE) içinde bir hata bildirimi aldığında bu zengin hata bilgileri kaydetmek için genel Win32 API'lerinin çağırabilirsiniz. [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Hata bilgilerini yönetmek için birlikte çalışma derlemeleri sağlar.  
  
## <a name="interop-methods"></a>Birlikte çalışma yöntemleri  
 Kolaylık, IDE bir yöntem sağlar. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A>, Win32 API'larını çağırma yerine kullanılacak. Yönetilen kod kullanımda <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A>. Bir hata oluştuğunda `HRESULT` burada hata iletisinin görüntülenmesi düzeyinde ulaşan (Bu genellikle nesnesidir uygulayan bir <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> komut işleyici), IDE başka bir yöntem kullanır <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A>, uygun ileti kutusu görüntülemek için. Yönetilen kod kullanımda <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> yöntemi.  
  
 Normal olarak, COM nesneleri VSPackage uygulayan uygulamak `ISupportErrorInfo`. `ISupportErrorInfo` Arabirimi sağlar zengin hata bilgisini araması zincirinde dikey olarak taşıyabilirsiniz. İş parçacıkları arasında veya üzerinde başka işlemler için kullanılabilir nesneleri desteklemelidir `ISupportErrorInfo` zengin hata bilgilerini geri çağırana düzgün şekilde sıralanmış olduğundan emin olmak için.  
  
 Zengin hata bilgisi için VSPackages ilgili ve, düzenleyici oluşturucuları, düzenleyiciler, hiyerarşileri dahil olmak üzere IDE genişletme ile ilgili ve Hizmetleri, sunulan tüm nesneleri desteklemelidir. IDE uygulamak için bu VSPackage nesneleri gerekmese `ISupportErrorInfo`, her zaman teşvik.  
  
 IDE hata bilgilerini raporlama ve bir kullanıcıya görüntüleme sorumludur [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] her bir `HRESULT` IDE yayılır. IDE de oluşturmak için mekanizmasıdır `ErrorInfo` nesneleri.  
  
## <a name="general-guidelines"></a>Genel Yönergeler  
 Kullanabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> ayarlamak ve VSPackage uygulamanız için de iç hatalarını raporlamak için yöntemleri. Ancak, genel bir kural olarak, VSPackage hata iletilerini işlemek için aşağıdaki yönergeleri izleyin:  
  
-   Uygulama `ISupportErrorInfo` VSPackage COM nesnelerinde.  
  
-   Çağıran mekanizması bildirdiği bir hata oluştur <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> uygulayan nesneler yönteminde <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
-   Aracılığıyla kullanıcılara hataları görüntülemek IDE izin <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> yöntemi.  
  
## <a name="error-information-in-the-ide"></a>IDE içinde hata bilgileri  
 Aşağıdaki kuralları hata bilgileri nasıl ele alınacağını gösteren [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE:  
  
-   Eski hata bilgisini kullanıcılara bildirilmedi güvence altına almak için bir savunma stratejisi işlevleri gibi bu çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> yöntemi ilk çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> yöntemi. Geçirin `null` herhangi bir şey çağıran yeni hata bilgilerini ayarlayabilir önce önbelleğe alınmış hata iletileri temizleyin.  
  
-   Hata iletilerini doğrudan bildirmeyen işlevleri çağırmak için izin verilmez <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> bir hata döndürüyor, yöntemi `HRESULT`. Temizlemek için izin verilen `ErrorInfo` bir işlevi veya döndürülürken girişindeki <xref:Microsoft.VisualStudio.VSConstants.S_OK>. Bir çağrı hata döndürdüğünde kuralın tek özel durum olan `HRESULT` hangi alıcı taraf açıkça kurtarmak veya güvenli bir şekilde yoksay.  
  
-   Açıkça bir hatayı gözardı herhangi bir tarafa `HRESULT` çağırmalısınız <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> yöntemiyle <xref:Microsoft.VisualStudio.VSConstants.S_OK>. Aksi takdirde, `ErrorInfo` nesnesi yanlışlıkla kullanılabilir başka bir tarafa kendi sağlamadan bir hata oluşturduğunda `ErrorInfo`.  
  
-   Bir hata kaynaklanan tüm yöntemleri `HRESULT` çağırmak için önerilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> yöntemi zengin hata bilgileri sağlayın. Varsa döndürülen `HRESULT` özel bir olan `FACILITY_ITF` hata sonra yöntemi uygun sağlamak için gereklidir `ErrorInfo`nesnesi. Döndürülen hata standart sistem hatası ise (örneğin, <xref:Microsoft.VisualStudio.VSConstants.E_OUTOFMEMORY>, <xref:Microsoft.VisualStudio.VSConstants.E_ABORT>, <xref:Microsoft.VisualStudio.VSConstants.E_INVALIDARG>, <xref:Microsoft.VisualStudio.VSConstants.E_UNEXPECTED>ve benzeri) hata kodu açıkça çağırmadan döndürmek için kabul edilebilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> yöntemi. Kaynaklanan bir hata olduğunda bir savunma kodlama stratejisi, olarak `HRESULT` (sistem hataları gibi), her zaman çağrısı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> biriyle yöntemi `ErrorInfo` daha ayrıntılı hata açıklayan veya `null`.  
  
-   Başka bir çağrı tarafından kaynaklanan bir hata başarısız alındı bilgileri geçirmek gerekir döndüren tüm işlevler Çağır `HRESULT` değiştirmeden `ErrorInfo` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [Seterrorınfo (Bileşen Otomasyonu)](http://msdn.microsoft.com/8eaacfac-fc37-4eaa-870b-10b99d598d66)   
 [Geterrorınfo](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-geterrorinfo)   
 [ISupportErrorInfo arabirimi](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo)
