---
title: "Nasıl yapılır: bir kitaplık nesnesi Yöneticisi ile kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- libraries, registering with object manager
- IVsLibrary2 interface, registering library with object manager
- IVsSimpleLibrary2 interface, registering library with object manager
- IVsObjectManager2 interface, registering library with object manager
- libraries, symbol-browsing tools
ms.assetid: f124dd05-cb0f-44ad-bb2a-7c0b34ef4038
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6782e1cb84f4fbbe63a0e69a5c684d44ec7ccd21
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-register-a-library-with-the-object-manager"></a>Nasıl yapılır: bir kitaplık nesnesi Yöneticisi ile kaydetme
Simgeler gözatma araçları, gibi **sınıf görünümü**, **Nesne Tarayıcısı**, **çağrısı tarayıcı** ve **Bul simgesi sonuçlarınızı**, görüntülemenizi sağlar projenizi veya dış bileşenlere simgeler. Ad alanları, sınıflar, arabirimler, yöntemleri ve diğer dil öğeleri simgeleri içerir. Kitaplıkları bu simgeleri izlemek ve bunlara kullanıma [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] araçları verileri ile doldurur Nesne Yöneticisi.  
  
 Nesne Yöneticisi'ni, kullanılabilir tüm kitaplıkları izler. Her kitaplık sembolleri için simgenin tarama araçları sağlamadan önce ile Nesne Yöneticisi'ni kaydetmeniz gerekir.  
  
 Genellikle, bir VSPackage yüklediğinde, bir kitaplık kaydedin. Ancak, bunu başka bir zamanda gerektiğinde yapılabilir. VSPackage kapatıldığında kitaplığı kaydını silin.  
  
 Bir kitaplık kaydetmek için kullanın <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterLibrary%2A> yöntemi. Yönetilen kod kitaplığı durumunda kullanmak <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> yöntemi.  
  
 Bir kitaplık kaydını silmek için kullanılmasını <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.UnregisterLibrary%2A> yöntemi.  
  
 Nesne Yöneticisi ' ni bir başvuru almak için <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2>, geçirmek <xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager> kimliği için hizmet `GetService` yöntemi.  
  
## <a name="registering-and-unregistering-a-library-with-the-object-manager"></a>Kaydetme ve bir kitaplık nesnesi Yöneticisi ile kaydı siliniyor  
  
#### <a name="to-register-a-library-with-the-object-manager"></a>Bir kitaplık nesnesi Yöneticisi ile kaydetmek için  
  
1.  Bir kitaplığı oluşturun.  
  
    ```vb  
    Private m_CallBrowserLibrary As CallBrowser.Library = Nothing  
    Private m_nLibraryCookie As UInteger = 0  
    ' Create Library.  
    m_CallBrowserLibrary = New CallBrowser.Library()  
    ```  
  
    ```csharp  
    private CallBrowser.Library m_CallBrowserLibrary = null;  
    private uint m_nLibraryCookie = 0;  
    // Create Library.  
    m_CallBrowserLibrary = new CallBrowser.Library();  
  
    ```  
  
2.  Bir nesne için bir başvuru elde <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2> yazın ve arama <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> yöntemi.  
  
    ```vb  
    Private Sub RegisterLibrary()  
        If m_nLibraryCookie <> 0 Then  
            Throw New Exception("Library already registered with Object Manager")  
        End If  
  
        ' Obtain a reference to IVsObjectManager2 type object.  
        Dim objManager As IVsObjectManager2 = TryCast(GetService(GetType(SVsObjectManager)), IVsObjectManager2)  
        If objManager Is Nothing Then  
            Throw New NullReferenceException("GetService failed for SVsObjectManager")  
        End If  
  
        Try  
            Dim hr As Integer = objManager.RegisterSimpleLibrary(m_CallBrowserLibrary, m_nLibraryCookie)  
            Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr)  
        Catch e As Exception  
            ' Code to handle any CLS-compliant exception.  
            Trace.WriteLine(e.Message)  
            Throw  
        End Try  
    End Sub  
    ```  
  
    ```csharp  
    private void RegisterLibrary()  
    {  
        if (m_nLibraryCookie != 0)  
            throw new Exception("Library already registered with Object Manager");  
  
        // Obtain a reference to IVsObjectManager2 type object.  
        IVsObjectManager2 objManager =   
                          GetService(typeof(SVsObjectManager)) as IVsObjectManager2;  
        if (objManager == null)  
            throw new NullReferenceException("GetService failed for SVsObjectManager");  
  
        try  
        {  
            int hr =   
                objManager.RegisterSimpleLibrary(m_CallBrowserLibrary,   
                                                 out m_nLibraryCookie);  
                Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr);  
        }  
        catch (Exception e)  
        {  
            // Code to handle any CLS-compliant exception.  
            Trace.WriteLine(e.Message);  
            throw;  
        }  
    }  
  
    ```  
  
#### <a name="to-unregister-a-library-with-the-object-manager"></a>Bir kitaplık nesnesi Yöneticisi ile kaydını kaldırmak için  
  
1.  Bir nesne için bir başvuru elde <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2> yazın ve arama <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.UnregisterLibrary%2A> yöntemi.  
  
    ```vb  
    Private Sub UnregisterLibrary()  
        If m_nLibraryCookie <> 0 Then  
            ' Obtain a reference to IVsObjectManager2 type object.  
            Dim objManager As IVsObjectManager2 = TryCast(GetService(GetType(SVsObjectManager)), IVsObjectManager2)  
            If objManager Is Nothing Then  
                Throw New NullReferenceException("GetService failed for SVsObjectManager")  
            End If  
  
            Try  
                objManager.UnregisterLibrary(m_nLibraryCookie)  
            Catch e As Exception  
                ' Code to handle any CLS-compliant exception.  
                Trace.WriteLine(e.Message)  
                Throw  
            Finally  
                m_nLibraryCookie = 0  
            End Try  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void UnregisterLibrary()  
    {  
        if (m_nLibraryCookie != 0)  
        {  
            // Obtain a reference to IVsObjectManager2 type object.  
            IVsObjectManager2 objManager = GetService(typeof(SVsObjectManager)) as IVsObjectManager2;  
            if (objManager == null)  
                throw new NullReferenceException("GetService failed for SVsObjectManager");  
  
            try  
            {  
                objManager.UnregisterLibrary(m_nLibraryCookie);  
            }  
            catch (Exception e)  
            {  
                // Code to handle any CLS-compliant exception.  
                Trace.WriteLine(e.Message);  
                throw;  
            }  
            finally  
            {  
                m_nLibraryCookie = 0;  
            }  
        }  
    }  
  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti genişletilebilirliği](../../extensibility/internals/legacy-language-service-extensibility.md)   
 [Simgenin tarama araçları destekleme](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [Nasıl yapılır: kullanıma nesnesi Yöneticisi kitaplığı tarafından sağlanan simgelerin listeler](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)