---
title: 'CA1040: boş arabirimlerden kaçının | Microsoft Docs'
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
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2a08764921bb917fee6118eaa1880a81d82753fb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690599"
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040: Boş arabirimlerden kaçının
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1040: boş arabirimlerden kaçının](https://docs.microsoft.com/visualstudio/code-quality/ca1040-avoid-empty-interfaces).  
  
TypeName | AvoidEmptyInterfaces |  
| Checkıd | CA1040 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Arabirim herhangi bir üye bildirmek veya iki veya daha fazla diğer arabirimleri de uygulamak desteklemez.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Arayüzler bir davranış veya kullanım sözleşmesi sağlayan üyeleri tanımlar. Arabirim tarafından tanımlanan fonksiyonellik herhangi bir tür tarafından türün kalıtım hiyerarşisinde nerede belirdiği önemsenmeksizin devralınabilir. Tür arabirimin üyeleri için uygulamaları sağlayarak bir arayüz uygular. Boş bir arabirim herhangi bir üye tanımlamıyor. Bu nedenle, uygulanabilir bir sözleşme tanımlamaz.  
  
 Tasarımınızı boş içeriyorsa türleri arabirimleri uygulayan beklenir, büyük olasılıkla bir işaretçi veya bir grup türleri tanımlamak için bir yol olarak bir arabirim kullanıyorsunuz. Bu kimliği, çalışma zamanında meydana gelir, bunu gerçekleştirmek için doğru şekilde özel bir öznitelik kullanmaktır. Hedef türlerini tanımlamak için varlığı veya öznitelik olmaması veya öznitelik özelliklerini kullanın. Ardından derleme zamanında kimliği olmalıdır, boş bir arabirim kullanmak için kabul edilebilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Arabirimi Kaldır veya üyeleri ekleyin. Boş arabirim türleri kümesi etiketlemek için kullanılıyorsa, arabirim özel bir öznitelik ile değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Arabirimi, derleme zamanında türleri kümesini tanımlamak için kullanıldığında, bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, boş bir arabirim gösterir.  
  
 [!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.InterfacesNotEmpty/cpp/FxCop.Design.InterfacesNotEmpty.cpp#1)]
 [!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.InterfacesNotEmpty/cs/FxCop.Design.InterfacesNotEmpty.cs#1)]
 [!code-vb[FxCop.Design.InterfacesNotEmpty#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.InterfacesNotEmpty/vb/FxCop.Design.InterfacesNotEmpty.vb#1)]



