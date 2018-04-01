---
title: Yeni veya değiştirilmiş davranışı Düzenleyicisi bağdaştırıcılarla | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - adapter behavior
ms.assetid: 5555b116-cfdb-4773-ba62-af80fda64abd
caps.latest.revision: 12
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c24b8c5520befcc204b59609b116d9d16ee26281
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="new-or-changed-behavior-with-editor-adapters"></a>Düzenleyici bağdaştırıcıları ile yeni veya değiştirilmiş davranışı
Visual Studio çekirdek Düzenleyicisi'ni önceki sürümlerinde karşı yazılmış kodun güncelleştirdiğiniz ve yeni API kullanmak yerine Düzenleyici bağdaştırıcıları (veya dolgular) kullanmayı düşünüyorsanız, düzenleyici bağdaştırıcıları davranışını aşağıdaki farklar dikkat etmeniz gerekir önceki çekirdek Düzenleyici göre.  
  
## <a name="features"></a>Özellikler  
  
#### <a name="using-setsite"></a>SetSite() kullanma  
 Çağırmalısınız <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite.SetSite%2A> zaman CoCreate metin arabelleğini metin görünümleri ve onlar üzerinde herhangi bir işlem gerçekleştirmeden önce windows kod. Ancak, bu kullanırsanız, gerekli değildir <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService> bu hizmetin Create() yöntemleri kendilerini bunları oluşturmak için <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.SetSite%2A>.  
  
#### <a name="hosting-ivscodewindow-and-ivstextview-in-your-own-content"></a>IVsCodeWindow ve IVsTextView kendi içeriği barındırma  
 Her ikisi de barındırabilir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> Win32 modunda veya WPF modunu kullanarak kendi içerik. Ancak, bazı farklar iki modda olduğunu göz önünde bulundurmanız.  
  
##### <a name="using-win32-and-wpf-versions-of-ivscodewindow"></a>IVsCodeWindow Win32 ve WPF sürümleri kullanma  
 Kod düzenleyicisini türetilir <xref:Microsoft.VisualStudio.Shell.WindowPane>, eski Win32 uygulayan <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> arabirim yanı sıra yeni WPF <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane> arabirimi. Kullanabileceğiniz <xref:Microsoft.VisualStudio.Shell.WindowPane.Microsoft%23VisualStudio%23Shell%23Interop%23IVsWindowPane%23CreatePaneWindow%2A> HWND tabanlı barındırma ortamı, oluşturmak için yöntemi veya <xref:Microsoft.VisualStudio.Shell.WindowPane.Microsoft%23VisualStudio%23Shell%23Interop%23IVsUIElementPane%23CreateUIElementPane%2A> bir WPF barındırma ortamı oluşturmak için yöntem. Temel alınan Düzenleyicisi her zaman WPF kullanır, ancak bu bölme doğrudan kendi içeriğinizi katıştırma, barındırma gereksinimlerinize uygun pencere bölmesine tür oluşturabilirsiniz.  
  
##### <a name="using-win32-and-wpf-versions-of-ivstextview"></a>IVsTextView Win32 ve WPF sürümleri kullanma  
 Ayarlayabileceğiniz bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> Win32 modu veya WPF modu.  
  
 Bir düzenleyici üreteci HWND içinde barındırılır varsayılan olarak bir metin görünümü, oluşturduğunda ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWindowHandle%2A> HWND döndürür. Bu mod, WPF denetimi içinde Düzenleyicisi katıştırmak için kullanmamalısınız.  
  
 Metin görünümü WPF moduna ayarlamak için çağırmalısınız <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.Initialize%2A> ve geçirin <xref:Microsoft.VisualStudio.TextManager.Interop.TextViewInitFlags3> başlatma biri de bayrakları gibi `InitView` parametresi. Alma <xref:System.Windows.FrameworkElement> çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane.CreateUIElementPane%2A>.  
  
 WPF modu Win32 modu iki yolla farklıdır. İlk olarak, metin görünümü bir WPF bağlamında barındırılabilir. Atama tarafından WPF bölmesinde erişebilirsiniz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> için <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane> ve çağırma <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElement.GetUIObject%2A>. İkinci, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWindowHandle%2A> hala yalnızca konumunu denetleyin ve odağı üzerinde ayarlamak için bir HWND, ancak bu HWND kullanılabilir döndürür. Düzenleyici penceresini nasıl boyar etkilemez olduğundan, bu HWND WM_PAINT iletiyi yanıtlamak için kullanmaması gerekir. Yalnızca yeni Düzenleyicisi kodu Geçişi bağdaştırıcıları yoluyla kolaylaştırmak için bu HWND mevcuttur. Kullanılamaz olduğunu önerilen `VIF_NO_HWND_SUPPORT` bileşeniniz döndürülen HWND sınırlamaları nedeniyle çalışmak bir HWND gerektiriyorsa `GetWindowHandle` bu modda çalışırken.  
  
#### <a name="passing-arrays-as-parameters-in-native-code"></a>Yerel kod parametre olarak dizileri geçirme  
 API eski Düzenleyicisi'nde bir dizi ve sayımına dahil parametrelere sahip birçok yöntem vardır. Örnekler şunlardır:  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.AppendViewOnlyMarkerTypes%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.RemoveViewOnlyMarkerTypes%2A>  
  
 Bu yöntemler yerel kodda arıyorsanız, aynı anda yalnızca tek bir öğe geçmesi gerekir. Birden fazla öğe geçirirseniz, çağrı, birincil birlikte çalışma uygulamasını sorunlar nedeniyle reddedilir.  
  
 Sorun yöntemleriyle daha karmaşık olduğu gibi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.SetIgnoreMarkerTypes%2A>. Bu yöntem her çağrıldığında yalnızca bu yöntemi üç kez üç farklı işaret türleriyle çağırmak mümkün değildir yoksayılan işaret türleri, önceki listesini temizler. Yalnızca remedy, bu yöntem yalnızca yönetilen kodda çağırmaktır.  
  
#### <a name="threading"></a>İş Parçacığı Oluşturma  
 Her zaman, arabellek bağdaştırıcısı kullanıcı Arabirimi iş parçacığından çağırmalısınız. Yönetilen koddan içine arama COM hazırlama atlayacaktır ve aramanız otomatik olarak kullanıcı Arabirimi iş parçacığına sıralanacağını değil anlamına gelir yönetilen bir nesnenin arabellek bağdaştırıcısıdır.  Arka plan iş parçacığından arabellek bağdaştırıcısı arıyorsanız, kullanmalısınız <xref:System.Windows.Threading.Dispatcher.Invoke%2A> veya benzer bir yöntem.  
  
#### <a name="lockbuffer-methods"></a>LockBuffer yöntemleri  
 Tüm LockBuffer() yöntemleri kullanım dışı bırakılmıştır. Örnekler şunlardır:  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.LockBuffer%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.LockBuffer%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.LockBuffer%2A>  
  
#### <a name="commit-events"></a>Olayları Yürüt  
 Commit olayları desteklenmez. Bu olayları öneren bir yöntemi çağrılırken bir hata kodu döndürmek yöntemin neden olur.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPreliminaryTextChangeCommitEvents>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFinalTextChangeCommitEvents>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUndoRedoClusterWithCommitEvents>  
  
#### <a name="texteditorevents"></a>TextEditorEvents  
 <xref:EnvDTE.TextEditorEvents> Artık, Commit() üzerinde kov. Bunun yerine her metin değişikliğinde kov.  
  
#### <a name="text-markers"></a>Metin işaretçileri  
 Çağırmalısınız <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker.Invalidate%2A> üzerinde <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker> nesneleri bunları kaldırdığınızda. Önceki sürümlerde, yalnızca işaretlerinin sürüm gerekli.  
  
#### <a name="line-numbers"></a>Satır numaraları  
 Yöntemlere çeşitli <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx>satır numaralarını temel arabellek satır numaralarını karşılık gelen, değil satır numaraları faktörün anahat oluşturma ve word-wrap, Visual Studio 2008 olduğu gibi.  
  
 Etkilenen yöntemleri (liste değildir kapsamlı) şunları içerir:  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.CenterLines%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetCaretPos%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetLineAndColumn%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetNearestPosition%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetPointOfLineColumn%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetTextStream%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWordExtent%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.PositionCaretForEditing%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.ReplaceTextOnLine%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.SetCaretPos%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.SetSelection%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.SetTopLine%2A>  
  
#### <a name="outlining"></a>Anahat Oluşturma  
 İstemcileri <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> kullanılarak eklenen bu anahat bölgeler görürsünüz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A>veya <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSessionEx.AddHiddenRegionsEx%2A>. Düzenleyici bağdaştırıcıları aracılığıyla ekli değil çünkü geçici bölgeler görmezsiniz. Benzer şekilde, bu istemciler Düzenleyicisi bağdaştırıcıları yerine yeni Düzenleyicisi kodu kullanarak (C# ve C++ dahil) dilleri tarafından eklenen bölgeler anahat oluşturma görmezsiniz.  
  
#### <a name="line-heights"></a>Satır yükseklik  
 Yeni düzenleyicisinde metin satırlarını yazı tipi boyutunu ve diğer satırlara göre satır taşıyabilir olası satır dönüşümler bağlı olarak farklı yükseklikte olabilir. Gibi yöntemler tarafından döndürülen satır yüksekliğini <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetLineHeight%2A> hiçbir satır dönüşümler uygulanan varsayılan yazı tipi boyutunu kullanarak satırının yüksekliği. Bu yüksekliği olabilir veya bir çizgi görünümünde gerçek yüksekliğini yansıtmayabilir.  
  
#### <a name="eventing-and-undo"></a>Olay ve geri alma  
 Yeni düzenleyicisinde görünümü oluşturma ve bir geri alma küme açık olduğunda bile olaylar sürekli olarak oluşturma gibi işlemler gerçekleştirmek devam eder. Bu kapatma kadar sonra bu işlemler geri kümesinin gerçekleştirmedi eski görünümleri farklı davranıştır.  
  
#### <a name="intellisense"></a>IntelliSense  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.UpdateTipWindow%2A> Yöntemi başarısız olur ya da uygulamayan bir sınıfta geçirirseniz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextTipWindow2> veya <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow3>. Sahip tarafından çizilmiş özel Win32 tarayıcınızı artık desteklenmemektedir.  
  
#### <a name="smarttags"></a>Akıllı etiketler  
 İle oluşturulan akıllı etiketleri için bağdaştırıcı desteği yoktur <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagData>, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagTipWindow>, ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagTipWindow2> arabirimleri.  
  
#### <a name="dte"></a>DTE  
 <xref:EnvDTE80.IncrementalSearch>uygulanmadı.  
  
## <a name="unimplemented-methods"></a>Uygulanmayan yöntemleri  
 Bazı yöntemler metin arabelleği bağdaştırıcısı, metin görünümü bağdaştırıcısı ve metin katman bağdaştırıcısı henüz geliştirilmemiştir.  
  
|Arabirim|Uygulanmadı|  
|---------------|---------------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|`Reload(false)`uygulanmadı.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.EnumSpans%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetBufferMappingModes%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.GetMarkerData%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.ReleaseMarkerData%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CanReplaceLines%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CopyLineText%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CreateTrackingPoint%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.EnumLayerMarkers%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetBaseBuffer%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetLengthOfLine%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetLineCount%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetLineText%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetMarkerData%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.LockBufferEx%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.MapLocalSpansToTextOriginatingLayer%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.ReleaseMarkerData%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.ReplaceLines%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.ReplaceLinesEx%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.UnlockBufferEx%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView.GetSelectedAtom%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetSelectionDataObject%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.PositionCaretForEditing%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.RestrictViewRange%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateViewFrameCaption%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.GetSmartTagRect%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.InvokeInsertionUI%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.SetHoverWaitTimer%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow.SetViewClassID%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.AfterCompletorCommit%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.BeforeCompletorCommit%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.Exec%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetContextLocation%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetServiceProvider%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSmartTagRect%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSubjectCaretPos%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSubjectSelection%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSubjectText%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.QueryStatus%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.ReplaceSubjectTextSpan%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.SetSubjectCaretPos%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.SetSubjectSelection%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.UpdateSmartTagWindow%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewIntellisenseHost>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewIntellisenseHost.SetSubjectFromPrimaryBuffer%2A>Anahat kullanıcı Arabirimi tarafından yoksayılan ancak bağdaştırıcılarında uygulanır.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenRegionEx>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenRegionEx.GetBannerAttr%2A>Anahat kullanıcı Arabirimi tarafından yoksayılan ancak bağdaştırıcılarında uygulanır.|