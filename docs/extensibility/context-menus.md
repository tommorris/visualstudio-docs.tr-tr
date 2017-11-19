---
title: "Bağlam menüleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - context menus
ms.assetid: 44fd9e6a-6d42-4aba-80ba-f37fa0070f1d
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d56be2fecca89d3cfb5a7b12982a0de7f61d457f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="context-menus"></a>Bağlam menüleri
Bağlam menüleri istemci alanını etkin bir bölgede kullanıcı tıklattığında görüntülenir ve farenin sağ düğmesiyle yayımlandığında temizleyin.  
  
## <a name="editor-context-menus"></a>Düzenleyici Bağlam Menüleri  
 Kesintiye uğratan tarafından `ECMD_SHOWCONTEXTMENU`, dil hizmetinizi Düzenleyicisi'nde görüntüler bağlam menülerini kontrol edebilirsiniz. Kendi bağlam menüsünü görüntülemek için içine geçirildiğinde bu komutu işlemek, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A>. Bu komutu işlemek değil, IDE Düzenleyicisi sağlanan standart bağlam menüsü görüntülenir. Bağlam menüsü işaret başına temelinde içeriğini de denetleyebilirsiniz. Bu konu hakkında daha fazla bilgi için bkz: [kullanarak metin işaretçileri eski API ile](../extensibility/using-text-markers-with-the-legacy-api.md) ve [kesintiye uğratan eski dil hizmeti komutları](../extensibility/internals/intercepting-legacy-language-service-commands.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti geliştirme](../extensibility/internals/developing-a-legacy-language-service.md)   
 [Genişletme menüleri ve komutları](../extensibility/extending-menus-and-commands.md)