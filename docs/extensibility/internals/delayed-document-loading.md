---
title: Belge yükleme Gecikmeli | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: fb07b8e2-a4e3-4cb0-b04f-8eb11c491f35
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc10d7807633433b38fa8587d41c2ac3c0273ebe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="delayed-document-loading"></a>Belge yüklemesi ertelendi
Bir kullanıcı bir Visual Studio çözümü açana, ilişkili belgelere çoğunu hemen yüklü değil. Belge pencere çerçevesi başlatma bekleyen durumunda oluşturulur ve (bir saplama çerçeve olarak adlandırılır) bir yer tutucu belge çalıştıran belge Table'nın (RDT) yerleştirilir.  
  
 Uzantınızı gereksiz yere yüklenmeden önce belgeleri öğelerinde sorgulayarak yüklenecek proje belgelerin neden olabilir. Bu, Visual Studio için genel bellek alanını artırabilir.  
  
## <a name="document-loading"></a>Belge yükleme  
 Kullanıcı belge örneğin pencere çerçevesi sekmesi seçilerek eriştiğinde saplama çerçeve ve belge tam olarak başlatılır. Belge, belgenin verileri, belge verileri doğrudan edinmeye RDT erişme veya aşağıdaki çağrıları birini yaparak RDT dolaylı olarak erişmek ister bir uzantı tarafından da başlatılabilir:  
  
-   Pencere çerçevesi yöntemi göster: <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A>.  
  
-   GetProperty yöntemi pencere çerçevesi <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> herhangi bir aşağıdaki özellikleri:  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
 Yönetilen kod uzantınızı kullanıyorsa, değil çağırmalısınız <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> emin olmadığınız sürece belge başlatma bekleyen durumda değil veya tam olarak başlatılması için belgenin istediğiniz... Bu yöntem her zaman belge döndürür olmasıdır gerekirse oluşturma, veri nesnesi. Bunun yerine, IVsRunningDocumentTable4 arabirimde yöntemlerden birini çağırmalıdır.  
  
 Uzantınızı C++ kullanıyorsa, geçirebilirsiniz `null` istemediğiniz parametreler için.  
  
 İlgili özelliklerini isteyin önce aşağıdaki yöntemlerden birini çağırarak gereksiz belge yükleme önleyebilirsiniz: önce diğer özellikler için isteyin.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> kullanarak <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID6>.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A>. Bu yöntem bir <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4> için bir değer içeren nesnesinin <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4> belgeyi henüz başlatılmamış durumunda.  
  
 Bir belgenin belge tam olarak başlatıldığında RDT olayı için abone olarak yüklendiğinde, öğrenebilirsiniz. İki olasılık vardır:  
  
-   Olay iç havuz uyguluyorsa <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2>, abone olabilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2.OnAfterAttributeChangeEx%2A>,  
  
-   Aksi takdirde için abone olabilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterAttributeChange%2A>.  
  
 Bir kuramsal belge erişim senaryo verilmiştir. Bir Visual uzantısı açık belgeler hakkında bazı bilgileri görüntülemek istediğiniz Studio örneği için düzenleme kilit sayısı ve belge veriler hakkında bir şey. RDT kullanarak belgeler numaralandırır <xref:Microsoft.VisualStudio.Shell.Interop.IEnumRunningDocuments>, daha sonra çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> düzenleme kilit sayısı ve belge verileri almak için her belge için. Belge başlatma bekleyen durumdaysa belge verileri isteyen, gereksiz yere başlatılması neden olur.  
  
 Bunu yapmak için daha etkin bir şekilde bu kullanmaktır <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentEditLockCount%2A> düzenleme kilit sayısı almak ve daha sonra kullanmak için <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A> belge başlatılmış olup olmadığını belirlemek için. Bayrakları dahil etmezseniz <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4>, belge zaten başlatıldı ve belge verilerle isteyen <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentData%2A> gereksiz sıfırlamaları neden olmaz. Bayrakları eklerseniz <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4>, uzantı belge başlatılana dek belge verileri isteyen kaçınmalısınız. Bu OnAfterAttributeChange(Ex) olay işleyicisini algılanabilir.  
  
## <a name="testing-extensions-to-see-if-they-force-initialization"></a>Başlatma zorla görmek için uzantılarını test etme  
 Bir belge başlatılmış olup olmadığını, uzantınızı başlatma başlatılmasına gerek olmadığını öğrenmek zor olabilir belirtmek için hiçbir görünür işaret yoktur. Metin için tam olarak başlatılmadı her belgenin başlığını neden olduğundan doğrulama kolaylaştırır bir kayıt defteri anahtarı ayarlayabilirsiniz `[Stub]` başlık.  
  
 İçinde **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0\BackgroundSolutionLoad]**ayarlayın **StubTabTitleFormatString** için **{0} [saplama]**.