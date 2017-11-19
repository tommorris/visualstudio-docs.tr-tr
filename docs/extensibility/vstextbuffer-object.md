---
title: VSTextBuffer nesne | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSTextBuffer
helpviewer_keywords:
- VSTextBuffer object, reference
- views [Visual Studio SDK], VSTextBuffer object
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d25551d6af9b2250275713541dc9c9df39ca90ec
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="vstextbuffer-object"></a>VSTextBuffer nesnesi
Metin arabelleği nesnesini bir akış genellikle bir dosya ile ilişkilendirilmiş bir Unicode metin temsil eder. A <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> nesne gibi bir sihirbaz söz konusu olduğunda çekirdek Düzenleyici, bağlam dışında kullanılabilir.  
  
 Aşağıdaki tablo arabirimler gösterir `VSTextBuffer`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797)|Standart OLE arabirimi. Geri alma/yineleme arabellekte işleme için temel olarak kullanılır.|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Standart OLE arabirimi.|  
|[IPersistStream](http://msdn.microsoft.com/library/windows/desktop/ms690091)|Standart OLE arabirimi.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Bileşimlerini eylemleri (diğer bir deyişle, bir tek geri alma/yineleme biriminde gruplandırılır Eylemler) oluşturulmasını sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Metin arabelleğini tarafından yönetilen belge veri kalıcılığını etkinleştirir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Temel hizmetleri sağlayan; birçok istemciler tarafından kullanılır.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|Arabellek aramak için kullanılır.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Sağlar okuma ve yazma iki boyutlu koordinatları kullanarak yetenekleri. Öğesinden devralınan `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Sağlar okuma ve yazma yeteneklerini tek boyutlu koordinatları kullanarak. Öğesinden devralınan `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Hızlı, metin arabelleği akış odaklı, sıralı erişim sağlar.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Bir genel koleksiyon özelliklerinin erişim sağlar. En önemli özelliğinin adı veya arabellek ad olmalıdır. Bir GUID oluşturarak ve bir anahtar olarak kullanarak rastgele verilerinizi bu arabirimle arabellek depolayabilirsiniz.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Bağlantı noktaları için olayları destekler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `VSTextBuffer` Genellikle tarafından bulunan bir `QueryInterface` çağırmak `IVsTextBuffer`. Daha fazla bilgi için bkz: [metin arabelleğini](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [Şekiller Düzenle](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)