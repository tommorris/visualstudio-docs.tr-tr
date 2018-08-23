---
title: 'CA1412: ComSource arabirimlerini IDispatch | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MarkComSourceInterfacesAsIDispatch
- CA1412
helpviewer_keywords:
- CA1412
- MarkComSourceInterfacesAsIDispatch
ms.assetid: 131a7563-0410-443c-a8f5-52104250cfb4
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ed548db444929a542a526cf61deaec7135b1f128
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674370"
---
# <a name="ca1412-mark-comsource-interfaces-as-idispatch"></a>CA1412: ComSource Arabirimlerini IDispatch olarak işaretleyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1412: işareti ComSource arabirimlerini IDispatch olarak](https://docs.microsoft.com/visualstudio/code-quality/ca1412-mark-comsource-interfaces-as-idispatch).  
  
TypeName | MarkComSourceInterfacesAsIDispatch |  
| Checkıd | CA1412 |  
| Kategori | Microsoft.Interoperability|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir türü ile işaretlenmiş <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> özniteliği ve en az bir belirtilen arabirim işaretlenmemiş ile <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> özniteliğini `InterfaceIsDispatch` değeri.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> Bileşen Nesne Modeli (COM) istemcilere bir sınıfı gösterir olay arabirimi tanımlamak için kullanılır. Bu arabirimleri olarak sunulmalıdır `InterfaceIsIDispatch` olay bildirimlerini almak üzere Visual Basic 6 COM istemcileri etkinleştirmek için. Varsayılan bir arabirim ile işaretlenmemiş olması <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> öznitelik, bir çift arabirim sunulur.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için ekleme veya değiştirme <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> değeri ile belirtilen tüm arabirimlerin InterfaceIsIDispatch için ayarlanır böylece öznitelik <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, burada bu arabirimlerinden birini kuralını ihlal eden bir sınıfı gösterir.  
  
 [!code-csharp[FxCop.Interoperability.MarkIDispatch#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.MarkIDispatch/cs/FxCop.Interoperability.MarkIDispatch.cs#1)]
 [!code-vb[FxCop.Interoperability.MarkIDispatch#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.MarkIDispatch/vb/FxCop.Interoperability.MarkIDispatch.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1408: AutoDual ClassInterfaceType kullanma](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir COM havuzu tarafından işlenen olayları oluşturma](http://msdn.microsoft.com/en-us/7c9944b2-e951-4c3e-a0a1-59b2ae37d7fd)   
 [Yönetilmeyen Kod ile Birlikte Çalışma](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



