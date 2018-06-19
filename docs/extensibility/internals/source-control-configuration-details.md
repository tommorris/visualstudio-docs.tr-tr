---
title: Kaynak denetimini yapılandırma ayrıntılarını | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], configuration details
ms.assetid: adbee9fc-7a2e-4abe-a3b8-e6615bcd797f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fc10c7602f3298b532b4af76e66b43d469416ba5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134132"
---
# <a name="source-control-configuration-details"></a>Kaynak denetimini yapılandırma ayrıntıları
Kaynak denetimi uygulamak için proje sistem ya da aşağıdakileri yapmak için Düzenleyicisi'ni düzgün şekilde yapılandırmanız gerekir:

-   Değiştirilen durumuna geçiş izin iste

-   Bir dosyayı kaydetmek için izin iste

-   Eklemek, kaldırmak veya projedeki dosyaları yeniden adlandırmak için izin iste

## <a name="request-permission-to-transition-to-changed-state"></a>Değiştirilen durumuna geçiş izin iste
 Bir proje veya Düzenleyicisi değiştirilen (kirli) durumuna geçiş izni çağırarak istemelidir <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>. Uygulayan her Düzenleyicisi <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty%2A> çağırmalısınız <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> ve belgenin ortamından döndürmeden önce değiştirmek için onay almak `True` için <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty%2A>. Bir proje aslında bir proje dosyası için bir düzenleyici ve sonuç olarak, bir metin düzenleyicisi dosyalarından için yaptığı gibi uygulama durumu değişti izleme proje dosyası için aynı sorumluluğunu vardır. Ortam çözümü değiştirilen durumunu işler, ancak değiştirilen durumu çözümü başvuruyor, ancak, bir proje dosyası veya öğelerinden gibi depolamaz herhangi bir nesnenin işlemelidir. Proje veya Düzenleyicisi öğeyi kalıcılığını yönetmekten sorumlu ise, genel olarak, daha sonra durumu değişti izleme uygulama için sorumludur.

 Yanıt olarak `IVsQueryEditQuerySave2::QueryEditFiles` çağrısı, ortam aşağıdakileri yapabilirsiniz:

-   Servis talebi Düzenleyicisi veya proje değiştirilmemiş (temiz) durumda kalması gereken değiştirmek için arama reddeder.

-   Belge verileri yeniden yüklenmesi belirtir. Bir proje için ortam proje için verileri yeniden yükleyecektir. Bir düzenleyici üzerinden disk verileri yeniden yüklemeniz gerekir, <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> uygulaması. Verileri yeniden yüklendiğinde her iki durumda da proje veya düzenleyicide bağlamda değiştirebilirsiniz.

 Uygun yükseltmek için karmaşık ve zor bir görev olduğundan `IVsQueryEditQuerySave2::QueryEditFiles` varolan bir kod tabanına üzerine çağrıları. Sonuç olarak, bu çağrıları Düzenleyicisi ve proje oluşturma sırasında tümleşik.

## <a name="request-permission-to-save-a-file"></a>Bir dosyayı kaydetmek için izin iste
 Bir proje veya Düzenleyicisi bir dosyayı kaydetmeden önce çağırmalısınız <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A> veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>. Proje dosyaları için bu çağrılardan bir proje dosyası kaydetmek ne zaman bilir çözümü tarafından otomatik olarak doldurulur. Düzenleyiciler sürece bu çağrıları yapmaktan sorumlu Düzenleyicisi uyarlamasını `IVsPersistDocData2` yardımcı işlevini kullanır <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A>. Düzenleyicinizi uyguluyorsa `IVsPersistDocData2` bu şekilde, ardından çağrısı içinde `IVsQueryEditQuerySave2::QuerySaveFile` veya `IVsQueryEditQuerySave2::QuerySaveFiles` sizin için yapılır.

> [!NOTE]
>  Her zaman bu erken önlem aramalarda — diğer bir deyişle, bir seferde düzenleyicinizi olduğunda bir iptal alabilir.

## <a name="request-permission-to-add-remove-or-rename-files-in-the-project"></a>Eklemek, kaldırmak veya projedeki dosyaları yeniden adlandırmak için izin iste
 Bir proje eklemek, yeniden adlandırmak veya bir dosya veya dizin kaldırmadan önce uygun çağırmalısınız `IVsTrackProjectDocuments2::OnQuery*` Ortamı'ndan izin istemek yöntemi. İzin verilir sonra projeyi işlemi tamamlayın ve ardından uygun çağıran `IVsTrackProjectDocuments2::OnAfter*` ortam işleminin tamamlandığını bildirmek için yöntem. Proje yöntemlerini çağırmalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> tüm dosyaları (örneğin, özel) ve yalnızca üst dosyaları için arabirim. Dosya aramaları zorunlu ancak dizin aramaları isteğe bağlıdır. Projenizin dizin bilgilerini sahip sonra uygun çağırmalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> yöntemleri, ancak bu bilgileri yok sonra ortamı dizin bilgilerini Infer.

 Proje yöntemlerini çağırmalıdır değil `IVsTrackProjectDocuments2` Proje Aç veya kapat. Bu bilgileri başlangıçta istediğiniz dinleyicileri bekle <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A> olay ve ihtiyaç duyduğunuz bilgileri bulmak için çözüm yineleme. Kapatma işlemi, bu bilgileri gerekli değildir. `IVsTrackProjectDocuments2` tablodan sağlanan <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>.

 Her Ekle, yeniden adlandırın ve kaldırma eylemi için bir `OnQuery*` yöntemi ve bir `OnAfter*` yöntemi. Çağrı `OnQuery*` eklemek için izninizi yöntemi yeniden adlandırın veya dosya veya dizin kaldırın. Çağrı `OnAfter*` dosya veya dizin eklenen, yeniden adlandırılmış veya kaldırıldı ve yeni durum proje durumu yansıtır sonra yöntemi.

## <a name="see-also"></a>Ayrıca Bkz.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>
- [Kaynak Denetimini Destekleme](../../extensibility/internals/supporting-source-control.md)