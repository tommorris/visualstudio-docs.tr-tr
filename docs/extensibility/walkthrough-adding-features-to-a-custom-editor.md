---
title: 'İzlenecek yol: Özellik için bir özel düzenleyici ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - add features
ms.assetid: bfe083b6-3e35-4b9c-ad4f-b30b9ff412a5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 14642a13553f3c4a09b86daa2d7638183fe7d8d9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-adding-features-to-a-custom-editor"></a>İzlenecek yol: Bir özel düzenleyici özellik ekleme
Özel bir düzenleyici oluşturduktan sonra daha fazla özelliği ekleyebilirsiniz.  
  
### <a name="to-create-an-editor-for-a-vspackage"></a>Bir VSPackage için bir düzenleyici oluşturmak için  
  
1.  Visual Studio Paketi proje şablonunu kullanarak bir özel düzenleyici oluşturma.  
  
     Daha fazla bilgi için bkz: [izlenecek yol: bir özel düzenleyici oluşturma](../extensibility/walkthrough-creating-a-custom-editor.md).  
  
2.  Tek bir görünüm veya birden çok görünüm desteklemek için düzenleyicinizi isteyip istemediğinize karar verin.  
  
     Destekleyen bir düzenleyici **yeni pencere** komutunu veya form görünümü ve kod görünümü, ayrı belge veri nesneleri ve belge görünümü nesneleri gerektirir. Yalnızca tek bir görünüm destekleyen bir düzenleyicide belge veri nesnesi ve belge görünüm nesnesi aynı nesne üzerinde uygulanabilir.  
  
     Birden çok görünüm bir örnek için bkz: [destekleyen birden çok belge görünümleri](../extensibility/supporting-multiple-document-views.md).  
  
3.  Bir düzenleyici üreteci uygulayarak uygulamak <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> arabirimi.  
  
     Daha fazla bilgi için bkz: [Düzenleyicisi oluşturucuları](../extensibility/editor-factories.md).  
  
4.  Yerinde etkinleştirme kullanmayı düzenleyicinizi istediğiniz veya belge görünümü nesne penceresi yönetmek için katıştırma Basitleştirilmiş olup olmadığını karar verin.  
  
     Yerinde etkinleştirme Düzenleyicisi penceresini bir ActiveX denetimi veya diğer etkin nesnesi, belge görünüm olarak sunarken basitleştirilmiş bir katıştırma Düzenleyicisi penceresini standart belge görünümü barındırır. Daha fazla bilgi için bkz: [Basitleştirilmiş katıştırma](../extensibility/simplified-embedding.md) ve [yerinde etkinleştirme](../extensibility/in-place-activation.md).  
  
5.  Uygulama <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> komutları işlemek için arabirim.  
  
6.  Belge Kalıcılık ve dış dosya değişikliklere yanıt aşağıdakileri yaparak sağlar:  
  
    1.  Dosya kalıcı hale getirmek için uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> ve <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> Düzenleyicisi'nin belge veri nesnesi üzerinde.  
  
    2.  Dış dosya değişikliklerine yanıt vermelerini uygulamak <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl> Düzenleyicisi'nin belge veri nesnesi üzerinde.  
  
        > [!NOTE]
        >  Çağrı `QueryService` üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx> gösteren bir işaretçi almak için `IVsFileChangeEx`.  
  
7.  Kaynak kodu denetimi ile belge düzenleme olaylarını koordinatı. Bunu yapmak için:  
  
    1.  Bir işaretçi elde `IVsQueryEditQuerySave2` çağırarak `QueryService` üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>.  
  
    2.  İlk olay Düzenle oluştuğunda çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> yöntemi.  
  
         Bu zaten kullanıma değil, dosyayı kullanıma denetlemek için kullanıcıya sorar. Hataları avert için bir "dosyası kullanıma değil" koşulu işlemek emin olun  
  
    3.  Benzer şekilde, dosyayı kaydetmeden önce arama <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A> yöntemi.  
  
         Bu yöntem henüz kaydedilmemişse veya son kaydedildiğinden beri değiştirilmişse dosyayı kaydetmek için kullanıcıya sorar.  
  
8.  Etkinleştirme **özellikleri** Metin Düzenleyicisi'nde seçili özelliklerini görüntülemek için penceresi. Bunu yapmak için:  
  
    1.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> her zaman metin seçimi, geçirme uygulamanızda değişiklikleri <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>.  
  
    2.  Çağrı `QueryService` üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> gösteren bir işaretçi almak için hizmet <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>.  
  
9. Kullanıcıların öğeleri Düzenleyicisi arasında sürükleyip sağlamak ve **araç**, veya dış Düzenleyicileri (örneğin, Microsoft Word) arasında ve **araç**. Bunu yapmak için:  
  
    1.  Uygulama `IDropTarget` IDE düzenleyicinizi bir bırakma hedefi uyarmak için düzenleyicinizi üzerinde.  
  
    2.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser> düzenleyicinizi etkinleştirebilir ve öğelerini devre dışı bırakmak için Görünüm arabirimde **araç**.  
  
    3.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.ResetDefaults%2A> ve arama `QueryService` üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.SVsToolbox> gösteren bir işaretçi almak için hizmet <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> arabirimleri.  
  
         Bu yeni öğeler eklemek, VSPackage sağlar **araç**.  
  
10. Düzenleyici programınızın diğer isteğe bağlı özellikler istediğinize karar verin.  
  
    -   Düzenleyicinizi desteklemek istiyorsanız bulmak ve komutları yerini alır, uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>.  
  
    -   Belge Anahattı araç penceresi düzenleyicinizde kullanmak istiyorsanız, uygulama `IVsDocOutlineProvider`.  
  
    -   Durum çubuğu düzenleyicinizde kullanmak istiyorsanız, uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> ve arama `QueryService` için <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> gösteren bir işaretçi almak için `IVsStatusBar`.  
  
         Örneğin, bir düzenleyicide satır görüntüleyebilen / sütun bilgileri, seçim modunu (akış / kutusuna) ve ekleme modu (ekleme / OVERSTRIKE).  
  
    -   Düzenleyicinizi desteklemek istiyorsanız `Undo` komutu, önerilen yöntem, OLE geri alma yöneticisi modeli kullanmaktır. Alternatif olarak, düzenleyici tanıtıcı olabilir `Undo` doğrudan komutu.  
  
11. Kayıt defteri VSPackage, menüler, düzenleyici ve diğer özellikler için GUID'ler gibi bilgileri oluşturun.  
  
     Bir düzenleyici düzgün kaydetme göstermek için .rgs dosya komut dosyanıza koyabilirsiniz kodunun genel bir örnek verilmiştir.  
  
    ```  
    NoRemove Editors  
    {  
          ForceRemove {...guidEditor...} = s 'RTF Editor'  
          {  
             val Package = s '{...guidVsPackage...}'  
             ForceRemove Extensions  
             {  
                val rtf = d 50  
             }  
          }  
    }  
    NoRemove Menus  
    {  
          val {...guidVsPackage...} = s ',203,11'  
    }  
    ```  
  
12. Bağlama duyarlı Yardım desteği uygulayın.  
  
     Bu öğeleri düzenleyicinizde F1 Yardımı ve dinamik Yardım penceresini desteği sağlamanıza izin verir. Bunun hakkında daha fazla bilgi için bkz: [nasıl yapılır: düzenleyicileri sağlamak bağlamının](../extensibility/how-to-provide-context-for-editors.md).  
  
13. Bir Otomasyon nesne modeli, düzenleyicisinden uygulayarak kullanıma `IDispatch` arabirimi.  
  
     Daha fazla bilgi için bkz: [otomasyon modeli katkıda bulunan](../extensibility/internals/contributing-to-the-automation-model.md).  
  
## <a name="robust-programming"></a>Güçlü Programlama  
  
-   IDE çağırır Düzenleyici örneği oluşturulduğunda <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> yöntemi. Düzenleyici birden çok görünüm destekliyorsa `CreateEditorInstance` belge verileri ve belge görünümü nesneleri oluşturur. Belge veri nesnesi zaten varsa açın, null olmayan bir `punkDocDataExisting` değeri iletilir `IVsEditorFactory::CreateEditorInstance`. Düzenleyici üreteci uygulamanız için uygun arabirimlerde sorgulayarak var olan bir belgeyi veri nesnesi uyumlu olup olmadığını belirlemeniz gerekir. Daha fazla bilgi için bkz: [destekleyen birden çok belge görünümleri](../extensibility/supporting-multiple-document-views.md).  
  
-   Basitleştirilmiş katıştırma yaklaşımı kullanırsanız, uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> arabirimi.  
  
-   Yerinde etkinleştirme kullanmaya karar verirseniz, aşağıdaki arabirimlerini uygular:  
  
     <xref:Microsoft.VisualStudio.OLE.Interop.IOleObject>  
  
     <xref:Microsoft.VisualStudio.OLE.Interop.IOleInPlaceActiveObject>  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent>  
  
    > [!NOTE]
    >  `IOleInPlaceComponent` Arabirimi OLE 2 menü birleştirme önlemek için kullanılır.  
  
     `IOleCommandTarget` Uygulama işleme komutları gibi **Kes**, **kopya**, ve **Yapıştır**. Uygularken `IOleCommandTarget`, düzenleyicinizi kendi komut menü yapısını tanımlamak için kendi .vsct dosyası gerekli olup olmadığını veya tarafından tanımlanan standart komutları uygulama durumunda karar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Genellikle, düzenleyiciler kullanın ve IDE'nin menüleri genişletmek ve kendi araç çubukları tanımlayın. Ancak, genellikle IDE'nin standart komut kümesini kullanmanın yanı sıra kendi belirli komutları tanımlamak bir düzenleyici için gereklidir. Bunu yapmak için düzenleyicinizi kullanır ve ardından yeni komutlar, bağlam menülerini, üst düzey menüleri ve araç çubuklarını .vsct dosyasında tanımlamak standart komutları bildirmeniz gerekir. Yerinde etkinleştirme Düzenleyicisi oluşturursanız, sonra uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent> ve OLE 2 menü birleştirme kullanmak yerine bir .vsct dosyayı düzenleyicide için menüleri ve araç çubuklarını tanımlayın.  
  
-   Menü komutu kullanıcı Arabiriminde doldurmak önlemek için mevcut komutları IDE'de yeni komutları inventing önce kullanmanız gerekir. Paylaşılan komutları SharedCmdDef.vsct ve ShellCmdDef.vsct tanımlanır. Bu dosyalar VisualStudioIntegration\Common\Inc alt varsayılan olarak yüklenir, [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] yükleme.  
  
-   `ISelectionContainer` hem tek hem de birden çok seçim hızlı. Seçilen her nesnenin olarak uygulanan bir `IDispatch` nesnesi.  
  
-   IDE uygulayan `IOleUndoManager` erişilebilen bir hizmet olarak bir <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> veya aracılığıyla örneği bir nesne olarak <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A>. Düzenleyici uygulayan `IOleUndoUnit` arabirimi her `Undo` eylem.  
  
-   İki yerde vardır özel bir düzenleyici Otomasyon nesneleri getirebilir:  
  
    -   `Document.Object`  
  
    -   `Window.Object`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomasyon modeli katkıda bulunan](../extensibility/internals/contributing-to-the-automation-model.md)   
 [Nasıl yapılır: içerik düzenleyicileri açısından sağlayın](../extensibility/how-to-provide-context-for-editors.md)