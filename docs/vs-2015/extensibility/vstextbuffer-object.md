---
title: VSTextBuffer nesnesi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VSTextBuffer
helpviewer_keywords:
- VSTextBuffer object, reference
- views [Visual Studio SDK], VSTextBuffer object
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 897604c39f64df2208b3b0e17da2c0ddfe8cc2ab
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633661"
---
# <a name="vstextbuffer-object"></a>VSTextBuffer Nesnesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [VSTextBuffer nesnesi](https://docs.microsoft.com/visualstudio/extensibility/vstextbuffer-object).  
  
Metin arabelleği nesnesini bir akış genellikle bir dosya ile ilişkilendirilmiş bir Unicode metin temsil eder. A <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> nesne gibi bir Sihirbazı söz konusu olduğunda çekirdek Düzenleyici, bağlamı dışında kullanılabilir.  
  
 Aşağıdaki tabloda, arabirimler gösterilir `VSTextBuffer`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797)|Standart OLE arabirimidir. Esas olarak, Geri Al/Yinele arabellekteki işleme için kullanılır.|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Standart OLE arabirimidir.|  
|[IPersistStream](http://msdn.microsoft.com/library/windows/desktop/ms690091)|Standart OLE arabirimidir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Bileşimden eylemleri (diğer bir deyişle, bir tek geri al/Yinele biriminde gruplandırılır eylemleri) oluşturulmasını sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Metin arabelleği tarafından yönetilen belge veri kalıcılığını etkinleştirir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Temel hizmetleri sağlar. birden çok istemci tarafından kullanılır.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|Arabellek aramak için kullanılır.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Sağlar okuma ve yazma iki boyutlu koordinatlarını kullanarak özellikleri. Devralınan `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Sağlar okuma ve yazma özellikleri kullanarak tek boyutlu koordinatları. Devralınan `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Hızlı, arabellekteki metni akışa dayalı olarak sıralı erişim sağlar.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Genel Özellikler koleksiyonu erişim sağlar. En önemli özellik adını veya bilinen ad, arabellek olur. Bir GUID oluşturma ve bir anahtar olarak kullanarak rastgele verilerinizi bu arabirimle arabellek depolayabilirsiniz.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Bağlantı noktaları için olayları destekler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `VSTextBuffer` Genellikle tarafından bulunan bir `QueryInterface` çağırmak `IVsTextBuffer`. Daha fazla bilgi için [metin arabelleğini](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [Şekil Düzenle](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)

