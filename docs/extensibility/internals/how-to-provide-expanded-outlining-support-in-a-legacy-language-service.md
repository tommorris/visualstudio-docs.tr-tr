---
title: "Bir dil hizmetindeki desteğin sağlamak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], outlining support
- language services, supporting outlining
- outlining, supporting
ms.assetid: df759e89-8193-418c-8038-6626304d387b
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0fd353e39e3e3edbdbdb929fa16abb74126dbbc9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-provide-expanded-outlining-support-in-a-legacy-language-service"></a>Nasıl yapılır: eski dil hizmetindeki genişletilmiş anahat desteği sağlar
Destekleyen ötesinde dilinizi anahat desteğini genişletmek için iki seçenek vardır **daraltmak için tanımları** komutu. Anahat Düzenleyicisi denetimli bölgeler ekleyin ve istemci tarafından denetlenen anahat bölgeler ekleyin.  
  
## <a name="adding-editor-controlled-outline-regions"></a>Anahat Düzenleyicisi denetimli bölgeler ekleme  
 Daraltılmış, anahat bölge oluşturmak ve bölge genişletilmiş olup olmadığını işlemek için Düzenleyicisi izin vermek için bu yaklaşımı kullanın ve benzeri. Anahat desteği sağlamak için bu iki seçenekten birini bu az sağlam bir seçenektir. Bu seçenek için metni kullanarak, belirtilen bir aralığı yeni anahat bölgesi oluşturmak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A>. Bu bölge oluşturulduktan sonra davranışını Düzenleyicisi tarafından denetlenir. Anahat Düzenleyicisi denetimli bölgeler uygulamak için aşağıdaki yordamı kullanın.  
  
#### <a name="to-implement-an-editor-controlled-outline-region"></a>Bir düzenleyici denetimli anahat bölge uygulamak için  
  
1.  Çağrı `QueryService` için<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>  
  
     Bu bir işaretçi döndürür <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>, verilen metin belgesi için bir işaretçi geçen. Bu bir işaretçi döndürür <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> arabellek nesne.  
  
3.  Çağrı <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> üzerinde <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> gösteren bir işaretçi için <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession>.  
  
4.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> ekleyin veya daha yeni bir kerede bölgeleri ana hatlarını vermektedir.  
  
     Bu yöntem, Anahat, varolan anahat bölgeler olup kaldırılan veya korunur ve anahat bölge veya genişletilmiş varsayılan olarak daraltılmış metin aralığını belirtmenizi sağlar.  
  
## <a name="adding-client-controlled-outline-regions"></a>İstemci tarafından denetlenen anahat bölgeler ekleme  
 Uygulama istemci denetimli (veya akıllı) anahat oluşturma bu yaklaşım tarafından kullanılan gibi kullanım [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] dil Hizmetleri. Kendi anahat oluşturma yöneten bir dil hizmeti, bunlar geçersiz olduğunda eski anahat bölgeleri yok etmek için ve gerektiğinde yeni anahat bölgeler oluşturmak için metin arabelleği içeriği izler.  
  
#### <a name="to-implement-a-client-controlled-outline-region"></a>Bir istemci tarafından denetlenen anahat bölge uygulamak için  
  
1.  Çağrı `QueryService` için <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>. Bu bir işaretçi döndürür <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>, verilen metin belgesi için bir işaretçi geçen. Bu, gizli metin oturumu zaten için arabellek var olup olmadığını belirler.  
  
3.  Bir metin oturumu zaten var sonra biri ve var olan bir işaretçi oluşturun gerekmez <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> nesne döndürülür. Bu işaretçinin numaralandırır ve anahat bölgeler oluşturmak için kullanın. Aksi halde çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> arabellek için gizli metni oturum oluşturmak için. Bir işaretçi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> nesne döndürülür.  
  
    > [!NOTE]
    >  Çağırdığınızda <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A>, gizli metin istemci belirtebilirsiniz (diğer bir deyişle, bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient> nesnesi). Bu istemci gizli metni olduğunda uyarır veya anahat bölge genişletilmiş veya kullanıcı tarafından daraltılmış.  
  
4.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> yapısı) parametre: değerini belirtin <xref:Microsoft.VisualStudio.TextManager.Interop.HIDDEN_REGION_TYPE> içinde `iType` üyesi <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> gizli bir bölge yerine bir anahat bölge oluşturmakta olduğunuz belirtmek için yapısı. Bölge içinde düzenleyicisi olarak kontrol ya da istemci denetlenen olup olmadığını belirtin `dwBehavior` üyesi <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> yapısı. Akıllı anahat uygulamanızı anahat bölgeler Düzenleyicisi ve istemci denetlenen bir karışımını içerebilir. Anahat bölgenize, "... gibi", buna daraltıldığında görüntülenen Başlık metni belirtin `pszBanner` üyesi <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> yapısı. Düzenleyicinin varsayılan başlık metni gizli bir bölge için "...".