---
title: 'Nasıl yapılır: dosya değişiklik bildirimlerini bastır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - suppress file change notification
ms.assetid: 891c1eb4-f6d0-4073-8df0-2859dbd417ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 95821baec7f2f46a65e2ab0f0b0b78b0e397f2ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-suppress-file-change-notifications"></a>Nasıl yapılır: dosya değişiklik bildirimlerini bastır
Metin arabelleğini temsil eden fiziksel dosya değiştirildiğinde iletisiyle bir iletişim kutusu görüntüler **şu öğeler için değişiklikleri kaydetmek istiyor musunuz?** Bu dosya değişikliği bildirimi bilinir. Birçok değişiklikleri dosyaya kullanacaksanız, ancak, bu iletişim kutusunu tekrar tekrar görüntüleme hızlı bir şekilde rahatsız edici haline gelebilir.  
  
 Aşağıdaki yordamı kullanarak bu iletişim kutusunu program aracılığıyla gizleyebilirsiniz. Bunu yaparak, bir dosya hemen her zaman değişiklikleri kaydetmek için kullanıcıya sor zorunda kalmadan yeniden yükleyebilirsiniz.  
  
### <a name="to-suppress-file-change-notification"></a>Dosya değişikliği bildirimi gizlemek için  
  
1.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> hangi metin arabellek nesnesi açık dosyasıyla ilişkili olduğunu belirlemek için yöntem.  
  
2.  Doğrudan <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> yoksay bellekte elde ederek dosya değişiklikleri izleme nesnesi <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl> alanından arabirim <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> (belge veri) nesnesi ve ardından uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> yöntemiyle `fIgnore` parametresi kümesine `true`.  
  
3.  Yöntemleri çağırmak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> bellek içi güncelleştirmek için arabirimleri <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> (örneğin, bir alan bileşeniniz için eklendiğinde) dosya değişiklikleri olan nesne.  
  
4.  Diskteki dosya kullanıcı ediyor olabilir düzenlemeleri beklemedeki düşünmeden değişikliklerle güncelleştirin.  
  
     Bu şekilde, doğrudan zaman <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> nesne için dosya izleme sürdürmek için değişiklik bildirimleri, bellekte metin arabelleğini diğer bekleyen düzenlemeler yanı sıra oluşturulan değişiklikleri yansıtır. Diskteki dosya tarafından oluşturulan en son kod yansıtır ve herhangi bir daha önce kullanıcı tarafından yapılan değişiklikler kullanıcı düzenlenmiş kodda kaydedilir.  
  
5.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> bildirmek için yöntemi <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> ayarlayarak dosya değişiklik bildirimlerini için izlemeyi sürdürmek için nesne `fIgnore` parametresi `false`.  
  
6.  Kaynak kodu denetimi (SCC) durumunda olduğu gibi dosyanın birkaç değişiklik planlıyorsanız, dosya değişikliği bildirimlerini geçici olarak askıya almak için genel dosya değişikliği hizmeti bildirmeniz gerekir.  
  
     Örneğin, dosyayı yeniden zaman damgası değiştirirseniz, ayrı bir dosya olay değiştikçe yeniden yazma ve timestample işlemleri her sayısı gibi dosya değişiklik bildirimlerini askıya gerekir. Bunun yerine çağrı genel dosya değişikliği bildirimi etkinleştirmek için <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx.IgnoreFile%2A> yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki dosya değişikliği bildirimi Önle gösterilmiştir.  
  
```cpp  
//Misc. helper classes  
  
CSuspendFileChanges::CSuspendFileChanges(  
    /* [in] */ const CString& strMkDocument,   
    /* [in] */ BOOL fSuspendNow /* = TRUE */)   
:  
    m_strMkDocument(strMkDocument),  
    m_fFileChangeSuspended(FALSE)  
{  
    if(fSuspendNow)  
        Suspend();  
}  
CSuspendFileChanges::~CSuspendFileChanges()  
{  
    Resume();  
}  
void CSuspendFileChanges::Suspend()  
{  
    USES_CONVERSION;  
  
    // Prevent suspend from suspending more than once.  
    if(m_fFileChangeSuspended)  
        return;  
  
    IVsRunningDocumentTable* pRDT =   
      _VxModule.GetIVsRunningDocumentTable();  
    ASSERT(pRDT);  
    if (!pRDT)  
        return;  
  
    CComPtr<IUnknown> srpDocData;  
    VSCOOKIE vscookie = VSCOOKIE_NIL;  
    pRDT->FindAndLockDocument(RDT_NoLock, T2COLE(m_strMkDocument),    
      NULL, NULL, &srpDocData, &vscookie);  
    if ( (vscookie == VSCOOKIE_NIL) || !srpDocData)  
        return;  
    CComPtr<IVsFileChangeEx> srpIVsFileChangeEx;  
    HRESULT hr = _VxModule.QueryService(SID_SVsFileChangeEx,   
      IID_IVsFileChangeEx, (void **)&srpIVsFileChangeEx);  
    if (SUCCEEDED(hr) && srpIVsFileChangeEx)  
    {  
        m_fFileChangeSuspended = TRUE;  
        srpIVsFileChangeEx->IgnoreFile(NULL, m_strMkDocument, TRUE);   
        srpDocData->QueryInterface(IID_IVsDocDataFileChangeControl,   
          (void**)&m_srpIVsDocDataFileChangeControl);  
        if(m_srpIVsDocDataFileChangeControl)  
            m_srpIVsDocDataFileChangeControl->IgnoreFileChanges(TRUE);  
    }  
}  
void CSuspendFileChanges::Resume()  
{  
    if(!m_fFileChangeSuspended)  
        return;  
  
    CComPtr<IVsFileChangeEx> srpIVsFileChangeEx;  
    HRESULT hr = _VxModule.QueryService(SID_SVsFileChangeEx,   
      IID_IVsFileChangeEx, (void **)&srpIVsFileChangeEx);  
    if (SUCCEEDED(hr) && srpIVsFileChangeEx)  
  
    srpIVsFileChangeEx->IgnoreFile(NULL, m_strMkDocument, FALSE);   
    if(m_srpIVsDocDataFileChangeControl)  
        m_srpIVsDocDataFileChangeControl->IgnoreFileChanges(FALSE);  
    m_fFileChangeSuspended = FALSE;  
    m_srpIVsDocDataFileChangeControl.Release();  
}  
// Misc. helper classes  
```  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Ardından durumunuz dosyaya SCC, durumunda olduğu gibi birden çok değişikliği içeriyorsa belge verileri için dosya değişiklikleri izlemeye devam uyarmadan önce genel dosya değişiklik bildirimlerini sürdürme önemlidir.