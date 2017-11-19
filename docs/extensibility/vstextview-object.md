---
title: VSTextView nesne | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSTextView
helpviewer_keywords:
- VSTextView object, reference
- views [Visual Studio SDK], reference
ms.assetid: 78272ddc-9718-4c65-a94e-a44a2e8d54f4
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e3b7cdc698a169150560b2a924cd6f3317fa78ed
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="vstextview-object"></a>VSTextView nesnesi
Metin görünümü, kullanıcıların metin arabelleğinin Unicode metni görüntüleyin ve düzenleyin olanak veren bir penceredir. Esas olarak, hangi kullanıcıların çoğunun düzenleyicisi olarak başvurmak görünümüdür. Görünüm arabelleğinden çeşitli metin katmanları (sözcük kaydırma, anahat metin vb.) ayrı olması nedeniyle görünümü metin arabelleği tam bir temsili olması garanti edilmez. Metin görünümü hakkında daha fazla bilgi için bkz: [eski API kullanarak getirip metin görünümü erişme](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
  
 Aşağıdaki tablo arabirimler gösterir <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> nesnesi.  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|[IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071)|Standart OLE arabirimi.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>|Standart OLE arabirimi.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite>|Standart OLE arabirimi.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Standart OLE arabirimi.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Bileşik eylemleri (diğer bir deyişle, bir tek geri alma/yineleme biriminde gruplandırılır Eylemler) oluşturulmasını sağlar.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|Temel yöntemler yönetme ve görünüm erişim sağlar. `IVsTextView`iş parçacığı güvenli değil.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Oluşturur ve bir pencere bölmesine yönetir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|Metin katmanları ile etkileşime girer.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsThreadSafeTextView>|Farklı bir iş parçacığından görünümü işlemleri gerçekleştirir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şekiller Düzenle](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)   
 [VSTextBuffer nesnesi](../extensibility/vstextbuffer-object.md)   
 [Eski API kullanarak getirip metin görünümü erişme](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)