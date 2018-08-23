---
title: 'Nasıl yapılır: eski dil hizmetinde ana hat oluşturma desteği | Microsoft Docs'
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
- editors [Visual Studio SDK], collapse to definitions command
- language services, supporting Collapse to Definitions command
- hidden text, Collapse to Definitions command
ms.assetid: bb6e74c3-93e4-4ef7-afc7-1c9b342f083b
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 336e8c04116afa5523a10f7e0617fdc18678c5d7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684381"
---
# <a name="how-to-support-outlining-in-a-legacy-language-service"></a>Nasıl yapılır: eski dil hizmetinde ana hat oluşturma desteği
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: eski dil hizmetinde destek anahat](https://docs.microsoft.com/visualstudio/extensibility/internals/how-to-support-outlining-in-a-legacy-language-service).  
  
Anahat oluşturma, genişletme veya daraltma farklı bölgelerdeki metin için kullanılır. Anahat oluşturma şekilde kullanılan tarafından farklı dillerde farklı şekilde tanımlanabilir. Daha fazla bilgi için [anahat](../../ide/outlining.md).  
  
 Eski dil Hizmetleri bir VSPackage'ı bir parçası olarak uygulanır, ancak dil hizmeti özellikleri uygulamak için daha yeni MEF uzantıları kullanmaktır. Anahat oluşturma uygulamak için en yeni yolu hakkında daha fazla bilgi için bkz: [izlenecek yol: ana hat oluşturmayı](../../extensibility/walkthrough-outlining.md).  
  
> [!NOTE]
>  Yeni bir düzenleyici API hemen kullanmaya başlamak öneririz. Bu dil hizmetinizin performansını ve yeni düzenleyici özellikleri yararlanmanıza olanak tanır.  
  
 Bu komut, language service Pro desteklemek nasıl gösterir.  
  
### <a name="to-support-outlining"></a>Ana hat oluşturmayı desteklemek için  
  
1.  Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage> dil hizmeti nesneniz üzerinde.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> yeni anahat bölge ekleme için anahat oluşturma geçerli oturum nesnesi üzerinde.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Bir kullanıcı seçtiğinde **Daralt tanımları** üzerinde **anahat** menüsü, IDE çağrıları <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage.CollapseToDefinitions%2A> dil hizmetinizde.  
  
 Bu yöntem çağrıldığında, IDE içinde geçen bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> işaretçi (işaretçiye bir metin arabelleği için) ve bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession> (geçerli anahat oluşturma oturumu için bir işaretçi).  
  
 Çağırabilirsiniz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> yöntemi bu bölgelerde belirterek, birden çok ana hat bölgeler için `rgOutlnReg` parametresi. `rgOutlnReg` Parametresi bir <xref:Microsoft.VisualStudio.TextManager.Interop.NewOutlineRegion> yapısı. Bu işlem, belirli bir bölge genişletilmiş veya daraltılmış gibi gizli bölge farklı özelliklerini belirtmenize olanak sağlar.  
  
> [!NOTE]
>  Yeni satır karakterleri gizleme hakkında dikkatli olun. Gizli metin ilk satırını başından son karakter bir bölümdeki son satırın son yeni satır karakteri görünür bırakmak genişletmelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: eski dil hizmetinde gizli metin desteği](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)   
 [Nasıl yapılır: Eski Dil Hizmetinde Genişletilmiş Ana Hat Oluşturma Desteği Sağlama](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)

