---
title: "CA2001: sorunlu yöntemleri çağırmaktan kaçının | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2001
- AvoidCallingProblematicMethods
helpviewer_keywords:
- CA2001
- AvoidCallingProblematicMethods
ms.assetid: 19db8edb-31ce-441c-b0de-a0f2746155b7
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: da5da213d400f846f634a98dbdbe919cedf03bcd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2001-avoid-calling-problematic-methods"></a>CA2001: Sorunlu yöntemleri çağırmaktan kaçının
|||  
|-|-|  
|TypeName|AvoidCallingProblematicMethods|  
|CheckId|CA2001|  
|Kategori|Microsoft.Reliability|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir üye olası tehlikeli ya da sorunlu yöntemi çağırır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Gereksiz ve potansiyel olarak tehlikeli olabilecek bir yöntem çağrıları yapma kaçının.  
  
 Bu kural ihlal üyesi aşağıdaki yöntemlerden birini çağırır oluşur.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|<xref:System.GC.Collect%2A?displayProperty=fullName>|GC çağrılıyor. Toplama, uygulama performansını önemli ölçüde etkileyebilir ve nadiren gereklidir. Daha fazla bilgi için bkz: [Riko Mariani'nın performans ipuçları](http://go.microsoft.com/fwlink/?LinkId=169256) MSDN'de blog girişi.|  
|<xref:System.Threading.Thread.Resume%2A?displayProperty=fullName><br /><br /> <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>|Thread.Suspend ve Thread.Resume beklenmeyen davranışları nedeniyle kullanım dışı bırakıldı.  Diğer sınıflarda kullanmak <xref:System.Threading> ad alanı, gibi <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex>, <xref:System.Threading.Mutex>, ve <xref:System.Threading.Semaphore> iş parçacığı eşitleme veya kaynakları korumak için.|  
|<xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A?displayProperty=fullName>|Geçersiz bir tanıtıcı döndürebildiğinden DangerousGetHandle yöntemi bir güvenlik riski oluşturur. Bkz: <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> ve <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A> DangerousGetHandle yöntemi güvenli bir şekilde kullanma hakkında daha fazla bilgi için yöntemleri.|  
|<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>|Bu yöntemler derlemelerini beklenmeyen konumlardan yükleyebilir. Örneğin, Suzanne Etikan'ın .NET CLR notları blog gönderilerine bakın [önce LoadFile işlevini vs. LoadFrom](http://go.microsoft.com/fwlink/?LinkId=164450) ve [bir bağlama bağlamı seçme](http://go.microsoft.com/fwlink/?LinkId=164451) derlemeler yükleme yöntemleri hakkında bilgi için MSDN Web sitesinde.|  
|[CoSetProxyBlanket](http://go.microsoft.com/fwlink/?LinkID=169250) (Ole32)<br /><br /> [CoInitializeSecurity](http://go.microsoft.com/fwlink/?LinkId=169255) (Ole32)|Zaman yönetilen bir işlemde çalışan kullanıcı kodu başlatır, bu çok geç güvenilir bir şekilde CoSetProxyBlanket çağırmaktır. Ortak dil çalışma zamanı (CLR) P/Invoke kullanıcıların başarılı engelleyebilir başlatma eylemleri gerçekleştirir.<br /><br /> Yönetilen bir uygulama için CoSetProxyBlanket çağırmak varsa, bir yerel kod (C++) yürütülebilir dosyası kullanarak işlemini başlatmak CoSetProxyBlanket yerel kodda çağırın ve sonra yönetilen kod uygulamanızı işleminde başlatmak öneririz. (Bir çalışma zamanı sürüm numarası belirttiğinizden emin olun.)|  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için kaldırmak veya tehlikeli veya sorunlu yöntemi çağrısı değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Yalnızca hiçbir alternatifleri sorunlu yöntemi kullanılabilir olduğunda bu kuraldan iletilerini.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenilirlik Uyarıları](../code-quality/reliability-warnings.md)