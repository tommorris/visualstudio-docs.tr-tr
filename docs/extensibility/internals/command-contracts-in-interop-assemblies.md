---
title: Birlikte çalışma derlemeleri sözleşmelerinde komut | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- command handling with interop assemblies, command contracts
- interop assemblies, command contracts
ms.assetid: 57245708-f539-42dc-8963-2754a48f0189
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bfb60bb4fdc0a633ecee92c47b8465f794416bec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="command-contracts-in-interop-assemblies"></a>Birlikte çalışma derlemeleri komutu sözleşmeleri
Komutları işlemek için temel sözleşme <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimidir ortamı çağırdığı <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi komutu desteklenip desteklenmediğini ve bu desteklenip desteklenmediğini belirlemek için durumu ve metin belirlemek için. Ardından, ortam çağrıları <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemi komutu yürütün.  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> Yöntemi tüm komutlar için aynı şekilde işlenir. Daha fazla iletişim (örneğin, açılan listeleri ile), gerekirse yönetilir çağırarak <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> uygun parametrelerle yöntemi. Bu parametreler yorumu belirtilen komuta bağlı olarak değişir.  
  
 Komut hedefi çıkış parametresinde değerler döndürürse, çağıran her zaman ayrılmış tüm kaynakları serbest bırakma için sorumludur. Bu parametre bir değişken olduğundan, değişken temizleme kaynakları serbest bırakır.  
  
 Burada komutları gerekir çalışması hiyerarşisi penceresi içinde durumlarda <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> arabirimi kullanılmalıdır. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> Arabirimi benzer yöntemleriyle benzer gereksinim vardır: <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Komut içinde VSPackages yönlendirme](../../extensibility/internals/command-routing-in-vspackages.md)   
 [Uygulama](../../extensibility/internals/command-implementation.md)