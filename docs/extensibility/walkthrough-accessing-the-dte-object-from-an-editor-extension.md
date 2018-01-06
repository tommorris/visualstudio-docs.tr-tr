---
title: "İzlenecek yol: bir düzenleyici uzantı DTE nesnesine erişim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - getting the DTE object
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: af14fa5f9a76e08a1fba3355e9391ce8229bd652
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-accessing-the-dte-object-from-an-editor-extension"></a>İzlenecek yol: bir düzenleyici uzantı DTE nesnesine erişim
VSPackages içinde çağırarak DTE nesne alabilirsiniz <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> yöntemi DTE nesne türüne sahip. Yönetilen Genişletilebilirlik Çerçevesi (MEF) uzantılarında aldığınız <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> ve ardından arama <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> yöntemi türüne sahip <xref:EnvDTE.DTE>.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="getting-the-dte-object"></a>DTE nesnesini alma  
  
#### <a name="to-get-the-dte-object-from-the-serviceprovider"></a>ServiceProvider DTE nesnesini almak için  
  
1.  Adlı bir C# VSIX proje oluşturma `DTETest`. Bir düzenleyici sınıflandırıcı öğe şablonu ekleyin ve adını `DTETest`. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
2.  Aşağıdaki derleme referanslarını projeye ekleyin:  
  
    -   EnvDTE  
  
    -   EnvDTE80  
  
    -   Microsoft.VisualStudio.Shell.Immutable.10.0  
  
3.  DTETest.cs dosyasına gidin ve aşağıdakileri ekleyin `using` yönergeleri:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using Microsoft.VisualStudio.Shell;  
  
    ```  
  
4.  İçinde `GetDTEProvider` sınıfı, içeri aktarma bir <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>.  
  
    ```csharp  
    [Import]  
    internal SVsServiceProvider ServiceProvider = null;  
  
    ```  
  
5.  İçinde `GetClassifier()` yöntemi, aşağıdaki kodu ekleyin.  
  
    ```csharp  
    DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));  
  
    ```  
  
6.  Kullanmanız gerekiyorsa <xref:EnvDTE80.DTE2> arabirimi, DTE nesnesiyle çevirebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dil Hizmeti ve Düzenleyici Uzantı Noktaları](../extensibility/language-service-and-editor-extension-points.md)