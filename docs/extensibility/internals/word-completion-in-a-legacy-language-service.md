---
title: Eski dil hizmetinde tamamlama Word | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services [managed package framework], IntelliSense Complete Word
- IntelliSense, Complete Word
- Complete Word
ms.assetid: 0ace5ac3-f9e1-4e6d-add4-42967b1f96a6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 72ddf4e7c755fdecf562f4c190abfb145e6f9819
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31141519"
---
# <a name="word-completion-in-a-legacy-language-service"></a>Eski dil hizmetindeki Sözcük tamamlama
Kısmen yazılan Word eksik karakterleri, sözcük tamamlama doldurur. Yalnızca bir olası tamamlanma ise, tamamlama karakter girdiğinizde word tamamlandı. Kısmi sözcük birden fazla olasılığı eşleşirse, tamamlanabilir listesi görüntülenir. Tamamlama karakter tanımlayıcıları için kullanılmayan herhangi bir karakter olabilir.  
  
 Eski dil hizmetler bir VSPackage bir parçası olarak uygulanır, ancak dil hizmet özellikleri uygulamak için daha yeni MEF uzantıları kullanmak için bir yoludur. Daha fazla bilgi bulmak için bkz: [Düzenleyicisi ve dil Hizmetleri genişletme](../../extensibility/extending-the-editor-and-language-services.md).  
  
> [!NOTE]
>  Yeni Düzenleyicisi API mümkün olan en kısa sürede kullanmaya başlamanızı öneriyoruz. Bu dil hizmetinizin performansını ve yeni Düzenleyicisi özelliklerden yararlanmak sağlar.  
  
## <a name="implementation-steps"></a>Uygulama adımları  
  
1.  Kullanıcı seçtiğinde **tam sözcüğü** gelen **IntelliSense** menüsünde <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> komutu dil hizmetine gönderilir.  
  
2.  <xref:Microsoft.VisualStudio.Package.ViewFilter> Sınıfını yakalayan çağrıları ve komut <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> yöntemi ayrıştırma nedeni ile <xref:Microsoft.VisualStudio.Package.ParseReason>.  
  
3.  <xref:Microsoft.VisualStudio.Package.Source> Sınıf sonra çağrıları <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> olası sözcük tamamlamalar ve araç ipucu sözcükleri listesinde kullanarak ardından görüntüler listesini almak için yöntemi <xref:Microsoft.VisualStudio.Package.CompletionSet> sınıfı.  
  
     Yalnızca bir eşleşen sözcük ise <xref:Microsoft.VisualStudio.Package.Source> sınıfı word tamamlar.  
  
 Alternatif olarak, tarayıcı tetikleme değerini döndürürse <xref:Microsoft.VisualStudio.Package.TokenTriggers> ilk karakteri bir tanımlayıcı olarak yazıldığında <xref:Microsoft.VisualStudio.Package.Source> sınıfı bu algılar ve çağırır <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> yöntemi ayrıştırma nedeni ile <xref:Microsoft.VisualStudio.Package.ParseReason>. Bu durumda ayrıştırıcısı gerekir üye seçimi karakter varolup olmadığını algılamak ve üyelerin listesi sağlayın.  
  
## <a name="enabling-support-for-the-complete-word"></a>Tam sözcük desteğini etkinleştirme  
 Word tamamlama kümesi desteğini etkinleştirmek için `CodeSense` geçirilen parametre adlı <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> dil paket ile ilişkili kullanıcı özniteliği. Bu ayarlar <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> özellikte <xref:Microsoft.VisualStudio.Package.LanguagePreferences> sınıfı.  
  
 Ayrıştırıcısı sürümünüzü yanıt ayrıştırma neden değeri olarak bildirimleri listesini döndürmelidir <xref:Microsoft.VisualStudio.Package.ParseReason>, çalışmak Sözcük tamamlama.  
  
## <a name="implementing-complete-word-in-the-parsesource-method"></a>Tam sözcük ParseSource yöntemi uygulama  
 Sözcük tamamlama <xref:Microsoft.VisualStudio.Package.Source> sınıfı çağrıları <xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDeclarations%2A> yöntemi <xref:Microsoft.VisualStudio.Package.AuthoringScope> olası sözcük eşleşmeleri listesini elde etmek için sınıf. Türetilmiş bir sınıf listesi uygulamalıdır <xref:Microsoft.VisualStudio.Package.Declarations> sınıfı. Bkz: <xref:Microsoft.VisualStudio.Package.Declarations> sınıfını uygulaması gerekiyor yöntemleri hakkında ayrıntılı bilgi için.  
  
 Listede yalnızca tek bir sözcük, varsa sonra <xref:Microsoft.VisualStudio.Package.Source> sınıfı kısmi sözcük yerine bu word otomatik olarak ekler. Listede birden fazla sözcük varsa <xref:Microsoft.VisualStudio.Package.Source> sınıfı kullanıcı seçebileceği uygun seçeneği araç ipucu listesini gösterir.  
  
 Aynı zamanda örneğe bakın bir <xref:Microsoft.VisualStudio.Package.Declarations> sınıfı uygulamasında [eski dil hizmetindeki üye tamamlama](../../extensibility/internals/member-completion-in-a-legacy-language-service.md).