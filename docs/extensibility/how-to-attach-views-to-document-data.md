---
title: "Nasıl yapılır: veri belgelemek için görünümler ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - attach views to document data
ms.assetid: f92c0838-45be-42b8-9c55-713e9bb8df07
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 146303eebbd824342b000fb14b8dbf953c3f0523
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-attach-views-to-document-data"></a>Nasıl yapılır: veri belgelemek için görünümler ekleme
Yeni bir belge görünüm varsa, var olan bir belgeyi veri nesnesine eklemek mümkün olabilir.  
  
### <a name="to-determine-if-you-can-attach-a-view-to-an-existing-document-data-object"></a>Var olan bir belgeyi veri nesnesine ekleyebilirsiniz bir görünüm belirlemek için  
  
1.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>.  
  
2.  Uygulamanızda `IVsEditorFactory::CreateEditorInstance`, çağrı `QueryInterface` IDE çağırdığında mevcut belge veri nesnesi üzerinde `CreateEditorInstance` uygulaması.  
  
     Çağırma `QueryInterface` belirtilen varolan belge veri nesnesi incelemek sağlar `punkDocDataExisting` parametresi.  
  
     Sorgu gerekir tam arabirimleri ancak bağlıdır belgeyi açmayı Düzenleyicisi 4. adımda özetlendiği gibi.  
  
3.  Varolan belge veri nesnesi üzerinde uygun arabirimleri bulamazsanız düzenleyicinizi belge veri nesnesi Düzenleyicisi ile uyumsuz olduğunu belirten bir hata kodu dönün.  
  
     IDE'nin uygulamasında <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, belgeyi başka bir düzenleyicide açık olduğundan ve kapatmak isteyip istemediğinizi soran bir ileti kutusu size bildirir.  
  
4.  Bu belgeyi kapatırsanız, Visual Studio, düzenleyici üreteci için ikinci kez çağırır. Bu çağrı üzerinde `DocDataExisting` parametresi NULL değerine eşittir. Düzenleyici Üreteç uygulaması sonra belgeyi veri nesnesi kendi düzenleyicisinde açın.  
  
    > [!NOTE]
    >  Varolan bir belge veri nesneyle çalışıp çalışmadığını belirlemek için de arabirim uygulamasına özel bilgisini gösteren bir işaretçi gerçek atama tarafından kullanabilirsiniz [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] özel uygulamanızın sınıfı. Örneğin, tüm standart düzenleyicileri uygulamak `IVsPersistFileFormat`, devralan <xref:Microsoft.VisualStudio.OLE.Interop.IPersist>. Bu nedenle, çağırabilirsiniz `QueryInterface` için <xref:Microsoft.VisualStudio.OLE.Interop.IPersist.GetClassID%2A>, sınıf kimliği ve varolan belge veri nesnesi üzerinde sınıf kimliği uygulamanız 's eşleşiyorsa, sonra belge veri nesnesi ile çalışabilirsiniz.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Visual Studio uygulamanızı çağırdığında <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> yöntemi, bunu geçirir geri işaretçi mevcut belge veri nesne için `punkDocDataExisting` varsa parametresi. Döndürülen belge veri nesnesi inceleyin `punkDocDataExisting` belge veri nesnesi bu konudaki yordamının 4. adımda not özetlendiği gibi düzenleyici için uygun olup olmadığını belirlemek için. Uygun olan sonra Düzenleyici üreteci ikinci bir görünüm için veri kısmında özetlendiği gibi sağlamalıdır [destekleyen birden çok belge görünümleri](../extensibility/supporting-multiple-document-views.md). Aksi durumda, ardından uygun bir hata iletisi görüntülenmelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok belge görünümleri destekleme](../extensibility/supporting-multiple-document-views.md)   
 [Belge verileri ve belge görünümünde özel düzenleyiciler](../extensibility/document-data-and-document-view-in-custom-editors.md)