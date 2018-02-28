---
title: "Eski kod düzenleyicisine uyarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - adapters
ms.assetid: a208d38e-9bea-41c9-9fe2-38bd86a359cb
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ef1bce81e20772660a6074c15bd5dad494804373
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="adapting-legacy-code-to-the-editor"></a>Eski kod düzenleyicisine uyarlama
Visual Studio düzenleyicisinde var olan kodu bileşenlerini erişmek için birçok özelliğe sahiptir. Aşağıdaki yönergeler, bir MEF olmayan bileşeni, düzenleyici işlevselliği kullanmak için örneğin, bir VSPackage, uyum gösterilmektedir. Yönergeler ayrıca bağdaştırıcıları Düzenleyicisi Hizmetleri yönetilen ve yönetilmeyen kodu almak için nasıl kullanılacağını gösterir.  
  
## <a name="editor-adapters"></a>Düzenleyici bağdaştırıcıları  
 Düzenleyici bağdaştırıcıları veya dolgular, olan sınıfları ve arabirimleri de kullanıma Düzenleyicisi nesneleri için sarmalayıcılar <xref:Microsoft.VisualStudio.TextManager.Interop> API. Örneğin Düzenleyicisi olmayan hizmetleri arasında taşımak için bağdaştırıcılar, Visual Studio Kabuk komutları ve Düzenleyicisi Hizmetleri'ni kullanabilirsiniz. (Düzenleyici Visual Studio şu anda nasıl barındırılan budur.) Bağdaştırıcıları ayrıca Visual Studio'da düzgün çalışması eski Düzenleyicisi ve dil hizmeti uzantılarını etkinleştirme.  
  
## <a name="using-editor-adapters"></a>Düzenleyici bağdaştırıcıları kullanmak  
 <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService> Yeni Düzenleyicisi arabirimleri ve eski arabirimler arasında geçiş yapma yöntemleri ve ayrıca bağdaştırıcıları oluşturma yöntemleri sağlar.  
  
 Bu hizmet bir MEF Bileşeni bölümünde kullanıyorsanız, hizmeti aşağıdaki gibi içeri aktarabilirsiniz.  
  
```  
[Import(typeof(IVsEditorAdaptersFactoryService))]  
internal IVsEditorAdaptersFactoryService editorFactory;  
```  
  
 Bu hizmet bir MEF olmayan bileşeni kullanmak istiyorsanız, bu konunun devamındaki "Kullanarak Visual Studio Düzenleyicisi Hizmetleri bir olmayan MEF Bileşeni" bölümündeki yönergeleri izleyin.  
  
## <a name="switching-between-the-new-editor-api-and-the-legacy-api"></a>Yeni Düzenleyicisi API ve eski API arasında geçiş yapma  
 Eski bir arabirimle Düzenleyicisi nesneyi arasında geçiş yapmak için aşağıdaki yöntemleri kullanın.  
  
|Yöntem|Dönüştürme|  
|------------|----------------|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetBufferAdapter%2A>|Dönüştüren bir <xref:Microsoft.VisualStudio.Text.ITextBuffer> için bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetDataBuffer%2A>|Dönüştüren bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> için bir <xref:Microsoft.VisualStudio.Text.ITextBuffer>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetDocumentBuffer%2A>|Dönüştüren bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> için bir <xref:Microsoft.VisualStudio.Text.ITextBuffer>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetViewAdapter%2A>|Dönüştüren bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView> için bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.GetWpfTextView%2A>|Dönüştüren bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> için bir <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>.|  
  
## <a name="creating-adapters"></a>Bağdaştırıcıları oluşturma  
 Eski arabirimleri için bağdaştırıcıları oluşturmak için aşağıdaki yöntemleri kullanın.  
  
|Yöntem|Dönüştürme|  
|------------|----------------|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsCodeWindowAdapter%2A>|Oluşturur bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextBufferAdapter%2A>|Oluşturur bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> belirtilen için <xref:Microsoft.VisualStudio.Utilities.IContentType>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextBufferAdapter%2A>|Oluşturur bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextBufferCoordinatorAdapter%2A>|Oluşturur bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextViewAdapter%2A>|Oluşturur bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> için bir <xref:Microsoft.VisualStudio.Text.Editor.ITextViewRoleSet>.|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService.CreateVsTextViewAdapter%2A>|Oluşturur bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.|  
  
## <a name="creating-adapters-in-unmanaged-code"></a>Yönetilmeyen kod içinde bağdaştırıcıları oluşturma  
 Yerel olarak kayıtlı tüm bağdaştırıcısı sınıfları birlikte creatable ve kullanarak oluşturulabilir `VsLocalCreateInstance()` işlevi.  
  
 Tüm bağdaştırıcıları vsshlids.h dosyasında tanımlanan GUID'ler kullanılarak oluşturulan... Visual Studio SDK yükleme klasörü \VisualStudioIntegration\Common\Inc\. VsTextBufferAdapter örneği oluşturmak için aşağıdaki kodu kullanın.  
  
```  
IVsTextBuffer *pBuf = NULL;  
VsLocalCreateInstance(CLSID_VsTextBuffer, NULL, CLSCTX_INPROC_SERVER, IID_IVsTextBuffer, (void**)&pBuf);  
```  
  
## <a name="creating-adapters-in-managed-code"></a>Yönetilen kodda bağdaştırıcıları oluşturma  
 Yönetilen kodda, bağdaştırıcıları yönetilmeyen kod için açıklanan aynı şekilde birlikte oluşturabilirsiniz. Oluşturma ve bağdaştırıcıları ile etkileşime olanak sağlayan bir MEF hizmetini de kullanabilirsiniz. Bu şekilde, bir bağdaştırıcıyı almaya birlikte oluşturduğunuzda olandan daha ayrıntılı denetim sağlar.  
  
#### <a name="to-create-an-adapter-for-ivstextview"></a>Bir bağdaştırıcı için IVsTextView oluşturmak için  
  
1.  Microsoft.VisualStudio.Editor.dll bir başvuru ekleyin. Olduğundan emin olun `CopyLocal` ayarlanır `false`.  
  
2.  Örneği <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>gibi.  
  
    ```  
    using Microsoft.VisualStudio.Editor;  
    ...  
    IVsEditorAdaptersFactoryService adapterFactoryService = ComponentModel.GetService<IVsEditorAdaptersFactoryService>();  
    ```  
  
3.  Çağrı `CreateX()` yöntemi.  
  
    ```  
    adapterFactoryService.CreateTextViewAdapter(textView);  
    ```  
  
## <a name="using-the-visual-studio-editor-directly-from-unmanaged-code"></a>Yönetilmeyen kod doğrudan Visual Studio Düzenleyicisi'ni kullanarak  
 COM aranabilir arabirimleri Microsoft.VisualStudio.Platform.VSEditor ad alanı ve Microsoft.VisualStudio.Platform.VSEditor.Interop ad IVx * arabirimleri olarak kullanıma sunar. Örneğin, Microsoft.VisualStudio.Platform.VSEditor.Interop.IVxTextBuffer arabirimi COM sürümüdür <xref:Microsoft.VisualStudio.Text.ITextBuffer> arabirimi. Gelen `IVxTextBuffer`, arabellek anlık görüntülere erişmek, arabellek değiştirmek, arabellek metin değişikliği olaylarını dinler ve izleme noktaları ve yayılma oluşturun. Aşağıdaki adımları nasıl erişeceğinizi gösterir bir `IVxTextBuffer` gelen bir `IVsTextBuffer`.  
  
#### <a name="to-get-an-ivxtextbuffer"></a>Bir IVxTextBuffer almak için  
  
1.  VSEditor.h dosyasında IVx * arabirimleri tanımı verilmiştir... Visual Studio SDK yükleme klasörü \VisualStudioIntegration\Common\Inc\.  
  
2.  Aşağıdaki kodu kullanarak metin arabelleğini başlatır `IVsUserData->GetData()` yöntemi. Aşağıdaki kodda, `pData` gösteren bir işaretçidir bir `IVsUserData` nesnesi.  
  
    ```  
    #include <textmgr.h>  
    #include <VSEditor.h>  
    #include <vsshlids.h>  
  
    CComPtr<IVsTextBuffer> pVsTextBuffer;  
    CComPtr<IVsUserData> pData;  
    CComPtr<IVxTextBuffer> pVxBuffer;  
    ...  
    if (SUCCEEDED(pVsTextBuffer->QueryInterface(IID_IVsUserData, &pData))  
    {  
        CComVariant vt;  
        if (SUCCEEDED(pData->GetData(GUID_VxTextBuffer, &vt)) &&  
        (vt.Type == VT_UNKNOWN) && (vt.punkVal != NULL))  
        {  
            vt.punkVal->QueryInterface(IID_IVxTextBuffer, (void**)&pVxBuffer);  
        }  
    }  
    ```  
  
## <a name="using-visual-studio-editor-services-in-a-non-mef-component"></a>Visual Studio düzenleyicisinde Hizmetleri bir MEF olmayan bileşeni kullanma  
 MEF kullanmayan varolan yönetilen kod bileşeni varsa ve Visual Studio düzenleyicisinde hizmetlerini kullanmak istediğiniz ComponentModelHost VSPackage içeren bütünleştirilmiş kodun bir başvuru ekleyin ve onun SComponentModel hizmeti alın.  
  
#### <a name="to-consume-visual-studio-editor-components-from-a-non-mef-component"></a>Visual Studio Düzenleyicisi bileşenleri bir MEF olmayan bileşenin kullanmak için  
  
1.  Microsoft.VisualStudio.ComponentModelHost.dll bütünleştirilmiş kodunda bir başvuru ekleyin... Visual Studio yükleme \Common7\IDE\ klasör. Olduğundan emin olun `CopyLocal` ayarlanır `false`.  
  
2.  Özel eklemek `IComponentModel` Visual Studio Düzenleyicisi Hizmetleri, aşağıdaki gibi kullanmak istediğiniz sınıf üyesine.  
  
    ```  
    using Microsoft.VisualStudio.ComponentModelHost;  
    ....  
    private IComponentModel componentModel;  
    ```  
  
3.  Bileşeniniz için başlatma yöntemini bileşen modelinde örneği oluşturur.  
  
    ```  
    componentModel =  
     (IComponentModel)Package.GetGlobalService(typeof(SComponentModel));  
    ```  
  
4.  Bundan sonra Visual Studio Düzenleyicisi Hizmetleri birini çağırarak alma `IComponentModel.GetService<T>()` istediğiniz hizmeti için yöntem.  
  
    ```  
    textBufferFactoryService =  
         componentModel.GetService<ITextBufferFactoryService>();     
    ```