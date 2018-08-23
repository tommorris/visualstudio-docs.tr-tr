---
title: Bağlam menüleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - context menus
ms.assetid: 44fd9e6a-6d42-4aba-80ba-f37fa0070f1d
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b95f913f5705b115473847b12b3fd1df8a5bcff8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690937"
---
# <a name="context-menus"></a>Bağlam Menüleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [bağlam menüleri](https://docs.microsoft.com/visualstudio/extensibility/context-menus).  
  
Bağlam menüleri kullanıcı etkin bir istemci alanını bölgesinde tıkladığında görüntülenir ve farenin sağ düğmesi bırakıldığında temizleyin.  
  
## <a name="editor-context-menus"></a>Düzenleyici Bağlam Menüleri  
 Kesintiye tarafından `ECMD_SHOWCONTEXTMENU`, düzenleyicide görüntülenir bağlam menüleri, dil hizmeti denetleyebilirsiniz. Kendi bağlam menüsünü görüntülemek için oturum geçirildiğinde bu komutu işlemek, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A>. Bu komut işlememesi IDE düzenleyici için sağlanan standart bağlam menüsü görüntülenir. Bağlam menüsü işaret başına temelinde içeriğini de denetleyebilirsiniz. Bu konu hakkında daha fazla bilgi için bkz. [kullanarak metin işaretçileri eski API'siyle](../extensibility/using-text-markers-with-the-legacy-api.md) ve [kesintiye eski dil hizmeti komutlarını](../extensibility/internals/intercepting-legacy-language-service-commands.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti geliştirme](../extensibility/internals/developing-a-legacy-language-service.md)   
 [Menüleri ve Komutlari Genişletme](../extensibility/extending-menus-and-commands.md)

