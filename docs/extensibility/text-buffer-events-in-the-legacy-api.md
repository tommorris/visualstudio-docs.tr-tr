---
title: "Metin arabelleği olayları eski API'sindeki | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - text buffer events
ms.assetid: 9be49e9f-1864-41c2-8a3c-f66895881341
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7e7847cdca2065cadd6adaf0d4b3e6ea10444725
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="text-buffer-events-in-the-legacy-api"></a>Eski API metin arabelleği olayları
Metin arabellek nesnesi farklı durumlarda yanıt olanak sağlayan birkaç farklı olayları gösterir.  
  
 Eski API'si kullanılırken metin arabelleği değişikliklerle ilgili bildirim almak için aşağıdaki arabirimleri uygulamanız gerekir. Metin arabelleği kullanarak arabirimleri kullanıma `IConnectionPointContainer` satır bildirim almak için metin arabelleğini arabirimde arabelleğinden değiştirir. Daha fazla bilgi için bkz: [nasıl yapılır: kayıt eski API olan metin arabelleği olaylar için](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md). Durumunda `IVsTextStreamEvents` veya `IVsTextLinesEvents` arabirimleri, değişiklikleri döndürülür ya da bir veya two dimensional koordinatlarında, sırasıyla.  
  
## <a name="text-buffer-interfaces"></a>Metin arabelleği arabirimleri  
 Metin arabelleği nesne tarafından uygulanan arabirimler aşağıda verilmiştir.  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Bileşik eylemleri (diğer bir deyişle, bir tek geri alma/yineleme biriminde gruplandırılır Eylemler) oluşturulmasını sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Metin arabelleğini tarafından yönetilen belge veri kalıcılığını etkinleştirir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Temel hizmetleri sağlayan; birçok istemciler tarafından kullanılır.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Sağlar okuma ve yazma iki boyutlu koordinatları kullanarak yetenekleri. Öğesinden devralınan `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Hızlı, metin arabelleği akış odaklı, sıralı erişim sağlar.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Sağlar okuma ve yazma yeteneklerini tek boyutlu koordinatları kullanarak. Öğesinden devralınan `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Bir genel koleksiyon özelliklerinin erişim sağlar. En önemli özelliğinin adı veya arabellek ad olmalıdır. Bir GUID oluşturarak ve bir anahtar olarak kullanarak rastgele verilerinizi bu arabirimle arabellek depolayabilirsiniz.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Bağlantı noktaları için olayları destekler.|  
  
## <a name="text-buffer-event-interfaces"></a>Metin arabelleği olay arabirimleri  
 Metin arabelleği olay bildirimi arabirimleri aşağıda verilmiştir.  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferEvents>|Yeni bir dil hizmeti bir metin arabelleği ile ilişkili olduğunda istemcilere bildirir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferDataEvents>|İstemciler, bir metin arabelleği başlatıldığında ve metin arabelleği verilerde değişiklik yapıldığında bildirir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStreamEvents>|Tek boyutlu koordinatlarında temel metin arabellek değişiklikleri istemcilere bildirir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>|Temel metin arabellek iki boyutlu koordinatlarında değişiklikleri istemcilere bildirir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserDataEvents>|Kullanıcı verilerde yapılan değişiklikleri istemcilere bildirir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsPreliminaryTextChangeCommitEvents>|Olayı tetiklemek için son yürütme hareketi istemcilere bildirir ve değiştirilen metin aralığını sağlar. `IVsPreliminaryTextChangeCommitEvents` Arabirimi değil geri veya komutları yinelemek için yanıt olarak tetiklenir. Olaylar, yalnızca bir geri alma yöneticisi olan arabelleklerini kov. `IVsPreliminaryTextChangeCommitEvents`Asıl listenin gibi diğer olayları önce değişiklikler kaydedilmeden önce diğer olaylarla metni değiştirmeyin emin olmak için tetiklenir. VSPackage ya da izlemelisiniz `IVsPreliminaryTextChangeCommitEvents` arabirimi veya `IVsFinalTextChangeCommitEvents` arabirimi, ancak ikisini birden değil.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFinalTextChangeCommitEvents>|Olayı tetiklemek için son yürütme hareketi istemcilere bildirir ve değiştirilen metin aralığını sağlar. `IVsFinalTextChangeCommitEvents` Arabirimi değil geri veya komutları yinelemek için yanıt olarak tetiklenir. Olaylar, yalnızca bir geri alma yöneticisi olan arabelleklerini kov. `IVsFinalTextChangeCommitEvents`Yalnızca dil hizmetler veya düzenleme üzerinde tam denetime sahip diğer nesneleri tarafından kullanılmaya yöneliktir. VSPackage ya da izlemelisiniz `IVsPreliminaryTextChangeCommitEvents` arabirimi veya `IVsFinalTextChangeCommitEvents` arabirimi, ancak ikisini birden değil.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski API kullanarak metin arabelleği erişme](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)   
 [Nasıl yapılır: metin arabelleği olayları eski API ile kaydetme](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)