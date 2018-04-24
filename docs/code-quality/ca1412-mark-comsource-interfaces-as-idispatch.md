---
title: 'CA1412: ComSource Arabirimlerini IDispatch olarak işaretleyin'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkComSourceInterfacesAsIDispatch
- CA1412
helpviewer_keywords:
- CA1412
- MarkComSourceInterfacesAsIDispatch
ms.assetid: 131a7563-0410-443c-a8f5-52104250cfb4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e4c446f1838120afd1dbcdf21ce9710982d38c0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1412-mark-comsource-interfaces-as-idispatch"></a>CA1412: ComSource Arabirimlerini IDispatch olarak işaretleyin
|||
|-|-|
|TypeName|MarkComSourceInterfacesAsIDispatch|
|CheckId|CA1412|
|Kategori|Microsoft.Interoperability|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir türü ile işaretlenmiş <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> özniteliği ve en az bir belirtilen arabirimi işaretlenmemiş ile <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> özniteliğini `InterfaceIsDispatch` değeri.

## <a name="rule-description"></a>Kural Tanımı
 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> Bileşen Nesne Modeli (COM) istemciler için bir sınıf gösteren olay arabirimi tanımlamak için kullanılır. Bu arabirimleri olarak sunulmalıdır `InterfaceIsIDispatch` olay bildirimlerini almak üzere Visual Basic 6 COM istemcileri etkinleştirmek için. Varsayılan olarak bir arabirim ile işaretli değilse, <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> öznitelik, bir çift arabirim sunulur.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için ekleme veya değiştirme <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> değeri ile belirtilen tüm arabirimler için InterfaceIsIDispatch için ayarlanır böylece özniteliği <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> özniteliği.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, burada bu arabirimlerinden biri, kuralını ihlal eden bir sınıfı gösterir.

 [!code-csharp[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/CSharp/ca1412-mark-comsource-interfaces-as-idispatch_1.cs)]
 [!code-vb[FxCop.Interoperability.MarkIDispatch#1](../code-quality/codesnippet/VisualBasic/ca1412-mark-comsource-interfaces-as-idispatch_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1408: AutoDual ClassInterfaceType kullanma](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Yönetilmeyen Kod ile Birlikte Çalışma](/dotnet/framework/interop/index)