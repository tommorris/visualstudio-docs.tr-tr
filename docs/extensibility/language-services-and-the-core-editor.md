---
title: "Dil Hizmetleri ve çekirdek Düzenleyici | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - language services
ms.assetid: e03199a6-ad5f-4075-bfba-8d36865112b7
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c3d2bcad21bb919125b487a57b73d3a458a3a1f9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="language-services-and-the-core-editor"></a>Dil Hizmetleri ve çekirdek Düzenleyicisi
Visual Studio'da düzenleyicileri sık bir dil hizmeti ile ilişkilendirilmiş. Bunun yanı sıra, bir dil hizmeti söz dizimi renklendirme, deyim tamamlama, IntelliSense ve metin biçimlendirmesini sağlar.  
  
## <a name="core-editors-and-document-data-objects"></a>Çekirdek düzenleyicileri ve belge veri nesneleri  
 Çekirdek Düzenleyici eriştiğinizde, düzenleme belge verileri ve belge görünümü nesneleri oluşturmayın. IDE oluşturur ve bu iki nesne denetler ve uygun çağrıları düzenleyicinizde Üreteç uygulaması yaparak bunları işleyicilerine elde edin.  
  
 Daha fazla bilgi için bkz: [projede açılır bir dosyayı hangi Düzenleyicisi'ni belirleme](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md).  
  
## <a name="language-services-and-the-core-editor"></a>Dil Hizmetleri ve çekirdek Düzenleyicisi  
 Bir dil hizmeti uygulayarak, verilerin bir belge görünümünde nasıl görüntüleneceğini kontrol edebilirsiniz. Bir dil hizmeti bilgileri ve Visual C++ gibi belirli bir dile özgü davranış sağlar. Bir metin arabelleği oluşturduğunuzda ve açmakta olduğunuz belge için dosya adı uzantısı belirlemek metin arabelleği HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Editors bir kayıt defteri anahtarından bu dosya adı uzantısıyla ilişkili dil hizmeti belirler. \\{YourLanguageService GUID} \Extensions. Yordam sonra yükleme standart VSPackage, VSPackage yükler ve dil hizmetinin bir örneği oluşturulur.  
  
 Temel dil hizmeti aşağıdaki çizimde gösterilmiştir.  
  
 ![Dil Hizmet Modeli grafiği](../extensibility/media/vslanguageservicemodel.gif "vsLanguageServiceModel")  
Çekirdek düzenleyici ve dil hizmeti nesneleri  
  
 Çekirdek düzenleyici için belge veri nesnesi bir metin arabelleği olarak adlandırılır ve tarafından temsil edilen <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> nesnesi. Belge görünüm nesnesi bir metin görünüm olarak adlandırılır ve tarafından temsil edilen <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> nesnesi. Bu iki nesne çekirdek Düzenleyici birleşik bir görünümünü sağlamak için dil hizmeti ile birlikte çalışır. Metin arabelleği ve metin görünümü görüntüler belge penceresindeki bilgileri kod penceresi çağrılır. Kod penceresini belge kod Pencere Yöneticisi tarafından yönetilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 [Eski API kullanarak bir dil Hizmet bağlamı sağlama](../extensibility/providing-a-language-service-context-by-using-the-legacy-api.md)   
 [IntelliSense barındırma](../extensibility/intellisense-hosting.md)   
 [Kapsanan dilleri](../extensibility/contained-languages.md)   
 [Eski Dil Hizmeti Geliştirme](../extensibility/internals/developing-a-legacy-language-service.md)