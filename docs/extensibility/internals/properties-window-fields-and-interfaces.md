---
title: "Özellikler penceresi alanları ve arabirimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Properties window, fields and interfaces
ms.assetid: 0328f0e5-2380-4a7a-a872-b547cb775050
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1f238cceb189723e3ec10fbf8db4abbd9675ae21
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-window-fields-and-interfaces"></a>Özellikler penceresi alanları ve arabirimleri
Hangi bilgilerin görüntüleneceğini belirlemek seçim için model **özellikleri** penceresi IDE'de odaklanmış penceresi dayanır. Her pencere ve nesneyi seçili penceresinde genel seçimi bağlamına gönderilir, Seçim bağlam nesnesi olabilir. Bu pencere odağa sahip olduğunda ortamı genel seçimi bağlam pencere çerçevesi değerlerle güncelleştirir. Bu nedenle odak değiştiğinde, Seçim bağlam yapar.  
  
## <a name="tracking-selection-in-the-ide"></a>IDE içinde izleme seçimi  
 Pencere çerçevesi veya IDE tarafından sahip olunan site adı verilen bir hizmeti sahip <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>. Aşağıdaki adımlar başka bir açık penceresine odak değiştirmenin ya da farklı proje öğesinde seçerek kullanıcı neden bir seçim içindeki bir değişiklik nasıl gösterir **Çözüm Gezgini**, görüntüleneniçeriğideğiştirmekiçinuygulanması **Özellikler** penceresi.  
  
1.  Seçilen pencere çağrılarında tarihli, VSPackage tarafından oluşturulan nesne <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> olmasını <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> çağırma <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>.  
  
2.  Seçili pencere tarafından sağlanan seçim kapsayıcısı kendi oluşturur <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> nesnesi. Seçim değişiklikleri VSPackage çağırdığında <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> ortamında, tüm dinleyiciler bildirmek için de dahil olmak üzere **özellikleri** değişikliği penceresi. Ayrıca, yeni seçimi ilgili hiyerarşi ve madde bilgilerine erişim sağlar.  
  
3.  Çağırma <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> ve seçilen hiyerarşi öğelerde geçirme `VSHPROPID_BrowseObject` parametresi doldurur <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> nesnesi.  
  
4.  Bir nesne türetilmiş [IDispatch arabirimi](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) için döndürülen <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> İstenen öğe ve ortam içine saran bir <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> (aşağıdaki adıma bakın). Çağrı başarısız olursa, ortam, ikinci çağrıda bulunur. `IVsHierarchy::GetProperty`, seçim kapsayıcısı geçirme <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> hiyerarşi öğesi veya öğeleri sağlayın.  
  
     Projenizi VSPackage oluşturmaz <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> ortamı tarafından sağlanan penceresi VSPackage, bunu uyguladığı için (örneğin, **Çözüm Gezgini**) oluşturur <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> kendi adına.  
  
5.  Ortam yöntemlerini çağırır <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> temel nesneleri almak için `IDispatch` doldurmak için arabirimi **özellikleri** penceresi.  
  
 Bir değer olduğunda **özellikleri** penceresi değiştirildiğinde, VSPackages uygulamak `IVsTrackSelectionEx::OnElementValueChangeEx` ve `IVsTrackSelectionEx::OnSelectionChangeEx` öğesi değerine değişikliği bildirmek için. Ortam sonra çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> veya <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> görüntülenen bilgileri korumak için **özellikleri** penceresi özellik değerleri ile eşitlenmiş. Daha fazla bilgi için bkz: [güncelleştirme özellik değerlerini Özellikleri penceresinde](#updating-property-values-in-the-properties-window).  
  
 Farklı bir seçerek yanı sıra öğesi proje **Çözüm Gezgini** öğeyle ilişkili özellikleri görüntülemek için de kullanılabilir açılan listeyi kullanarak bir form veya belge penceresi içinde farklı bir nesne seçebilirsiniz **Özellikleri** penceresi. Daha fazla bilgi için bkz: [Özellikler penceresini nesne listesi](../../extensibility/internals/properties-window-object-list.md).  
  
 Bilgi görüntülendiği şekilde değiştirebilirsiniz **özellikleri** penceresi kılavuzdan alfabetik kategorik için ve, varsa, ayrıca seçili bir nesne için bir özellik sayfası üzerindeuygundüğmeleretıklayarakaçabilirsiniz **Özellikler** penceresi. Daha fazla bilgi için bkz: [Özellikler penceresini düğmelerini](../../extensibility/internals/properties-window-buttons.md) ve [özellik sayfaları](../../extensibility/internals/property-pages.md).  
  
 Son olarak, listenin sonuna **özellikleri** penceresinde seçili alanının açıklaması de bulunur **özellikleri** penceresi kılavuz. Daha fazla bilgi için bkz: [alma alan açıklamaları Özellikler penceresinde](#getting-field-descriptions-from-the-properties-window).  
  
## <a name="updating-property-values-in-the-properties-window"></a>Özellik değerlerini Özellikleri penceresinde güncelleştiriliyor
Tutmak için iki yolla **özellikleri** penceresi özellik değeri değişiklikleri ile eşitlenmiş. İlk çağırmaktır <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> ortamı tarafından sağlanan araç ve belge pencereleri oluşturulmasını ve erişim de dahil olmak üzere temel Pencereleme işlevine erişim sağlayan arabirim. Aşağıdaki adımlar bu eşitleme işlemi açıklar.  
  
### <a name="updating-property-values-using-ivsuishell"></a>Özellik değerlerini IVsUIShell kullanarak güncelleştirme  
  
#### <a name="to-update-property-values-using-the-ivsuishell-interface"></a>IVsUIShell arabirimini kullanarak özellik değerleri güncelleştirmek için  
  
1.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> (aracılığıyla <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> hizmeti) projeleri, bu VSPackages kurduğunda veya düzenleyicileri ihtiyacınız oluşturmak veya windows aracı veya belge numaralandırmak.  
  
2.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.RefreshPropertyBrowser%2A> tutmak için **özellikleri** penceresi özellik değişikliklerini bir proje ile senkronize (veya diğer tarafından taranan seçili nesnenin **özellikleri** penceresi) Uygulamaolmadan<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> ve tetikleme <xref:Microsoft.VisualStudio.OLE.Interop.IPropertyNotifySink.OnChanged%2A> olaylar.  
  
3.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> yöntemleri <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.AdviseHierarchyEvents%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.UnadviseHierarchyEvents%2A> kurmak ve, sırasıyla uygulamak için istemci bildirimini hiyerarşi gerektirmeden hiyerarşi olayların devre dışı bırakmak için <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>.  
  
### <a name="updating-property-values-using-iconnection"></a>Iconnection kullanarak özellik değerleri güncelleştiriliyor  
 Korumak için ikinci yol **özellikleri** özellik değeri değişiklikleri ile eşitlenmiş penceredir uygulamak için `IConnection` giden arabirimleri varlığını göstermek için bağlanılabilirlik nesne üzerinde. Özellik adı yerelleştirme istiyorsanız, nesnesinden türetilen <xref:System.ComponentModel.ICustomTypeDescriptor>. <xref:System.ComponentModel.ICustomTypeDescriptor> Uygulama döndürdüğü özellik tanımlayıcılarının değiştirebilir ve bir özellik adını değiştirin. Açıklama yerelleştirme için türetilen bir öznitelik oluşturun <xref:System.ComponentModel.DescriptionAttribute> ve Description özelliği geçersiz.  
  
#### <a name="considerations-in-implementing-the-iconnection-interface"></a>Iconnection arabirimini uygulayan ilişkin düşünceler  
  
1.  `IConnection`olan bir numaralandırıcı alt nesne erişim sağlayan <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> arabirimi. Ayrıca tüm bağlantı noktası alt nesnelerin erişim sağlayan her hangi uygulayan <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> arabirimi.  
  
2.  Herhangi bir Gözat nesnesi uygulamak için sorumlu olduğu bir <xref:Microsoft.VisualStudio.OLE.Interop.IPropertyNotifySink> olay. **Özellikleri** penceresi öneri olay aracılığıyla ayarlamak için `IConnection`.  
  
3.  İsteğe bağlı olarak kaç bağlantıları (bir veya daha fazla) kendi uygulamasında sağlayan bir bağlantı noktası denetimleri <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A>. Yalnızca bir arabirim sağlayan bir bağlantı noktası döndürebilir <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL> gelen <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.EnumConnections%2A> yöntemi.  
  
4.  Bir istemci çağırabilirsiniz `IConnection` sahip numaralandırıcısı alt nesneye erişim elde etmek için arabirim <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> arabirimi. <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> Arabirimi sonra çağrılabilir her giden bir arabirim kimliği'ni (IID) için bağlantı noktaları numaralandırılamıyor.  
  
5.  `IConnection`bağlantı noktası alt nesneler ile erişim sağlamak için çağrılabilir <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> her giden IID için arabirim. Aracılığıyla <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> arabirimi, bir istemci başlatıldığında veya bir danışma döngü bağlanılabilirlik nesne ve istemcinin kendi eşitleme ile sona erer. İstemci ayrıca çağırabilirsiniz <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> bir Numaralayıcı nesnesi ile almak için arabirimi <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnections> hakkında bilgi sahibi bağlantıları numaralandırmak için arabirim.  
  
## <a name="getting-field-descriptions-from-the-properties-window"></a>Özellikler penceresinden alan açıklamaları alma
Ekranın alt kısmındaki **özellikleri** penceresinde, bir açıklama alanı, seçili özellik alanıyla ilgili bilgileri görüntüler. Bu özellik varsayılan olarak açıktır. Açıklama alanı gizlemek istiyorsanız, sağ **özellikleri** penceresini açın ve **açıklama**. Bunun yapılması ayrıca kaldırır onay işareti yanına **açıklama** menü penceresinin başlık. Geçiş yapmak için aynı adımları izleyerek alan yeniden görüntüleyebilirsiniz **açıklama** yeniden açın.  
  
 Açıklama alanı bilgilerinde geldiği <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>. Her yöntem, arabirim, coclass'ı ve benzeri bir yerelleştirilmemiş olabilir `helpstring` tür kitaplığı özniteliği. **Özellikleri** penceresi alır, dizeden <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo.GetDocumentation%2A>.  
  
### <a name="to-specify-localized-help-strings"></a>Yerelleştirilmiş Yardım dizeleri belirtmek için  
  
1.  Ekleme `helpstringdll` özniteliği için tür kitaplığı kitaplık deyiminde (`typelib`).  
  
    > [!NOTE]
    >  Bu tür kitaplığı bir nesne kitaplığı (.olb) dosyasında ise isteğe bağlı bir adımdır.  
  
2.  Belirtin `helpstringcontext` dizeleri için öznitelikler. Ayrıca belirtebilirsiniz `helpstring` öznitelikleri.  
  
     Bu öznitelikler ayrı `helpfile` ve `helpcontext` gerçek .chm dosya Yardım konularında bulunan öznitelikler.  
  
 Vurgulanan özellik adı için görüntülenecek açıklama bilgileri almak için **özellikleri** penceresi çağrıları <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetDocumentation2%2A> seçili özellik için istenen belirtme `lcid` için özniteliği Çıkış dizesi. Dahili olarak, <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2> belirtilen .dll dosyasını bulur `helpstringdll` özniteliği ve çağrıları `DLLGetDocumentation` belirtilen bağlamı, .dll dosyasıyla üzerinde ve `lcid` özniteliği.  
  
 İmza ve uyarlamasını `DLLGetDocumentation` şunlardır:  
  
```cpp  
STDAPI DLLGetDocumentation  
(  
   ITypeLib * /* ptlib */,  
   ITypeInfo * /* ptinfo */,  
   LCID /* lcid */,  
   DWORD dwCtx,  
   BSTR * pbstrHelpString  
);  
```  
  
 `DLLGetDocumentation` İşlevi DLL için .def dosyasında tanımlanan bir verme olması gerekir.  
  
 Dahili olarak, aslında bir DLL olduğu bir .olb dosyası oluşturulur. Bir kaynak, tür kitaplığı (.tlb) dosyası ve bir dışarı aktarılan işlevi bu DLL içeren `DLLGetDocumentation`.  
  
 .Olb dosyaları, söz konusu olduğunda `helpstringdll` .tlb dosyası içeren dosyanın olduğundan özniteliği isteğe bağlıdır.  
  
 Dizelerin görünmesine almak için **açıklamaları** bölmesinde, bu nedenle, yapmanız gereken en düşük belirtin `helpstring` tür kitaplığı özniteliği. Bu dizelerin yerelleştirilmesi istiyorsanız belirtmek zorunda `helpstringdll` (isteğe bağlı) özniteliği ve `helpstringcontext` (gerekli) özniteliği ve uygulama `DLLGetDocumentation`.  
  
 Yerelleştirilmiş IDL'ın aracılığıyla bilgi alınırken zaman uygulanması gereken ek arabirim vardır `helpstringcontext` özniteliği ve `DLLGetDocumentation`.  
  
 Yerelleştirilmiş ad ve açıklama bir özelliğin almanın başka bir uygulama tarafından yoludur <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.GetLocalizedPropertyInfo%2A>. Bu yöntemin kullanımı ile ilgili daha fazla bilgi için bkz: [Özellikler penceresini alanları ve arabirimleri](../../extensibility/internals/properties-window-fields-and-interfaces.md).  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellikleri Genişletme](../../extensibility/internals/extending-properties.md)