---
title: "Tek dosya oluşturucuları uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom tools, implementing
- projects [Visual Studio SDK], extensibility
- projects [Visual Studio SDK], managed custom tools
ms.assetid: fe9ef6b6-4690-4c2c-872c-301c980d17fe
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b9fed2f4118600c48ad6cb769c8e697b06ae77d1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-single-file-generators"></a>Tek dosya oluşturucuları uygulama
Özel bir araç — bazen tek dosya oluşturucu da adlandırılır — genişletmek için kullanılan [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] ve [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] proje sistemlerinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Arabirimini uygulayan bir COM bileşeni özel bir araç olan <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> arabirimi. Bu arabirimi kullanarak, özel bir araç tek bir giriş dosyası tek bir çıktı dosyasına dönüştürür. Diğer kullanışlı olan çıktı veya dönüşümün sonucunu kaynak kodu olabilir. Görsel Tasarımcı ve Web Hizmetleri Açıklama Dili (WSDL) kullanılarak oluşturulan dosyaları değişikliklere yanıt olarak üretilen kod özel aracı tarafından oluşturulan kod dosyalarının iki örnek verilmiştir.  
  
 Özel bir araç yüklenir veya giriş dosyası kaydedilir, proje sistemi çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> yöntemini ve bir başvuru geçirir bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsGeneratorProgress> yapabildiği aracı raporlama yapabilir, ilerleme durumunu kullanıcıya geri çağırma arabirimi.  
  
 Özel araç oluşturur çıktı dosyası projesi ile giriş dosyası bir bağımlılığı eklenir. Özel aracın uygulaması tarafından döndürülen dize göre çıkış dosyasının adı proje sistemi otomatik olarak saptar <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>.  
  
 Özel bir araç uygulamalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> arabirimi. İsteğe bağlı olarak, destek özel araçları <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite> giriş dosyası dışındaki kaynaklardan bilgi almak için arabirim. Özel bir araç kullanmadan önce herhangi bir durumda, onu sistem veya de kaydetmeniz gerekir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yerel kayıt. Özel Araçlar kaydetme hakkında daha fazla bilgi için bkz: [kaydetme tek dosya oluşturucuları](../../extensibility/internals/registering-single-file-generators.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Türleri Görsel Tasarımcıların Kullanımına Sunma](../../extensibility/internals/exposing-types-to-visual-designers.md)