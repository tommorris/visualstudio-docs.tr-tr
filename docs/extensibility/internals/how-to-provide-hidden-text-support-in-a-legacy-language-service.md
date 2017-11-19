---
title: "Nasıl yapılır: eski dil hizmetindeki gizli metin desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hidden text, supporting
- editors [Visual Studio SDK], hidden text
- language services, implementing hidden text regions
ms.assetid: 1c1dce9f-bbe2-4fc3-a736-5f78a237f4cc
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f7aab5978d2fc5f7bee82b097ed61a9603d7e198
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-provide-hidden-text-support-in-a-legacy-language-service"></a>Nasıl yapılır: eski dil hizmetindeki gizli metin desteği sağlar
Anahat bölgeler yanı sıra gizli metni bölgeler oluşturabilirsiniz. Gizli metni bölgeler, istemci tarafından denetlenen veya Düzenleyicisi denetimli olabilir ve bir bölge metnin tamamen gizlemek için kullanılır. Düzenleyici gizli bir bölge yatay çizgiler olarak görüntüler. Bu komut yalnızca görünümünde HTML düzenleyicisi örneğidir.  
  
## <a name="procedure"></a>Yordam  
  
#### <a name="to-implement-a-hidden-text-region"></a>Gizli metni bölgeye uygulamak için  
  
1.  Çağrı `QueryService` için <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>.  
  
     Bu bir işaretçi döndürür <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>, verilen metin belgesi için bir işaretçi geçen. Bu, gizli metin oturumu zaten için arabellek var olup olmadığını belirler.  
  
3.  Zaten bir tane sonra biri ve var olan bir işaretçi oluşturun gerekmez <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> nesne döndürülür. Bu işaretçinin numaralandırır ve gizli metni bölgeler oluşturmak için kullanın. Aksi halde çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> arabellek için gizli metni oturum oluşturmak için.  
  
     Bir işaretçi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> nesne döndürülür.  
  
    > [!NOTE]
    >  Çağırdığınızda `CreateHiddenTextSession`, gizli metin istemci belirtebilirsiniz (diğer bir deyişle, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient>). Gizli metni istemci gizli metni veya anahat oluşturma genişletilmiş veya kullanıcı tarafından daraltılmış size bildirir.  
  
4.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> ekleyin veya daha yeni bir kerede anahat aşağıdaki bilgileri belirtme bölgeler için `reHidReg` (<xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion>) parametre:  
  
    1.  Değerini belirtin `hrtConcealed` içinde `iType` üyesi <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> anahat bölge yerine gizli bir bölge oluşturduğunuzu belirtmek için yapısı.  
  
        > [!NOTE]
        >  Gizli bilgiler bölgeler gizlidir, Düzenleyicisi'ni otomatik olarak kendi varlığını göstermek için gizli bölgeler etrafında çizgiler görüntüler.  
  
    2.  Bölge içinde düzenleyicisi olarak kontrol ya da istemci denetlenen olup olmadığını belirtin `dwBehavior` üyeleri <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> yapısı. Akıllı anahat uygulamanızı Düzenleyicisi ve istemci denetlenen anahat ve gizli metni bölgeler bir karışımını içerebilir.