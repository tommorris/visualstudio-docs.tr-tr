---
title: "Birlikte çalışabilirlik uyarıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.Interoperabilityrules
helpviewer_keywords:
- managed code analysis warnings, interoperability warnings
- interoperability warnings
- warnings, interoperability
ms.assetid: 95de6eb3-40c4-4063-9f59-25cb70e3b2b3
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 9d8a0587bdfce2284f4767087c88faab573e04b7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="interoperability-warnings"></a>Birlikte Çalışabilirlik Uyarıları
Birlikte çalışabilirlik uyarıları COM istemcileri ile etkileşimi destekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1400: P/Invoke giriş noktaları bulunmalıdır](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)|Ortak veya korumalı yöntem System.Runtime.InteropServices.DllImportAttribute özniteliği kullanılarak işaretlenir. Yönetilmeyen kitaplık bulunamadı ya da yöntem için bir işlev kitaplığında eşleştirilemedi.|  
|[CA1401: P/Invoke'lar görünür olmamalıdır](../code-quality/ca1401-p-invokes-should-not-be-visible.md)|Bir ortak türü bir public ya da korumalı yöntemi (Visual Basic'te Declare anahtar sözcüğü tarafından da uygulanan) System.Runtime.InteropServices.DllImportAttribute özniteliği var. Bu tür yöntemler açıkta kalmamalıdır.|  
|[CA1402: COM görünebilir arabirimler içinde aşırı yüklemelerden kaçının](../code-quality/ca1402-avoid-overloads-in-com-visible-interfaces.md)|Aşırı yüklenmiş yöntemler COM istemcilerine maruz kaldığında, sadece ilk yöntem aşırı yüklemesi adını korur. Sonraki aşırı yüklemeler adının sonuna alt çizgi karakteri (_) eklenerek ve aşırı yüklemenin tanımını karşılayacak şekilde bir tam sayı eklenerek benzersiz olarak yeniden adlandırılır.|  
|[CA1403: Otomatik yerleşim türleri COM görünebilir olmamalıdır](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)|COM görünür bir değer türü LayoutKind.Auto için System.Runtime.InteropServices.StructLayoutAttribute özniteliği kullanılarak işaretlendi. Bu tür düzenini sürümleri arasında değiştirebilir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], belirli bir düzen beklediğiniz COM istemcileri bozar.|  
|[CA1404: P/Invoke ardından hemen GetLastError Çağır](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)|Marshal.GetLastWin32Error yöntemi veya eşdeğer bir çağrı yapılır [!INCLUDE[TLA2#tla_win32](../code-quality/includes/tla2sharptla_win32_md.md)] GetLastError işlevi ve hemen önceki değil bir platform için yöntemi çağırın.|  
|[CA1405: COM görünebilir tür taban türler COM görünebilir olmalıdır](../code-quality/ca1405-com-visible-type-base-types-should-be-com-visible.md)|COM görünür türü, görünmeyen bir COM türünden türer.|  
|[CA1406: Visual Basic 6 istemcileri için Int64 bağımsız değişkenlerinden kaçının](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)|Visual Basic 6 COM istemcilerinde 64 bit tamsayı erişemiyor.|  
|[CA1407: COM görünebilir türler içinde statik üyelerden kaçının](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)|COM statik yöntemleri desteklemez.|  
|[CA1408: AutoDual ClassInterfaceType kullanma](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)|Çift arabirim kullanan türler, belirli bir arabirim düzenine bağlanmak için istemcileri etkinleştirir. Gelecek sürümdeki değişiklikler, türün düzeni veya bazı temel türler, arayüze bağlanan COM istemcilerini kesintiye uğratır. Varsayılan olarak, ClassInterfaceAttribute özniteliği belirtilmezse, salt dağıtılan arabirim kullanılır.|  
|[CA1409: Com görünebilir türler oluşturulabilmelidir](../code-quality/ca1409-com-visible-types-should-be-creatable.md)|Özellikle COM görünür olarak işaretlenmiş bir başvuru türü, parametreli ortak kurucu içeriyorsa ancak genel varsayılan (parametresiz) bir oluşturucuya sahip değildir. Genel varsayılan oluşturucu olmadan tür COM istemcileri tarafından oluşturulmamalıdır.|  
|[CA1410: COM kayıt yöntemleri eşleşmelidir](../code-quality/ca1410-com-registration-methods-should-be-matched.md)|Bir tür kullanarak işaretli bir yöntem bildirir <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> özniteliği ancak kullanarak işaretli bir yöntem bildirmiyor <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> özniteliği veya tam tersi.|  
|[CA1411: COM kayıt yöntemleri görünebilir olmamalıdır](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)|System.Runtime.InteropServices.ComRegisterFunctionAttribute özniteliği veya System.Runtime.InteropServices.ComUnregisterFunctionAttribute özniteliği kullanarak işaretli bir yöntem dışarıdan görünür olur.|  
|[CA1412: ComSource Arabirimlerini IDispatch olarak işaretleyin](../code-quality/ca1412-mark-comsource-interfaces-as-idispatch.md)|System.Runtime.InteropServices.ComSourceInterfacesAttribute özniteliğini kullanarak işaretlenen bir tür ve belirtilen arabirimlerden birini ayarlamak için ComInterfaceType.InterfaceIsIDispatch özniteliğine System.Runtime.InteropServices.InterfaceTypeAttribute özniteliğini kullanarak ayarlanır.|  
|[CA1413: COM görünebilir değer türleri içinde genel olmayan alanlardan kaçının](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)|COM-görünür değer türlerinin ortak olmayan örnek alanları COM istemcilerine görünürdür. Maruz kalmaması gereken, istenmeyen bir tasarım ya da güvenlik etkileri olan bilgi alanındaki içeriği gözden geçirin.|  
|[CA1414: boolean P/Invoke bağımsız değişkenlerini MarshalAs ile işaretleyin](../code-quality/ca1414-mark-boolean-p-invoke-arguments-with-marshalas.md)|Boolean veri türünün, yönetimsiz kod içinde birden fazla sunumu vardır.|  
|[CA1415: P/Invokes doğru bildirin](../code-quality/ca1415-declare-p-invokes-correctly.md)|Bu kural hedefleyen yöntem bildirimleri için platform çağırma arar [!INCLUDE[TLA2#tla_win32](../code-quality/includes/tla2sharptla_win32_md.md)] bir ÇAKIŞAN işaretçi olan işlevler parametre yapısını ve karşılık gelen yönetilen parametresi için bir işaretçi değil bir <xref:System.Threading.NativeOverlapped?displayProperty=fullName> yapısı.|