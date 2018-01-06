---
title: "Komut kullanılabilirlik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, context
- menu items, visibility contexts
ms.assetid: c74e3ccf-d771-48c8-a2f9-df323b166784
caps.latest.revision: "34"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 53ab248d9e71d3177cabb8ce522343d37bcabb26
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="command-availability"></a>Komut kullanılabilirliği
Visual Studio bağlam hangi komutların kullanılabileceğini belirler. İçerik geçerli projenin, geçerli Düzenleyici, yüklenen VSPackages ve diğer yönlerini tümleşik geliştirme ortamı (IDE) bağlı olarak değiştirebilirsiniz.  
  
## <a name="command-contexts"></a>Komut bağlamları  
 Aşağıdaki komut bağlamları en sık kullanılır.  
  
-   **IDE** IDE tarafından sağlanan komutlardır her zaman kullanılabilir.  
  
-   **VSPackage** VSPackages komutları görüntülenen veya gizleneceğini olduğunda tanımlayabilirsiniz.  
  
-   **Proje** proje komutlar, yalnızca şu anda seçili proje için görünür.  
  
-   **Düzenleyici** yalnızca bir düzenleyici etkin bir anda olabilir. Etkin düzenleyicisinden komutlar kullanılabilir. Bir düzenleyici yakından dil hizmeti ile çalışır. Dil hizmeti, kendi komutları ilişkili Düzenleyicisi bağlamında işlemi gerekir.  
  
-   **Dosya türü** bir düzenleyici birden çok dosya türünü yükleyebilirsiniz. Kullanılabilir komutlar dosya türüne bağlı olarak değiştirebilirsiniz.  
  
-   **Etkin pencereyi** son etkin belgeyi pencere kullanıcı arabirimi (UI) bağlamı için anahtar bağlamaları ayarlar. Ancak, iç Web tarayıcısı benzer bir anahtar bağlama tablo içeren bir araç penceresi UI bağlam ayarlayabilirsiniz. HTML düzenleyicisi gibi çoklu sekmeli belge pencereleri için farklı komut bağlam GUID her sekmesi vardır. Araç penceresi kaydedildikten sonra her zaman kullanılabilir **Görünüm** menüsü.  
  
-   **UI bağlam** UI bağlamları değerleri tarafından tanımlanan <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT> sınıfı, örneğin, <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionBuilding> çözüm yerleşik olduğunda veya <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_Debugging> hata ayıklayıcısı etkinken. Aynı anda birden çok UI bağlamları etkin olabilir.  
  
## <a name="defining-custom-context-guids"></a>Özel bağlam GUID'ler tanımlama  
 GUID zaten tanımlanmamış bir uygun komutu bağlamı, etkin veya devre dışı olarak komutlarınızı görünürlüğünü denetlemek için gerekli olması için program ve, VSPackage birinde tanımlayın.  
  
1.  Bağlam GUID'ler çağırarak kaydedin <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCmdUIContextCookie%2A> yöntemi.  
  
2.  Bağlam GUID durumunu çağırarak alma <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> yöntemi.  
  
3.  Çağırarak bağlam GUID'ler açıp kapatabilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.SetCmdUIContext%2A> yöntemi.  
  
    > [!CAUTION]
    >  Diğer VSPackages bunlara bağımlı çünkü, VSPackage her mevcut bağlam GUID'ler etkilemez emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçim bağlam nesneleri](../../extensibility/internals/selection-context-objects.md)   
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)